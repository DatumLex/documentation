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
- [MoSCoW and Planning Poker Guide](agile/moscow-and-planning-poker.md)
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

The table uses **MoSCoW**, a prioritization technique, for the product delivered
across **Sprints 1–3**. It is ordered by **Must Have → Should Have → Could Have**;
excluded capabilities are recorded under **Won't Have this time** below.
The planned sprint remains the target increment. A release-level Must Have does
not have to be implemented in Sprint 1.

| ID | MoSCoW priority | User story | Estimate (SP) | Planned sprint |
|---|---|---|---|---|
| US-01 | Must Have | As a legal professional, I want to open one shared dashboard by link and explore real TJDFT Civil Liability data from 2023 onward, so that I can research the agreed scope in one place. | Pending | Sprint 1 |
| US-02 | Must Have | As a legal professional, I want to filter the analysis by period and appeal outcome while seeing the fixed court and subject, so that the indicators reflect the scope I am researching. | Pending | Sprint 1 |
| US-03 | Must Have | As a lawyer or judicial advisor, I want to see analyzed appeal counts and evidenced granted/denied indicators, including the grant rate, so that I can understand historical merits within the selected scope. | Pending | Sprint 1 |
| US-04 | Must Have | As a legal professional, I want to compare granted and denied appeals in a chart, so that I can interpret the distribution of evidenced outcomes at a glance. | Pending | Sprint 1 |
| US-06 | Must Have | As a legal professional, I want to see the source, update date, calculation method, denominator, and coverage of the indicators, so that I can interpret and cite them in context. | Pending | Sprint 1 |
| US-07 | Must Have | As a legal professional, I want unknown outcomes, unavailable data, empty results, and loading errors to be clearly identified, so that I do not mistake missing evidence for a denied appeal or a real zero. | Pending | Sprint 1 |
| US-08 | Must Have | As a lawyer or magistrate, I want to consult relevant STJ jurisprudence and precedents alongside TJDFT analysis, so that I can examine the superior-court context for the legal issue. | Pending | Sprint 2 |
| US-09 | Must Have | As a lawyer or magistrate, I want to find related open doctrine from BDJur and other approved sources with attribution and source links, so that I can connect the observed decisions to legal scholarship. | Pending | Sprint 2 |
| US-10 | Must Have | As a legal professional, I want to navigate from an analytical result to related TJDFT, STJ, precedent, and doctrine records and understand why they were linked, so that I can audit the evidence. | Pending | Sprint 2 |
| US-11 | Must Have | As a litigating lawyer, I want to inspect extracted theses and grounds associated with outcomes, with supporting passages, confidence, and review information, so that I can verify the legal reasoning behind the numbers. | Pending | Sprint 2 |
| US-12 | Must Have | As a lawyer or judicial advisor, I want to see how TJDFT decisions adhere to relevant STJ precedents, with methodology and supporting decisions, so that I can assess alignment with superior-court guidance. | Pending | Sprint 2 |
| US-15 | Must Have | As a lawyer, I want to export the selected analysis as a formatted PDF with filters, indicators, charts, methodology, sources, and update date, so that I can present reproducible evidence in an opinion or client meeting. | Pending | Sprint 3 |
| US-05 | Should Have | As a lawyer or magistrate, I want to compare first- and second-instance merit results where evidence supports the comparison, so that I can distinguish initial judgments from appeal outcomes. | Pending | Sprint 1 — alignment pending* |
| US-13 | Should Have | As a lawyer or magistrate, I want to compare how chambers or panels treat the same thesis, with comparable samples and limitations, so that I can identify evidenced divergences in legal understanding. | Pending | Sprint 2 |
| US-16 | Should Have | As a legal operations professional, I want to export filtered evidence and analytical metadata to XLSX, so that I can audit and continue the research in a spreadsheet. | Pending | Sprint 3 |
| US-17 | Should Have | As a litigating lawyer, I want an AI-assisted narrative grounded in the selected indicators and retrieved decisions, with citations and my review before export, so that I can support strategy discussions and explain findings to clients. | Pending | Sprint 3 |
| US-18 | Should Have | As a lawyer or judicial advisor, I want to analyze Consumer Law outcomes and theses using the same traceable analytics, so that I can investigate this additional practice area. | Pending | Sprint 3 |
| US-19 | Should Have | As a lawyer or judicial advisor, I want to analyze contractual disputes, outcomes, and theses using the same traceable analytics, so that I can compare legal reasoning in Contracts. | Pending | Sprint 3 |
| US-14 | Could Have | As a legal professional, I want to explore how outcomes and theses evolve over time, with coverage and methodology changes explained, so that I can identify historical trends. | Pending | Sprint 2 |
| US-20 | Could Have | As a lawyer, magistrate, or judicial advisor, I want fewer repeated steps and clearer transitions between filters, evidence, and report review, so that recurring research is more convenient. | Pending | Sprint 3 |

### MoSCoW criteria

| Priority | Delivery decision |
|---|---|
| Must Have | Required for a viable, trustworthy release. Without it, the minimum product goal is not met. |
| Should Have | Important and planned, but a workable temporary alternative exists. Defer only through an explicit scope decision. |
| Could Have | Useful enhancement with a smaller impact if deferred; the first scope to reconsider when capacity is tight. |
| Won't Have this time | Explicitly excluded from Sprints 1–3; no delivery sprint is assigned. This is not a promise of a future feature. |

Source: [Agile Business Consortium — MoSCoW prioritization](https://www.agilebusiness.org/resource/what-is-moscow-prioritization/).

### Planning Poker criteria

**MoSCoW defines delivery importance; Planning Poker estimates relative effort.**
The **Estimate (SP)** column applies Planning Poker to each product user story.
SP means story points and includes complexity, uncertainty, and the work needed
to meet the Definition of Done. Points are not hours or a delivery guarantee.

| Scale or state | How to use it |
|---|---|
| 1, 2, 3, 5, 8 | Compare increasing effort with reference stories agreed by the team. |
| 13 | Discuss splitting the story into smaller useful outcomes. |
| 21 | Coarse estimate for refinement; split before selecting it for a sprint. |
| Pending | Team estimation has not been recorded. It does not mean zero effort. |

The PO clarifies the story and acceptance criteria. Delivery contributors choose
cards privately, reveal them together, discuss differences, and vote again until
they agree. Record the result and session evidence; a proposed number is not team
consensus. Use `?` in discussion when more information is needed and keep the
estimate pending. MoSCoW categories do not determine point values.

All 20 estimates are initially **Pending** until the team performs this process.
See the [MoSCoW and Planning Poker guide](agile/moscow-and-planning-poker.md) for
examples, responsibilities, and recording rules, and the
[Planning Poker reference](https://www.mountaingoatsoftware.com/agile/story-points/planning-poker).

### How this applies to DatumLex

- **Must Have:** the shared real-data dashboard, filters, initial merit metrics
  and outcome chart, transparent evidence, STJ/open-doctrine integration,
  explainable theses, precedent adherence, and reproducible PDF reporting deliver
  the core client value. US-04's chart is part of the visual analytics baseline
  and supports the charts required in US-15's PDF.
- **Should Have:** G1/G2 comparison, chamber/panel divergence, XLSX, AI-assisted
  narratives, and Consumer Law/Contracts expansion add substantial value. The
  core appeal analysis remains useful while G1/G2 is reconciled; professionals
  can inspect source evidence and write their own narrative, and Civil Liability
  remains the initial subject. These alternatives involve a real loss of convenience
  or coverage, which is why these features remain planned.
- **Could Have:** US-14's temporal exploration and US-20's fewer repeated steps
  improve the experience after core outcome/thesis analysis works. Essential
  navigation, accessibility, source dates, evidence, and human review remain required.

The GitHub Project now uses the same **Must Have, Should Have, Could Have, and
Won't Have this time** options in its **Priority** field. The
[prioritization policy](agile/estimation-and-prioritization.md#priority-moscow)
maps implementation work by capability and dependency, not by matching US numbers.
Supporting documentation, environment standardization, and additional automation
can be Should Have when an equivalent temporary approach preserves the required
outcome. Planned sprints and client acceptance criteria remain unchanged.
The PO and team review capacity and dependencies at refinement; any change to an
agreed client delivery must be explicitly reconciled. Required tests, privacy,
provenance, and quality criteria apply to every delivered feature. A Must Have
must include its necessary dependencies in the protected scope.

Review the balance using **estimated effort**, not the number of rows. Twelve
Must Have stories out of twenty do not prove that only 60% of the effort is
mandatory. Team estimates are still needed to assess capacity and leave room
for uncertainty; if the protected scope does not fit, renegotiate or split scope.

### Won't Have this time — Sprints 1–3

| Capability outside this delivery | Reason |
|---|---|
| Student learning paths, OAB or competitive-exam preparation | The agreed audience is lawyers, magistrates, and judicial advisors. |
| Case management, deadlines, and electronic filing | The product focuses on legal analytics and research. |
| Separate portals or complex permission tiers for each professional role | A shared dashboard with interactive filters meets the agreed access model. |

Guaranteed case-outcome prediction and replacing professional legal judgment
remain outside the product's purpose, not features deferred to a later sprint.

\* **US-05:** the latest client expectation is a Sprint 1 G1/G2 merit comparison.
Its metric, source feasibility, and chart acceptance criteria still need
[G1/G2 reconciliation](product/client-alignment.md#reconciliation-items-identified-on-september-15).
A second-instance record alone does not establish a linked appeal, reversal, or success.

Sprint 1 uses **DataJud only**. STJ, precedents, and approved open doctrine enter in
Sprint 2; PDF/XLSX, cited narratives, new subjects, and professional refinements
enter in Sprint 3. Source access and reuse rights must be validated. Missing
evidence stays **unknown/unavailable**, and historical patterns do not guarantee
future outcomes.

Operational story estimates remain in the Project's **`estimativa`** field.
README product estimates support refinement and do not add a second velocity
total. Because the two story catalogs have independent IDs and scopes, do not
copy points by US number or add their totals together; see the
[mapping and counting rules](agile/moscow-and-planning-poker.md#keep-the-readme-and-project-consistent).

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
