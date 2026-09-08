# 🏗️ Architecture

This folder documents the technical architecture of **DatumLex** — how the system is structured, how data flows through it, and the design decisions behind it.

## Contents

- **Dimensional model** — conceptual, logical, and physical models of the Data Warehouse (Star/Snowflake schema), including fact tables (judicial decisions, processes) and dimensions (legal themes, courts, authors, time periods).
- **Data dictionary** — detailed description of every table, field, data type, constraint, key, and relationship in the model. *(Required by FATEC — must be validated before implementation starts on each sprint.)*
- **ETL architecture** — how data is extracted from external sources (DataJud/CNJ, state TJs, official gazettes, jurisprudence repositories), transformed (including NLP-based theme extraction), and loaded into the warehouse.
- **System/component diagrams** — how the Django application, ETL pipelines, database, and dashboard relate to each other.
- **Technology decisions** — key architectural choices and the reasoning behind them (e.g. why a given OLAP approach, why Django, why a given NLP API).

## Why it matters

This is the folder evaluators will check first to understand *why* the system is built the way it is, not just what it does. Every non-trivial architectural decision should be traceable to a reason documented here — especially the dimensional model, since it's an explicit graded requirement of the challenge.