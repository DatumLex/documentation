# 🏗️ Architecture

This folder documents the technical architecture of **DatumLex** — how the system is structured, how data flows through it, and the design decisions behind it.

## Contents

- **Dimensional model** — conceptual, logical, and physical models of the Data Warehouse (Star/Snowflake schema), including fact tables (judicial decisions, processes) and dimensions (legal themes, courts, authors, time periods).
- **Data dictionary** — detailed description of every table, field, data type, constraint, key, and relationship in the model. *(Required by FATEC — must be validated before implementation starts on each sprint.)*
- **ETL architecture** — how data is extracted from approved sources (DataJud-only Sprint 1; STJ, jurisprudence, and open doctrine in later sprints), transformed (including NLP-based theme extraction), and loaded into the warehouse.
- **System/component diagrams** — how the Django application, ETL pipelines, database, and dashboard relate to each other.
- **Technology decisions** — key architectural choices and the reasoning behind them (e.g. why a given OLAP approach, why Django, why a given NLP API).

## Documents

- [Dimensional Models](/dimensional_model/dimensional-model.md) — existing conceptual/logical/physical diagrams; review and dictionary evidence remain required.
- [Data-Dictionary](https://github.com/DatumLex/documentation/blob/main/architecture/dimensional_model/data-dictionary.md) - existing data-dictionary; Document all tables, columns and data lineages.
- [Source Research](research/README.md) — source notes and their sprint boundaries.
- [Technology Stack and Rationale](technology-stack.md) — selected technologies,
  their responsibilities, and the rationale for each architectural decision.

## Why it matters

This is the folder evaluators will check first to understand *why* the system is built the way it is, not just what it does. Every non-trivial architectural decision should be traceable to a reason documented here — especially the dimensional model, since it's an explicit graded requirement of the challenge.

## Backlog and estimation

Modeling, source investigation, contracts, migrations, and tests contribute to
the parent story's `Estimate`; do not duplicate points on tasks. Follow the
[estimation policy](../agile/estimation-and-prioritization.md) and
[roadmap](../product/product-roadmap.md). Diagrams alone do not establish an approved
dictionary, implementation, or validated source coverage.
