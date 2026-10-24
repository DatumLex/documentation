# DatumLex ETL: How It Works

This document describes the ETL that exists in the repository today. The ETL is a set of Python entry points in `etl/` that call Django management commands and transformation code in `backend/`. It is not a separate data warehouse or an independently deployable application: it shares the backend's Django models, migrations, settings, and configured database.

## At a glance

```text
CNJ DataJud ──> extract_datajud ──> validate/normalize ──> dimensional tables
                                                            ├─> process movements
                                                            └─> extraction audit
STJ open-data catalog ──> stj_documents.py ──> metadata + versioned text files
Pangea public search ──> sync_pangea ──> legal references (pending legal approval)
```

The three paths have different source records and purposes. DataJud supplies public case metadata used by the analytical process dataset. The STJ catalog collector stores official publication metadata and full-text files as a separate operational collection. Pangea imports public precedent references and citation metadata. These sources are not automatically merged into one record or treated as interchangeable.

## 1. DataJud case metadata

`etl/run.py` bootstraps the backend environment and invokes its existing `extract_datajud` Django command. `etl/run.py --court STJ` selects the STJ DataJud endpoint; the default is TJDFT. The command can also be run directly through Django from `backend/`.

For remote collection, the DataJud client submits a bounded query for public (`nivelSigilo = 0`) records matching the explicitly supplied subject codes and date scope. Historical runs filter by `dataAjuizamento`; update runs can filter by `dataHoraUltimaAtualizacao`. The client requests only allowlisted source fields, sorts results, and uses DataJud's `search_after` cursor for pagination. Transient HTTP/network failures receive bounded retries; incomplete or non-advancing pages are rejected.

Each record is normalized and validated before loading. Validation checks tribunal and public scope, a source identifier, the 20-digit CNJ process number, filing date, explicit subject match, class and organization codes, and supported degree. Invalid records are counted and written to `RejectedRecord`; they do not enter the dimensional fact. Source metadata is allowlisted and hashed, rather than storing arbitrary fields from an API response or a supplied JSON sample.

Accepted records are upserted by source ID into the dimensional model: process, time, class, organization, degree, result, and subject dimensions; one `FactProcess` row per unique DataJud source document; a process-subject bridge; and the process movements captured in that source snapshot. The fact's weight is one document, not one individual appeal. A later source revision replaces its subject links and movement snapshot. A record older than the stored source update timestamp is counted as stale and does not overwrite newer data. The loader classifies the existing outcome rules and assigns a result dimension; this is a rule-based classification, not a legal review.

The extraction run records scope, status, cursor, source total where available, page count, and created/updated/rejected/stale/fetched counters. Each result page and its cursor are committed together, so a failed page can be retried safely. Runs can pause after a page limit and resume from the saved cursor.

## 2. STJ official publication texts

`etl/stj_documents.py` is a separate collector for the STJ open-data catalog. It reads the catalog, preserves a hash-addressed catalog snapshot, finds publication batches in the requested date interval, filters metadata by explicit subject codes, and downloads the associated official ZIP when available. It reads matching `.txt` or `.pdf` members without extracting archive paths and stores selected text locally under `etl/data/stj-documents/texts/` using the document ID and content hash in the filename.

Metadata, source URLs, publication and available decision fields, content hash, local relative path, text availability, collection run, and immutable version fingerprints are recorded in operational database tables. Publication timestamps expressed as epoch milliseconds are interpreted in `America/Sao_Paulo`. Missing text and malformed rows are tracked for reconciliation; completed batches can be skipped on a repeat run, while `--refresh` rereads them for source revisions. A file lock prevents concurrent local collector runs.

This collection is distinct from DataJud's analytical fact. An STJ publication is not automatically matched to a DataJud process, and its text does not itself change a legal outcome or dashboard metric. `numeroRegistro` is not assumed to be a CNJ process number. The catalog's available batches do not prove complete tribunal coverage.

## 3. Pangea public precedent references

`etl/pangea.py` calls the backend's `sync_pangea` management command. The command searches the public Pangea/BNP precedent endpoint for a query, validates that results belong to the STJ and are not marked confidential, extracts plain text from thesis/question fields, and retains explicitly listed paradigm-process citations. It records source metadata and a canonical payload hash, then creates or updates a `LegalReference` keyed by source and identifier.

Imported references remain unapproved. If an already approved reference's source payload changes, its approval is reset to pending. Pangea's `ultimaAtualizacao` is stored as a source-update date, not presented as a judgment or publication date. Importing a reference does not establish that it applies to a case or include it in legal indicators.

## Runtime and boundaries

The process is launched separately from the web server, but imports backend code and writes to the same configured database. Environment precedence is process environment, `etl/.env`, `backend/.env`, then Django defaults. The ETL entry point does not start a database, run migrations, provision users, or start the frontend. Apply backend migrations before using a schema that requires them. Use the same database as the backend when the dashboard should display the loaded data.

The detailed commands, options, database setup, and operating limits are in [ETL Operations Reference](ETL-OPERATIONS.md). For schema mapping and STJ data lineage, see [STJ Architecture](STJ-ARCHITECTURE.md) and the backend's [resource schema](../backend/docs/resource-schema.md).
