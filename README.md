# 📚 DatumLex — Documentation

Central documentation repository for **DatumLex** — an analytical platform (Data Warehouse + Web Dashboard) for consolidating and analyzing judicial decisions, jurisprudence, and academic doctrines.

> 💻 Source code: [datumlex-core](https://github.com/DatumLex/datumlex-core)
> 📋 Board / Backlog: [GitHub Project](https://github.com/orgs/DatumLex/projects/1/views/9?visibleFields=%5B%22Title%22%2C%22Assignees%22%2C%22Status%22%5D)
> 🎯 Client features: [Product Backlog](#product-backlog)

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

## Product Backlog

These user stories describe DatumLex's functions and their value to lawyers,
magistrates, and judicial advisors, based on the
[client direction](product/client-alignment.md) and [roadmap](product/product-roadmap.md).
The **US** IDs below identify this product backlog. Its numbering and priorities
are independent of the implementation stories in the GitHub Project; consult the
[implementation catalog](agile/user-stories.md) for engineering work.

The table is ordered by **High → Medium → Low**, using product value and the
minimum usable delivery as the criteria. Planned sprints are delivery forecasts.

| ID | Priority | User story | Planned sprint |
|---|---|---|---|
| US-01 | High | As a legal professional, I want to open one shared dashboard by link and explore real TJDFT Civil Liability data from 2023 onward, so that I can research the agreed scope in one place. | Sprint 1 |
| US-02 | High | As a legal professional, I want to filter the analysis by period and appeal outcome while seeing the fixed court and subject, so that the indicators reflect the scope I am researching. | Sprint 1 |
| US-03 | High | As a lawyer or judicial advisor, I want to see analyzed appeal counts and evidenced granted/denied indicators, including the grant rate, so that I can understand historical merits within the selected scope. | Sprint 1 |
| US-05 | High | As a lawyer or magistrate, I want to compare first- and second-instance merit results where evidence supports the comparison, so that I can distinguish initial judgments from appeal outcomes. | Sprint 1 — alignment pending* |
| US-06 | High | As a legal professional, I want to see the source, update date, calculation method, denominator, and coverage of the indicators, so that I can interpret and cite them in context. | Sprint 1 |
| US-07 | High | As a legal professional, I want unknown outcomes, unavailable data, empty results, and loading errors to be clearly identified, so that I do not mistake missing evidence for a denied appeal or a real zero. | Sprint 1 |
| US-08 | High | As a lawyer or magistrate, I want to consult relevant STJ jurisprudence and precedents alongside TJDFT analysis, so that I can examine the superior-court context for the legal issue. | Sprint 2 |
| US-09 | High | As a lawyer or magistrate, I want to find related open doctrine from BDJur and other approved sources with attribution and source links, so that I can connect the observed decisions to legal scholarship. | Sprint 2 |
| US-10 | High | As a legal professional, I want to navigate from an analytical result to related TJDFT, STJ, precedent, and doctrine records and understand why they were linked, so that I can audit the evidence. | Sprint 2 |
| US-11 | High | As a litigating lawyer, I want to inspect extracted theses and grounds associated with outcomes, with supporting passages, confidence, and review information, so that I can verify the legal reasoning behind the numbers. | Sprint 2 |
| US-12 | High | As a lawyer or judicial advisor, I want to see how TJDFT decisions adhere to relevant STJ precedents, with methodology and supporting decisions, so that I can assess alignment with superior-court guidance. | Sprint 2 |
| US-15 | High | As a lawyer, I want to export the selected analysis as a formatted PDF with filters, indicators, charts, methodology, sources, and update date, so that I can present reproducible evidence in an opinion or client meeting. | Sprint 3 |
| US-04 | Medium | As a legal professional, I want to compare granted and denied appeals in a chart, so that I can interpret the distribution of evidenced outcomes at a glance. | Sprint 1 |
| US-13 | Medium | As a lawyer or magistrate, I want to compare how chambers or panels treat the same thesis, with comparable samples and limitations, so that I can identify evidenced divergences in legal understanding. | Sprint 2 |
| US-14 | Medium | As a legal professional, I want to explore how outcomes and theses evolve over time, with coverage and methodology changes explained, so that I can identify historical trends. | Sprint 2 |
| US-16 | Medium | As a legal operations professional, I want to export filtered evidence and analytical metadata to XLSX, so that I can audit and continue the research in a spreadsheet. | Sprint 3 |
| US-17 | Medium | As a litigating lawyer, I want an AI-assisted narrative grounded in the selected indicators and retrieved decisions, with citations and my review before export, so that I can support strategy discussions and explain findings to clients. | Sprint 3 |
| US-18 | Medium | As a lawyer or judicial advisor, I want to analyze Consumer Law outcomes and theses using the same traceable analytics, so that I can investigate this additional practice area. | Sprint 3 |
| US-19 | Medium | As a lawyer or judicial advisor, I want to analyze contractual disputes, outcomes, and theses using the same traceable analytics, so that I can compare legal reasoning in Contracts. | Sprint 3 |
| US-20 | Low | As a lawyer, magistrate, or judicial advisor, I want fewer repeated steps and clearer transitions between filters, evidence, and report review, so that recurring research is more convenient. | Sprint 3 |

### Priority criteria

| Priority | Meaning |
|---|---|
| High | Essential to deliver useful, trustworthy merit and thesis analytics: a working dashboard, filters, evidenced outcomes, source transparency, cross-source research, precedent adherence, and a reproducible report. |
| Medium | Important analytical depth or additional value after the core: graphical outcome comparison, divergence and temporal views, XLSX, assisted narratives, and Consumer Law/Contracts expansion. |
| Low | Convenience refinements that can be deferred while the complete professional research journey remains usable. |

US-20 covers fewer repeated steps and clearer transitions in an already working
journey. Essential navigation, accessibility, evidence, and report review remain
part of the core features at every priority. Deferring convenience must not remove
quality safeguards. A High item may belong to a later sprint when it depends on
earlier capabilities; priority and delivery sequence are different decisions.

\* **US-05:** the latest client expectation is a Sprint 1 G1/G2 merit comparison.
Its metric, source feasibility, and chart acceptance criteria still need
[G1/G2 reconciliation](product/client-alignment.md#reconciliation-items-identified-on-september-15).
A second-instance record alone does not establish a linked appeal, reversal, or success.

Sprint 1 uses **DataJud only**. STJ, precedents, and approved open doctrine enter in
Sprint 2; PDF/XLSX, cited narratives, new subjects, and professional refinements
enter in Sprint 3. Source access and reuse rights must be validated. Missing
evidence stays **unknown/unavailable**, and historical patterns do not guarantee
future outcomes.

Team Planning Poker estimates remain in the Project's **`estimativa`** field.
This product summary does not add a second story-point total.

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
