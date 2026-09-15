# Product Roadmap — DatumLex

## Product goal and planning basis

Enable lawyers, magistrates, and judicial advisors to move from observed outcomes
to the legal theses, precedents, and evidence behind them. Depth and cross-source
analysis precede broader coverage. This plan reflects [client alignment through
September 15, 2026](client-alignment.md) and the [42-story catalog](../agile/user-stories.md).
Assignments are planned delivery, not completion claims. The [Project](https://github.com/orgs/DatumLex/projects/1)
holds live Priority, Sprint, `estimativa`, ownership, dates, and status.

## Sprint objectives

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

## Delivery evidence by sprint

| Sprint | Planned stories | Evidence required for the integrated outcome |
|---|---|---|
| 1 | US-01–US-27 | Conceptual/logical/physical models and dictionary; stack and court rationale; reproducible real DataJud run; reviewed classification and API; approved dashboard; unit/integration/system API/UI tests; static analysis; deployment and smoke evidence; release documentation. |
| 2 | US-28–US-36 | Verified source access/coverage/rights; ingestion and provenance; matching validation; versioned annotations and human-reviewed benchmark; NLP release thresholds; reconciled aggregates and source drill-down. |
| 3 | US-37–US-42 | PDF rendering and XLSX validation; export/API reconciliation; safe spreadsheet content; grounded-generation and citation evaluation; human review; validated subject boundaries; professional usability/accessibility evidence. |

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
concentration when assessing risk. This documentation review does not reschedule
the board.

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
