# DatumLex ETL Operations Reference

This reference documents how to configure and run the current ETL entry points. Keep `etl/` beside `backend/` in the same checkout. Django commands, transformations, models, and migrations remain in `backend/` and are reused by the ETL launchers.

## Runtime and configuration

The DataJud and Pangea launchers require Python 3.12+ and the ETL dependencies. From the repository root in PowerShell:

```powershell
cd etl
python -m venv .venv
.venv/Scripts/python.exe -m pip install -r requirements.txt
Copy-Item .env.example .env
```

Configure `DATAJUD_API_KEY` for DataJud and optionally `DATABASE_URL` in `etl/.env`. Do not overwrite an existing local `.env`. Environment precedence is process variables, `etl/.env`, `backend/.env`, then Django defaults. Without `DATABASE_URL`, Django's configured local SQLite database is used. Docker hostnames such as `db` only resolve inside the relevant Docker network; a host-run ETL process must use a published host and port. The database must already be migrated by the backend. The ETL entry points do not apply migrations or initialize infrastructure.

Use the same database as the backend if the dashboard/API should read the extracted records. Paths passed to `--input` are resolved from the terminal's current directory.

## DataJud: historical/date-range extraction

Get help without making a source request:

```powershell
.venv/Scripts/python.exe run.py --help
```

Example bounded collection (two pages, at most 200 records):

```powershell
.venv/Scripts/python.exe run.py --subjects 10431,10433,10439 --start 2023-01-01 --end 2026-10-23 --page-size 100 --max-pages 2
```

Options:

| Option | Behavior |
| --- | --- |
| `--court TJDFT\|STJ` | Selects the DataJud tribunal endpoint; default is `TJDFT`. |
| `--subjects` | Comma-separated positive TPU codes. Only the listed codes are requested; descendants are not expanded automatically. |
| `--start`, `--end` | Inclusive calendar date range for `dataAjuizamento`; defaults are 2023-01-01 and the execution date. Supported start dates are 2023 or later. |
| `--page-size` | Page size from 1 to 1000; default 100. |
| `--max-pages` | Maximum pages in this invocation; default 5. `0` continues until an empty source page. |
| `--resume ID` | Resumes a paused or failed remote DataJud run from its saved scope/cursor. |
| `--updated-since ISO_DATETIME` | Runs an update query by DataJud's update timestamp instead of a filing-date range. |
| `--input PATH` | Loads one local DataJud response with a `hits.hits` list as a sample; it does not page the remote API. |

If a run pauses or fails, use its printed ID:

```powershell
.venv/Scripts/python.exe run.py --resume 1 --max-pages 5
```

A repeated new command may automatically claim the most recent paused/failed remote run only when its complete scope matches. A resume uses the run's saved tribunal even if `--court` is omitted. File samples finish with status `sample` and are not resumable remote runs. A `paused` run is incomplete even if the process exits successfully. `--max-pages 0` may perform a large extraction.

The cursor and counters are stored in `ExtractionRun`. Each whole page and its new cursor are committed atomically. Re-running a resumed page is safe because the loader upserts by source ID. This is cursor-based recovery, not a scheduled refresh policy for every old source record. A separate backend scheduler may perform recurring historical/update synchronization; running these commands manually does not create a schedule.

## STJ DataJud metadata

Use the same DataJud command with `--court STJ`. For example:

```powershell
.venv/Scripts/python.exe run.py --court STJ --subjects 10431,10433,10439 --start 2023-01-01 --end 2026-10-23 --max-pages 0
```

This is still the DataJud metadata path. It does not download official STJ decision texts and does not make the STJ text collector run automatically.

## STJ official text collector

The official text collector has its own required end date and defaults to a 2023-01-01 start and subject codes `10431,10433,10439`:

```powershell
.venv/Scripts/python.exe stj_documents.py --start 2023-01-01 --end 2026-10-23 --subjects 10431,10433,10439
```

`--max-batches N` caps publication batches processed in this invocation; zero means no explicit cap. `--refresh` rereads batches that were previously complete, so revised source content can be observed. Without refresh, complete batches for the same scope are skipped; batches with missing documents or failed rows are retried when the same command is repeated. A batch limit marks the run `paused`. At the end, outstanding missing documents or failed rows produce `partial`; otherwise it is `completed` for available catalog batches. Completion is not a claim of full STJ coverage.

Catalog snapshots and text files live under `etl/data/stj-documents/`. The catalog is retained by content hash; text files use `seqDocumento` plus the SHA-256 of the bytes. Database records retain provenance and versions. The collector's Windows lock prevents two local collector instances from running concurrently. It uses the official STJ open-data host and validates download URLs.

## Pangea public precedent import

```powershell
.venv/Scripts/python.exe pangea.py --query "responsabilidade civil" --page-size 100 --max-pages 5
```

`--query` defaults to `responsabilidade civil`; page size is 1–100 and page count must be positive (default 5). The command reads the public catalog, searches STJ precedent records, and records a `PangeaImportRun` with query, page counts, fetched/created/updated/rejected totals, source total, and status. It has no automatic scheduler in this ETL folder. Imports stay pending legal approval, and are not automatically linked as adherence assessments or used as approved outcomes.

## Data model and source boundaries

| Pipeline | Main persisted data | Operational/audit data |
| --- | --- | --- |
| DataJud | Dimensional case/document fact, process-subject bridge, movements | `ExtractionRun`, rejected-record reasons, source payload hash |
| STJ publication texts | STJ document metadata and local official text files; immutable versions | `STJIngestionRun`, per-scope/day `STJDocumentBatch`, catalog and content hashes |
| Pangea | STJ legal references and explicit paradigm citations | `PangeaImportRun`, query/catalog/source metadata and payload hash |

DataJud `FactProcess` has one row per unique source document, weighted as one. Subject links do not multiply the fact count. STJ full text and Pangea precedent references are separate collections and are not automatic joins to DataJud facts. Do not treat the STJ registration number as a CNJ process number without a separately evidenced match.

## Operating constraints

- Run only one DataJud extraction against a given database at a time; avoid concurrent writes to the same scope.
- Run only one local STJ text collector at a time; a lock enforces this on Windows.
- Public subject filters use explicit codes. Descendant codes are not implicitly queried.
- API/catalog availability bounds what can be collected. An empty result or completed catalog traversal does not prove tribunal-wide completeness.
- Resuming a run continues its saved cursor. It does not refresh all old source documents; use the documented update workflow or explicit `--updated-since` when appropriate.
- Apply backend migrations when required by the selected pipeline/schema. Coordinate schema changes with the backend models and migrations.
- Consult [ETL Overview](ETL-OVERVIEW.md), [STJ Architecture](STJ-ARCHITECTURE.md), and the [backend README](../backend/README.md) for design, lineage, and scheduling context.
