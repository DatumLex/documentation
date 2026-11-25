# Sprint 3 & Solutions Fair Delivery Snapshot — DatumLex

**Snapshot date:** November 25, 2026  
**Target milestones:** Sprint 3 Review (November 23–27, 2026) & Solutions Fair (December 3, 2026)  
**Live application:** [https://datumlex-core.vercel.app/](https://datumlex-core.vercel.app/)  
**Pull Request & CI:** [DatumLex/datumlex-core#208](https://github.com/DatumLex/datumlex-core/pull/208)  
**SonarCloud Quality Gate:** [PASSED (`0 Bugs`, `0 Vulnerabilities`, `A / A / A`)](https://sonarcloud.io/dashboard?id=DatumLex_datumlex-core&pullRequest=208)

---

## Executive Summary

Through Sprint 3 and post-review hardening, **DatumLex** reached a complete, production-deployed legal intelligence release running on real official judicial data across **9 Brazilian courts** (`STJ`, `TJDFT`, `TJSP`, `TJMG`, `TJRJ`, `TJRS`, `TJPR`, `TRF1`, `TRF3`), with real statistical/neural NLP (`spaCy` + `scikit-learn`), source-grounded generative AI (`Gemini 3.5 Flash-Lite` RAG), reproducible PDF/XLSX exports, and continuous quality verification on GitHub Actions and SonarCloud.

## Delivered Production Dataset (`datumlex_release_real_civil_2026_11` — 75 MB)

| Dataset Layer | Live Production Count | Verification & Provenance |
|---|---:|---|
| **DataJud Process Records** (`fact_resource`) | **13,594** | 13,565 distinct CNJ numbers across 9 courts; 686 binary merit-eligible (139 granted / 547 denied); explicit exclusion funnel |
| **Approved Legal Corpus** (`warehouse_legalcorpusitem`) | **16,865** | 13,944 jurisprudence decisions · 2,772 Pangea/BNP precedents · 149 Senate RIL & open doctrines |
| **Official Legal References** (`legal_reference`) | **1,474** | 1,467 approved precedents + 7 approved doctrines (traceable links and citations) |
| **Curated NLP Decisions & Evidences** | **46 decisions / 135 evidences** | 33 TJDFT + 13 STJ official texts; 135 approved `LEGAL_THESIS` & `LEGAL_GROUND` literal spans validated by PostgreSQL `SHA-256` & append-only triggers |
| **Precedent Usage Links** | **248** | 70 applied · 39 not applied · 36 mentioned · 103 ambiguous |

## Delivered Capabilities Mapped to Product Backlog

| Capability Area | Related Backlog Stories | Implementation & Evidence |
|---|---|---|
| **Multi-court analytical dashboard & filters** | US-01–US-07, US-21, US-44 | React 19 / Vite 8 workspace on Vercel with dynamic multi-court, subject (TPU/CNJ), period, outcome, and source filters + transparent exclusion funnel |
| **Cross-source corpus, precedents & doctrine** | US-08–US-10, US-28–US-30 | Unified explorer across DataJud, STJ, TJDFT, Pangea/BNP, and Senate RIL doctrine with clickable official links and session notebook |
| **Real NLP Engine (`spaCy` + `scikit-learn`)** | US-11, US-31–US-33, US-43 | `backend/src/nlp/engine.py` (`spacy==3.8.18` `pt_core_news_sm` + `scikit-learn==1.9.1` `TfidfVectorizer` & `cosine_similarity`), endpoint `GET /api/v2/nlp-insights/`, interactive UI in **NLP · Teses** (top TF-IDF terms, grouped NER entities, live cosine similarity search) + curated theses/grounds with literal passages |
| **Precedent adherence & temporal trends** | US-12–US-14, US-34–US-36 | Precedent application/non-application breakdown, quarterly filing evolution charts, and court coverage diagnostics |
| **Reproducible PDF & XLSX exports** | US-15, US-16, US-37, US-38 | Server-side PDF synthesis and XLSX evidence/records exports preserving active filters, counting units, and official URLs |
| **Source-grounded AI Chat (Gemini RAG)** | US-17, US-39 | Dual chat integration (`Chat da pesquisa` and `Chat de análise · IA`) using `gemini-3.5-flash-lite` grounded strictly in SQL metrics and numbered sources (`F1..Fn`), displaying spaCy lemmas & NER per question, with automatic deterministic fallback |
| **Quality, Security & DevOps** | US-12, US-17, US-18, US-24–US-27, US-45 | 400+ automated tests (359 backend integration + 23 unit + 24 tools + 20 frontend), Ruff + ESLint zero errors, HTML/XML/LCOV coverage (`scripts/test-report.py`), SonarCloud Quality Gate **PASSED** (`0 Bugs`, `0 Vulnerabilities`) |

## Process & Governance Artifacts Delivered

- **Updated Architecture & FinOps Proposal (36-month support):** [DatumLex_Plano_Arquitetura_Escalabilidade_Custos_Suporte_v3.pdf](../presentation/DatumLex_Plano_Arquitetura_Escalabilidade_Custos_Suporte_v3.pdf) and [hosting-and-scalability.md](../architecture/hosting-and-scalability.md) — covering Vercel + Railway production topology, multi-sphere scalability (including the municipal sphere), 36-month cost projection, and provider-to-client handover.
- **Process documentation:** Scrum/Kanban workflow, Definition of Ready, Definition of Done, MoSCoW, Planning Poker, QA Guide, and Branch/Commit standards maintained in `DatumLex/documentation`.
