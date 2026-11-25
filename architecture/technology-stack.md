# Technology Stack and Rationale

**Last updated:** November 25, 2026  
**Status:** Active production architecture (`datumlex-core.vercel.app` + Railway + PostgreSQL 18 + SonarCloud)

## Purpose

This document records the technologies adopted for **DatumLex** and the architectural rationale behind each decision. It reflects the real production stack delivered through Sprint 3 and refined for the Solutions Fair (December 3, 2026), replacing earlier exploratory drafts.

DatumLex is a legal intelligence and analytics platform that consolidates judicial records, jurisprudence, precedents, and open doctrine from official Brazilian public sources into a structured analytical repository, exposing statistical indicators, real Natural Language Processing (NLP), source-grounded generative AI (RAG), and reproducible PDF/XLSX exports.

## Stack at a Glance

| Area | Technology | Version / Tier | Primary responsibility |
|---|---|---|---|
| **Backend language** | Python | `3.13` | API logic, ETL pipelines, statistical NLP, and AI orchestration |
| **Backend framework** | Django + Gunicorn | `5.2` | REST API, RBAC authentication, ORM/migrations, security & CSRF defaults |
| **Real NLP engine** | spaCy + scikit-learn | `spacy 3.8` (`pt_core_news_sm`) · `scikit-learn 1.9` | Tokenization, lemmatization, POS-tagging, Portuguese Named Entity Recognition (NER), `TfidfVectorizer` term extraction, and `cosine_similarity` semantic ranking — running on CPU at zero per-request cost |
| **Generative AI (RAG)** | Google Gemini API | `gemini-3.5-flash-lite` | Source-grounded legal synthesis over retrieved indicators and numbered sources (`F1..Fn`), with automatic deterministic fallback |
| **Frontend framework** | React + Vite | `React 19` · `Vite 8` | Interactive multi-court research workspace, NLP dashboard, RAG chat, corpus explorer, and accessible charts |
| **Edge & API Gateway** | Vercel + Node Gateway | Same-origin `/api/gateway.js` | Global HTTPS static delivery and same-origin proxy that isolates backend origin, preserves `HttpOnly` cookies, and blocks secret exposure |
| **Database** | PostgreSQL | `18` (Railway managed, TLS) | Dimensional Data Warehouse (`fact_resource`, `dim_*`), approved corpus (`warehouse_legalcorpusitem`), references (`legal_reference`), and append-only NLP audit tables with integrity triggers |
| **Backend & DB Hosting** | Railway | Dockerized service + Postgres 18 | Continuous zero-sleep deployment of API + NLP + PostgreSQL 18 (superseded Render Free tier) |
| **Quality & CI/CD** | GitHub Actions + SonarCloud | Public Quality Gate (`DatumLex_datumlex-core`) | Automated Linux + Windows test runs (400+ tests), Ruff, ESLint, HTML/XML/LCOV coverage reports, and static security/reliability gate (`0 Bugs`, `0 Vulnerabilities`) |
| **Official Data Sources** | DataJud/CNJ, Pangea/BNP, STJ, TJDFT, Senado RIL | 9 active civil courts + open doctrine | 32,000+ real official records in production, with modular multi-sphere expansion roadmap (Federal, State, District, and Municipal) |

---

## Technology Decisions & Rationale

### 1. Python 3.13 + Django 5.2 for Backend, ETL, and Analytics
Python unifies API serving, ETL ingestion, data validation, and NLP processing in a single runtime, eliminating polyglot operational overhead. Django 5.2 provides mature relational modeling, deterministic schema migrations, session security, CSRF enforcement, and role-based access control (`Master`, `Admin`, `Padrão`) with per-court authorization.

### 2. Real Statistical & Neural NLP on CPU (`spaCy` + `scikit-learn`)
Rather than relying on regex heuristics or costly GPU-hosted LLMs for corpus analysis, DatumLex runs a real Portuguese NLP pipeline directly on standard CPU instances (`backend/src/nlp/engine.py`):
- **`spaCy 3.8` with `pt_core_news_sm`**: neural Portuguese pipeline performing tokenization, lemmatization, part-of-speech analysis, and **Named Entity Recognition (NER)** across real judicial summaries and user queries.
- **`scikit-learn 1.9` (`TfidfVectorizer` + `cosine_similarity`)**: unigram/bigram sublinear TF-IDF vectorization over real approved decisions and live cosine similarity ranking exposed via `GET /api/v2/nlp-insights/` and rendered interactively in the **NLP · Teses** panel.
- **Curated literal evidence auditability**: alongside live statistical NLP, 46 curated official decisions (33 TJDFT + 13 STJ) and 135 verified `LEGAL_THESIS`/`LEGAL_GROUND` passages are protected by PostgreSQL append-only triggers (`nlp_no_change` and `nlp_check_revision`) that verify literal character offsets and `SHA-256` text hashes.

### 3. Source-Grounded Generative AI (`Gemini 3.5 Flash-Lite` in RAG Architecture)
Generative synthesis is strictly constrained to a **Retrieval-Augmented Generation (RAG)** workflow:
1. Incoming questions are preprocessed with `spaCy` (lemmas, NER entities, and intent classification).
2. The backend executes deterministic SQL aggregations over the user's authorized scope and retrieves approved jurisprudence, precedents, and doctrine as numbered sources (`F1..Fn`).
3. `gemini-3.5-flash-lite` receives only that structured evidence packet with strict grounding instructions forbidding fabricated numbers or uncited case law.
4. If the external LLM is rate-limited or unavailable, the backend degrades gracefully to a deterministic local synthesis over the same verified sources.

### 4. React 19 + Vite 8 + Vercel Same-Origin Gateway
React 19 and Vite 8 deliver a fast, responsive SPA with explicit loading, empty, partial, and error states. Deploying on **Vercel** provides global HTTPS CDN delivery, instant PR preview environments, and a lightweight serverless same-origin gateway (`frontend/api/gateway.js`) so the browser communicates exclusively with `datumlex-core.vercel.app/api/*` without cross-site cookie issues or leaked credentials.

### 5. PostgreSQL 18 + Railway (Migration from Render Free Tier)
Earlier prototypes ran on Render's free tier (see historical record [RENDER-HOSTING-RATIONALE.md](../design/RENDER-HOSTING-RATIONALE.md)). Because Render Free sleeps after 15 minutes of inactivity and deletes PostgreSQL instances after 30 days without managed backups, production was migrated to **Vercel (Frontend + Gateway) + Railway (Docker API + PostgreSQL 18)**. Everything remains 100% containerized and SQL-standard, enabling seamless FinOps migration to dedicated VPS + Cloudflare R2 cold storage as national and municipal data volumes grow (detailed in [hosting-and-scalability.md](hosting-and-scalability.md)).

### 6. Automated Testing, Coverage & SonarCloud Governance
Quality is enforced continuously through GitHub Actions and SonarCloud:
- **`scripts/test-report.py`** executes backend unit tests, full Django/pytest integration suite (359+ tests), frontend unit tests (20 tests), and NLP/collector validation tools (24 tests), generating an interactive HTML dashboard (`backend/tests/relatorio-cobertura.html`) plus Sonar-compatible XML/LCOV reports.
- **SonarCloud (`DatumLex_datumlex-core`)** evaluates every Pull Request and branch with `.sonarcloud.properties` and `sonar-project.properties`, maintaining a **PASSED** Quality Gate (`0 Bugs`, `0 Vulnerabilities`, Security/Reliability/Maintainability `A`).

---

## Architecture Boundaries

- **Frontend (`frontend/`):** presentation, interactive filtering, accessible visualization, and explicit data-state rendering; never computes legal rates independently or holds secrets.
- **Backend (`backend/`):** authoritative source for RBAC, SQL metrics, real NLP (`spaCy` + `scikit-learn`), RAG orchestration, and reproducible PDF/XLSX generation.
- **PostgreSQL 18 (`datumlex-db`):** persistent analytical warehouse and append-only NLP audit ledger (~75 MB currently holding 32,000+ real official records).
- **ETL Ingestion:** decoupled, idempotent Python pipelines with `SHA-256` deduplication and cursor checkpoints, keeping ingestion isolated from API serving latency.

## Related Documents

- [Cloud Hosting, Multi-Sphere Scalability & 36-Month Costs](hosting-and-scalability.md)
- [Dimensional Model](dimensional-model.md) · [Data Dictionary](data-dictionary.md)
- [ETL Overview](etl-overview.md) · [ETL Operations](etl-operations.md)
- [Sprint 3 Delivery Snapshot](../agile/sprint-3-delivery.md)
- [Architecture, Scalability, Costs & 36-Month Support Proposal (PDF v3.0)](../presentation/DatumLex_Plano_Arquitetura_Escalabilidade_Custos_Suporte_v3.pdf)
