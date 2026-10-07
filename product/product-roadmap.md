# Product Roadmap — DatumLex

## Product goal and planning basis

Enable lawyers, magistrates, and judicial advisors to move from observed outcomes
to the legal theses, precedents, and evidence behind them. Depth and cross-source
analysis precede broader coverage. This plan reflects [client alignment through
September 25, 2026](client-alignment.md), the October 7 refinement and the [45-story catalog](../agile/user-stories.md).
Assignments are planned delivery, not completion claims. The [Project](https://github.com/orgs/DatumLex/projects/1)
holds live Priority, Sprint, `Estimate`, ownership, dates, and status.

## Sprint objectives

### Sprint 1 — A deployed merit analytics foundation

Deliver a real DataJud → ETL → PostgreSQL Data Warehouse → API → dashboard
pipeline for TJDFT Civil Liability records from 2023 onward. Include an initial
evidenced merit indicator for appeal outcomes and the latest requested G1/G2
results where supported by source evidence and reconciled contracts; volume alone
is insufficient. DataJud is the only source. Deliver reviewed models and dictionary,
stack/scope rationale, API documentation, automated tests, static analysis, and a
deployment originally planned as Vercel frontend with Railway backend/database.
The September 22 hosting constraint and current environment must be reconciled
through Sprint 2 baseline task [#169](https://github.com/DatumLex/datumlex-core/issues/169). This is the first usable increment,
not the full product MVP. Delivery is planned for **September 27, 2026**.

### Sprint 2 — Explainable intelligence across legal sources

Deepen Civil Liability analysis with real TJDFT decision text, STJ jurisprudence
and precedents, and an initial approved BDJur doctrine corpus. Preserve source
rights, provenance and actual coverage. Extract theses and grounds with exact
supporting passages; validate NLP through a human-reviewed benchmark and agreed
quality thresholds. Show explainable rankings and **Ver fontes** evidence cards.

Deliver methodology-backed adherence, with possible divergence (Should Have)
and temporal exploration (Could Have) reviewed against team capacity. Add dynamic
multiselect filters for courts, outcomes and legal sources: TJDFT alone and
TJDFT + STJ must work in the same dashboard. Export the captured analysis to
**PDF in Sprint 2**, including clickable original-source links, coverage, counting
unit, NLP criteria and limitations. Reconcile source records, API, dashboard and
PDF in a deployed increment. See the [Sprint 2 plan](../agile/sprint-2-plan.md) for all stories, tasks,
dependencies and the team planning agenda.

### Sprint 3 — Exports, grounded narratives and expanded subjects

Deliver XLSX exports and grounded, cited narrative drafts that users review
before export, reusing the Sprint 2 PDF and analytical context. Extend validated
analytics to Consumer Law and Contracts and improve professional workflows.
The final product must explain evidenced theses behind outcomes using the
cross-source/NLP foundation. Sprint 2 and 3 dates remain subject to team planning.

## Delivery evidence by sprint

| Sprint | Planned stories | Evidence required for the integrated outcome |
|---|---|---|
| 1 | US-01–US-27 | Conceptual/logical/physical models and dictionary; stack and court rationale; reproducible real DataJud run; reviewed classification and API; approved dashboard; unit/integration/system API/UI tests; static analysis; deployment and smoke evidence; release documentation. |
| 2 | US-28–US-37, US-43–US-45 | Source/text access, coverage and rights; reviewed models and matching; human-reviewed NLP benchmark/thresholds; source-linked rankings and metrics; multiselect contract and tests; PDF rendering/source-link checks; source/API/UI/PDF reconciliation and deployed release evidence. |
| 3 | US-38–US-42 | XLSX validation and safe spreadsheet content; grounded-generation/citation evaluation and human review; integration with the Sprint 2 context/PDF; validated new subject boundaries and professional journeys. |

## Acceptance boundaries and unresolved alignment

- Unknown, partial, conflicting, and unavailable outcomes stay explicit. Binary
  grant rate is `granted / (granted + denied)` with coverage disclosed. An Outcome
  chart filter must not silently turn the rate card into 100%.
- Resolve the [G1/G2 mismatch](client-alignment.md#reconciliation-items-identified-on-september-15)
  before claiming that comparison is delivered. If DataJud cannot support a metric,
  record the blocker and obtain a scope decision; never fabricate evidence or
  silently add sources to Sprint 1.
- Sprint 2 text access is not proven by Sprint 1 metadata. Source candidates and
  research notes do not establish production coverage or reuse rights.
- AI summarizes retrieved, versioned evidence with citations and review. It does
  not promise outcomes or replace legal judgment.
- Exports alone cannot compensate for unfinished cross-source integration and
  thesis extraction: those remain indispensable at the end of Sprint 3.

## Scope and capacity controls

Use [Planning Poker](../agile/estimation-and-prioritization.md) on stories only.
Points include necessary quality work, do not convert to days, and do not override
dependency sequencing. Preserve Sprint 1's September 14 lower date boundary,
September 17–18 modeling concentration, and September 24–25 integration/deploy
concentration when assessing risk. The October 7 refinement preserves Sprint 1 history and leaves Sprint 2
assignment, dates and capacity selection for team planning.

Keep one professional dashboard. Student/exam features, role-specific portals,
case/deadline management, and guaranteed-result prediction are outside scope.
Individual case search is secondary to analytics. More courts or source candidates
require explicit decisions. The PO and delivery team revise scope with evidence;
a forecast does not waive DoD or establish stakeholder acceptance.

## Related documents

- [Product vision](product-vision.md)
- [Personas](personas.md)
- [Client alignment](client-alignment.md)
- [Story catalog](../agile/user-stories.md)
- [Definition of Done](../agile/definition-of-done.md)
