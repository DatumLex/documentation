# User Stories, Priorities, and Planned Sprints — DatumLex

## Snapshot and reading guide

Snapshot reviewed on **2026-09-15** against the live [GitHub Project](https://github.com/orgs/DatumLex/projects/1)
and `datumlex-core` issue bodies. Includes all **42 existing user stories**:
27 planned for Sprint 1, 9 for Sprint 2, and 6 for Sprint 3. Technical/enabler
stories are included for complete traceability; they are not verbatim client requests.
Each linked issue remains authoritative for full acceptance criteria and dependencies.

**Priority** below is the story's current Project value, not its child tasks' priority
and not a new reprioritization. **Planned delivery** is not a completion claim.
Current story priorities are heavily concentrated in High; review them using the
[minimum-goal prioritization policy](estimation-and-prioritization.md#priority-high-medium-low),
without assuming that every test or safety criterion makes an entire feature High.

The numeric Project field **`estimativa`** is used only on stories. No team Planning
Poker session is evidenced by this snapshot, so no invented point values are shown.
All estimates below remain pending team consensus; tasks and epics do not receive
points. See the [estimation agreement](estimation-and-prioritization.md).

## Client outcomes and delivery scope

See [client alignment](../product/client-alignment.md) and the [roadmap](../product/product-roadmap.md)
for the dated requirement history, professional audience, safeguards, and sprint
objectives. DataJud is the only Sprint 1 source; cross-source/NLP work is Sprint 2;
exports, grounded narratives, subject expansion, and professional refinement are Sprint 3.

## Sprint 1

| Story / issue | User need and value | Current Priority | Planned delivery | estimativa (SP) |
|---|---|---|---|---|
| [US-01 — Validate DataJud Access and Merit Feasibility (#3)](https://github.com/DatumLex/datumlex-core/issues/3) | As the data team, I want to validate access and actual outcome evidence, so that the merit indicator is traceable. | High | Sprint 1 | Pending |
| [US-02 — Document Stack, Architecture, and Scope Rationale (#4)](https://github.com/DatumLex/datumlex-core/issues/4) | As a team member, I want one consolidated technical decision document, so that I can understand and reproduce the solution. | High | Sprint 1 | Pending |
| [US-03 — Define Sprint 1 Scope and Metric Methodology (#5)](https://github.com/DatumLex/datumlex-core/issues/5) | As the PO, I want an explicit scope and metric specification, so that the team implements consistent analytics. | High | Sprint 1 | Pending |
| [US-04 — Produce and Validate the Conceptual and Dimensional Model (#6)](https://github.com/DatumLex/datumlex-core/issues/6) | As a data engineer, I want a conceptual DW model with explicit grain, so that the model represents merit analysis correctly. | High | Sprint 1 | Pending |
| [US-05 — Produce Logical and Physical DW Models (#7)](https://github.com/DatumLex/datumlex-core/issues/7) | As a data engineer, I want detailed logical and physical models, so that the DW can be implemented with data integrity. | High | Sprint 1 | Pending |
| [US-06 — Complete the Data Dictionary and Validate Modeling Artifacts (#8)](https://github.com/DatumLex/datumlex-core/issues/8) | As a team member, I want a complete dictionary and validated modeling package, so that implementation has unambiguous data definitions. | High | Sprint 1 | Pending |
| [US-07 — Extract Real DataJud Records (#10)](https://github.com/DatumLex/datumlex-core/issues/10) | As a data engineer, I want a repeatable extraction for the selected scope, so that real source data feeds the pipeline. | High | Sprint 1 | Pending |
| [US-08 — Transform Data and Classify Appeal Outcomes (#11)](https://github.com/DatumLex/datumlex-core/issues/11) | As a data engineer, I want deterministic outcome classification and normalized records, so that merit analytics is based on explicit source evidence. | High | Sprint 1 | Pending |
| [US-09 — Load and Reconcile the Data Warehouse (#12)](https://github.com/DatumLex/datumlex-core/issues/12) | As a data engineer, I want an idempotent PostgreSQL DW load, so that the API queries reliable real data. | High | Sprint 1 | Pending |
| [US-10 — Expose Merit Indicator Metrics (#14)](https://github.com/DatumLex/datumlex-core/issues/14) | As a frontend developer, I want an API for the three merit cards, so that the dashboard shows consistent real-data analytics. | High | Sprint 1 | Pending |
| [US-11 — Expose Granted versus Denied Distribution (#15)](https://github.com/DatumLex/datumlex-core/issues/15) | As a frontend developer, I want a filtered outcome distribution endpoint, so that the chart reflects real appeal outcomes. | High | Sprint 1 | Pending |
| [US-12 — Deploy the Backend on Railway (#16)](https://github.com/DatumLex/datumlex-core/issues/16) | As a team member, I want the backend deployed on Railway, so that the Vercel frontend can query the real DW. | High | Sprint 1 | Pending |
| [US-13 — Display Real Merit Indicator Cards (#18)](https://github.com/DatumLex/datumlex-core/issues/18) | As a legal analyst, I want three real-data indicator cards, so that I can understand appeal outcomes in the selected scope. | High | Sprint 1 | Pending |
| [US-14 — Display the Granted versus Denied Chart (#19)](https://github.com/DatumLex/datumlex-core/issues/19) | As a legal analyst, I want the appeal-outcome chart from the merit mockup, so that I can compare outcomes visually. | High | Sprint 1 | Pending |
| [US-15 — Implement the Dashboard Filter Bar (#20)](https://github.com/DatumLex/datumlex-core/issues/20) | As a legal analyst, I want working period and outcome filters, so that I can explore the available first-sprint scope. | High | Sprint 1 | Pending |
| [US-16 — Integrate the Dashboard with Real Data (#21)](https://github.com/DatumLex/datumlex-core/issues/21) | As a team member, I want the mockup implemented as a working dashboard, so that the complete pipeline is demonstrable. | High | Sprint 1 | Pending |
| [US-17 — Provision PostgreSQL on Railway (#23)](https://github.com/DatumLex/datumlex-core/issues/23) | As a DevOps engineer, I want a Railway PostgreSQL environment, so that the approved DW is available to the backend. | High | Sprint 1 | Pending |
| [US-18 — Deploy the Dashboard on Vercel (#24)](https://github.com/DatumLex/datumlex-core/issues/24) | As a stakeholder, I want the first-sprint dashboard accessible by link, so that I can evaluate the working product. | High | Sprint 1 | Pending |
| [US-19 — Standardize Local Development (#25)](https://github.com/DatumLex/datumlex-core/issues/25) | As a developer, I want a reproducible local environment, so that I can run the solution and tests consistently. | High | Sprint 1 | Pending |
| [US-20 — Document the Approved Color Palette (#27)](https://github.com/DatumLex/datumlex-core/issues/27) | As a designer, I want documented color tokens from the approved mockup, so that the dashboard and presentation remain consistent. | High | Sprint 1 | Pending |
| [US-21 — Document and Apply the Dashboard Style Guide (#28)](https://github.com/DatumLex/datumlex-core/issues/28) | As a designer, I want a concise style guide for the supplied mockup, so that the implementation stays visually consistent. | High | Sprint 1 | Pending |
| [US-22 — Organize Approved Brand Assets (#29)](https://github.com/DatumLex/datumlex-core/issues/29) | As a team member, I want a lightweight repository brand center, so that I can reuse approved logo assets in the product and presentation. | High | Sprint 1 | Pending |
| [US-23 — Document the Analytics API (#74)](https://github.com/DatumLex/datumlex-core/issues/74) | As an API consumer, I want an accurate API reference with examples, so that I can integrate and test the dashboard reliably. | Unset (recommend High) | Sprint 1 (issue scope; Project unset) | Pending |
| [US-24 — Automate Unit and Integration Tests (#78)](https://github.com/DatumLex/datumlex-core/issues/78) | As a data engineer, I want automated checks for transformations and persistence, so that data and metrics remain correct as code changes. | High | Sprint 1 | Pending |
| [US-25 — Automate Functional System API Tests (#81)](https://github.com/DatumLex/datumlex-core/issues/81) | As an API consumer, I want automated black-box tests against the running backend, so that API behavior matches documented analytics. | High | Sprint 1 | Pending |
| [US-26 — Automate Functional System UI Tests (#84)](https://github.com/DatumLex/datumlex-core/issues/84) | As a stakeholder, I want automated browser tests of the dashboard journey, so that the released UI behaves as expected. | High | Sprint 1 | Pending |
| [US-27 — Run Static Analysis and Automated Tests in CI (#87)](https://github.com/DatumLex/datumlex-core/issues/87) | As a developer, I want repeatable CI quality checks, so that regressions are detected before release. | High | Sprint 1 | Pending |

## Sprint 2

| Story / issue | User need and value | Current Priority | Planned delivery | estimativa (SP) |
|---|---|---|---|---|
| [US-28 — Integrate STJ Jurisprudence and Precedents (#97)](https://github.com/DatumLex/datumlex-core/issues/97) | As a legal professional, I want to search and retrieve relevant STJ decisions and precedents alongside TJDFT data, so that I can verify whether local decisions align with superior-court authority. | High | Sprint 2 | Pending |
| [US-29 — Integrate BDJur and Approved Open Doctrine (#100)](https://github.com/DatumLex/datumlex-core/issues/100) | As a lawyer or magistrate, I want to find open doctrine related to the researched legal issue, so that the analytical result includes authoritative context beyond court counts. | High | Sprint 2 | Pending |
| [US-30 — Normalize and Link Cross-Source Legal Records (#103)](https://github.com/DatumLex/datumlex-core/issues/103) | As a legal researcher, I want to navigate from an analytical result to related TJDFT, STJ, precedent, and doctrine records, so that I can audit why sources were considered related. | High | Sprint 2 | Pending |
| [US-31 — Extract Legal Grounds and Thesis Candidates (#107)](https://github.com/DatumLex/datumlex-core/issues/107) | As a litigating lawyer, I want to see the grounds and theses associated with favorable and unfavorable outcomes, so that I can understand what drives the observed result. | High | Sprint 2 | Pending |
| [US-32 — Validate NLP Quality with Human Review (#110)](https://github.com/DatumLex/datumlex-core/issues/110) | As a product owner and legal reviewer, I want to measure and review extraction quality, so that the product only presents NLP results at an understood reliability level. | High | Sprint 2 | Pending |
| [US-33 — Expose Explainable NLP Results (#113)](https://github.com/DatumLex/datumlex-core/issues/113) | As a lawyer or magistrate, I want to inspect extracted theses with confidence and supporting evidence, so that I can verify the result before relying on it. | High | Sprint 2 | Pending |
| [US-34 — Measure Adherence to Superior-Court Precedents (#117)](https://github.com/DatumLex/datumlex-core/issues/117) | As a litigating lawyer or judicial advisor, I want to compare TJDFT decisions with relevant STJ precedents, so that I can assess whether local decisions follow superior-court guidance. | High | Sprint 2 | Pending |
| [US-35 — Identify Divergent Understandings (#120)](https://github.com/DatumLex/datumlex-core/issues/120) | As a lawyer or magistrate, I want to compare how TJDFT chambers or panels treat the same thesis, so that I can detect legally relevant disagreement before choosing a strategy. | High | Sprint 2 | Pending |
| [US-36 — Explore Temporal Trends and Main Theses (#123)](https://github.com/DatumLex/datumlex-core/issues/123) | As a legal professional, I want to see how outcomes and legal theses evolve over time, so that I can identify changes in legal understanding without mistaking them for predictions. | Medium | Sprint 2 | Pending |

## Sprint 3

| Story / issue | User need and value | Current Priority | Planned delivery | estimativa (SP) |
|---|---|---|---|---|
| [US-37 — Export a Reproducible PDF Report (#127)](https://github.com/DatumLex/datumlex-core/issues/127) | As a lawyer, I want to export the current analysis as a polished PDF, so that I can attach evidence-based analytics to an opinion or present it to a client. | High | Sprint 3 | Pending |
| [US-38 — Export Research Data as a Spreadsheet (#130)](https://github.com/DatumLex/datumlex-core/issues/130) | As a researcher or legal operations professional, I want to download the filtered evidence and metadata as a spreadsheet, so that I can audit and continue analysis outside the platform. | Medium | Sprint 3 | Pending |
| [US-39 — Generate Grounded Legal Analysis Narratives (#133)](https://github.com/DatumLex/datumlex-core/issues/133) | As a litigating lawyer, I want to generate a cited narrative from the selected research, so that I can evaluate appeal or settlement strategy without manually summarizing every result. | High | Sprint 3 | Pending |
| [US-40 — Add Consumer Law Analytics (#137)](https://github.com/DatumLex/datumlex-core/issues/137) | As a lawyer or judicial advisor, I want to analyze Consumer Law outcomes and theses, so that I can use DatumLex on a high-volume professional practice area. | Medium | Sprint 3 | Pending |
| [US-41 — Add Contracts Analytics (#140)](https://github.com/DatumLex/datumlex-core/issues/140) | As a lawyer or judicial advisor, I want to analyze contract disputes, outcomes, and theses, so that I can compare contractual legal reasoning using traceable evidence. | Medium | Sprint 3 | Pending |
| [US-42 — Optimize Professional Research Workflows (#143)](https://github.com/DatumLex/datumlex-core/issues/143) | As a lawyer, magistrate, or judicial advisor, I want to move from a question to evidence, comparison, and a reviewable report efficiently, so that DatumLex supports real legal decision-making and client communication. | High | Sprint 3 | Pending |

## Gaps and maintenance

- **US-23 / #74:** Sprint and Priority are blank in the Project. The issue explicitly
  specifies Sprint 1. High is recommended because the API contract/reference enables
  integration and tests; it has not been written to the Project by this review.
- **G1/G2:** the latest client request and US-14's replacement of the older G1/G2
  chart need reconciliation. See the [alignment record](../product/client-alignment.md#reconciliation-items-identified-on-september-15).
- **NLP source text:** make TJDFT/STJ text retrieval and coverage dependencies
  explicit during refinement; DataJud metadata alone does not establish them.
- Story-point totals and historical velocity cannot be asserted while estimates
  are pending. Sprint 1's deadline is September 27; Sprint 2/3 dates are not specified here.

When approved scope, priority, or planned delivery changes, update the Project and
refresh this dated catalog through a reviewed PR. Preserve release snapshots for
historical comparison. Do not copy task priorities into stories or infer completion
from elapsed dates. This review changes no issue status, assignee, date, Sprint,
Priority, or acceptance criterion.
