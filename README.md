# 📚 DatumLex — Documentation

Central documentation repository for **DatumLex** — an analytical platform (Data Warehouse + Web Dashboard) for consolidating and analyzing judicial decisions, jurisprudence, and academic doctrines.

> 💻 Source code: [datumlex-core](https://github.com/DatumLex/datumlex-core)
> 📋 Board / Backlog: [GitHub Project](https://github.com/orgs/DatumLex/projects/1/views/9?visibleFields=%5B%22Title%22%2C%22Assignees%22%2C%22Status%22%5D)

---

## 🏢 About the Project

DatumLex is a legal intelligence platform designed to support more informed and
consistent decision-making. It brings together judicial decisions,
jurisprudence, and other official legal data that are often spread across
different sources, then organizes them into information that can be explored
through a web dashboard.

The product helps legal professionals and decision-makers identify patterns,
compare outcomes, and understand relevant judicial context more efficiently.
Rather than replacing professional legal judgment, DatumLex is intended to
provide reliable, structured evidence that supports analysis and decision-making.

### Product goals

- Consolidate official judicial data into a structured analytical repository.
- Make legal information easier to search, filter, compare, and interpret.
- Surface indicators and trends that support evidence-based legal analysis.
- Reduce the time spent gathering information from disconnected sources.

| | |
|---|---|
| **Institution** | Fatec SJC — Database, 5th semester (evening) |
| **Team** | LegacyTech |
| **Academic Partner** | Xertica (Juan Hassam, Gerson Rolim) |
| **Professors / Evaluators** | Eduardo Sakaue, Juliana Pasquini |
| **Stack** | Python/Django, React/Tailwind, PostgreSQL DW, Vercel + Railway; DataJud-only Sprint 1, cross-source NLP in later sprints |

## 👥 Team

| Name | Role | GitHub | LinkedIn |
|---|---|---|---|
| Pedro Mattos | Product Owner (P.O.) | [pedromattos11](https://github.com/pedromattos11) | |
| Ed Wilson | Scrum Master | [EdWilsonsj](https://github.com/EdWilsonsj) | |
| Abimael Souza | Developer | [Bima0195](https://github.com/Bima0195) | |
| Thiago Chaves | Developer | [ThiagoChaves13](https://github.com/ThiagoChaves13) | |
| Johnatan Coelho | Developer | [JohnatanCoelho](https://github.com/JohnatanCoelho) | |
| Diego Vitvicki | QA | [dievit](https://github.com/dievit) | |

---

## 🗂️ Repository Structure

```
documentation/
├── agile/          → agile management, backlog, sprints
├── architecture/   → data modeling and ETL
├── development/    → development, review, QA, and delivery workflow
├── design/         → visual identity and prototypes
├── product/        → product vision, audiences, roadmap, and references
└── presentation/   → official deliverables for evaluators
```

## 🔗 Documentation Index

### Agile / Scrum
- [Agile folder overview](agile/README.md)
- [User Stories, Priorities, and Planned Sprints](agile/user-stories.md)
- [Planning Poker, estimativa, and Prioritization](agile/estimation-and-prioritization.md)
- [Agile Glossary (Epics, User Stories, Tasks)](agile/glossary.md)
- [Backlog / Board (GitHub Project)](https://github.com/orgs/DatumLex/projects/1/views/9?visibleFields=%5B%22Title%22%2C%22Assignees%22%2C%22Status%22%5D)
- [Definition of Ready](agile/definition-of-ready.md)
- [Definition of Done](agile/definition-of-done.md)
- [Product Owner Guide](agile/product-owner-guide.md)
- [Scrum Master Guide](agile/scrum-master-guide.md)
- [Team Permanence Rule](agile/team-permanence-rule.md)
- [Strike Register](agile/strike-register.md)

### Development
- [Development folder overview](development/README.md)
- [Developer Guide](development/developer-guide.md)
- [End-to-End Development Process](development/development-process.md)
- [Commit Standards](development/commit-standards.md)
- [Branch Standards](development/branch-standards.md)
- [QA Guide](development/qa-guide.md)

### Product
- [Product folder overview](product/README.md)
- [Product Vision](product/product-vision.md)
- [Client Alignment and Scope Decisions](product/client-alignment.md)
- [Personas and Primary Audiences](product/personas.md)
- [Product Roadmap](product/product-roadmap.md)
- [Market References](product/market-references.md)

### Architecture & Data
- [Technology Stack and Rationale](architecture/technology-stack.md)
- [Architecture folder overview](architecture/README.md)

### Design
- [Design folder overview](design/README.md)
- [Design Standards Guide](design/datumlex-design-guide.pdf)
- [Minimal Logo](design/datumlex-logo-minimalist.jpg)
- [Horizontal Logo](design/datumlex-logo-horizontal.jpg)

### Academic Deliverables
- [Presentation folder overview](presentation/README.md)
- [Sprint 1 presentation (Google Slides)](https://docs.google.com/presentation/d/15ZrHGEJONJXZg2ENUoq1YoI8AjIF6A7Wol1-tTPDVHM/edit?usp=sharing)

---

## 📌 About the Challenge

Legal professionals currently combine fragmented court portals and long lists of
decisions manually. DatumLex turns approved public judicial data into traceable
indicators, comparisons, and thesis evidence for legal strategy and client
communication. One shared dashboard serves lawyers, magistrates, and advisors;
student/exam features and case/deadline management are outside this delivery plan.
The [client alignment record](product/client-alignment.md) explains the decisions
from August 31 through September 15, 2026, including unresolved backlog mismatches.

## 📈 Sprint Objectives

### Sprint 1 — A deployed merit analytics foundation

Deliver a real DataJud → ETL → PostgreSQL Data Warehouse → API → dashboard
pipeline for TJDFT Civil Liability records from 2023 onward. Include an initial
evidenced merit indicator for appeal outcomes and the latest requested G1/G2
results where supported by source evidence and reconciled contracts; volume alone
is insufficient. DataJud is the only source. Deliver reviewed models and dictionary,
stack/scope rationale, API documentation, automated tests, static analysis, and a
Vercel frontend with Railway backend/database. This is the first usable increment,
not the full product MVP. Delivery is planned for **September 27, 2026**.

### Sprint 2 — Explainable intelligence across legal sources

Deepen the analysis by connecting TJDFT data to STJ jurisprudence, precedents,
and approved open doctrine, prioritizing BDJur. Preserve provenance and rights,
extract theses and grounds using NLP with supporting passages, and validate
quality with human review. Add methodology-backed precedent adherence, chamber/panel
divergence, and temporal trends, keeping uncertainty and unavailable data explicit.

### Sprint 3 — Reproducible reports and professional workflows

Deliver reproducible PDF and XLSX exports and grounded, cited narrative drafts
that users review before export. Extend validated analytics to Consumer Law and
Contracts and improve workflows for lawyers, magistrates, and judicial advisors.
The final product must explain the evidenced theses behind outcomes using the
cross-source/NLP foundation, not merely present counts. Sprint 2 and 3 dates remain
subject to team planning; none are invented here.

See the [roadmap](product/product-roadmap.md) for delivery evidence and the
[user-story catalog](agile/user-stories.md) for all 42 stories, current priorities,
and planned sprints. Planning Poker uses the numeric Project column **`estimativa`**
on user stories only, with **1, 2, 3, 5, 8, 13, 21** story points. Tasks and epics
are not scored; blank means not yet estimated. See the
[estimation and prioritization agreement](agile/estimation-and-prioritization.md).
