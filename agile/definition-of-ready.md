# ✅ Definition of Ready (DoR) — DatumLex

The **Definition of Ready** is a checklist that every User Story must satisfy before it can be pulled into a Sprint. It is not part of the Scrum Guide, but the LegacyTech team adopts it to avoid starting development on stories that are still ambiguous.

This checklist is **fixed for the whole team** — it does not change per sprint. What changes is the content filled in for each User Story (see `agile/sprint-<n>-user-stories.md` for applied examples).

A User Story is considered **Ready** when all items below are checked:

## 📋 Checklist

- [ ] **Business rules detailed** — the rules governing the behavior are written out explicitly (e.g. validation rules, constraints, what's mandatory vs. optional).
- [ ] **Data defined** — every data element involved has a type, source, and validation rule specified (e.g. for ETL stories: source field, target field, expected format, null handling).
- [ ] **Confirmation, error, and warning messages defined** — user-facing feedback (success message, error message, warning) is written out.
- [ ] **UI prototype or wireframe attached** — for stories that touch the dashboard/UI. *(Not applicable to pure ETL/backend stories — see note below.)*
- [ ] **Acceptance criteria written** — at least one Gherkin-style scenario (`Dado / Quando / Então`) describing expected behavior.
- [ ] **Dependencies identified** — any blocking story, external API, or data source the story depends on is called out, and is either resolved or explicitly accepted as a known risk.
- [ ] **Estimated** — the team has estimated the story (story points or T-shirt size) in Planning.
- [ ] **Testability confirmed** — the team understands how the story will be tested (unit, integration, or system-level) before development starts.
- [ ] **Validated by the Product Owner** — Pedro (P.O.) has reviewed and approved the story content.

## 📝 Notes for DatumLex specifically

Because the project has two very different kinds of work — **ETL/Data Warehouse** and **Web Dashboard** — not every checklist item applies the same way to every story:

| Item | ETL / Data Warehouse story | Dashboard / UI story |
|---|---|---|
| Business rules | Transformation and cleaning rules | Business rules for the screen/feature |
| Data defined | Source schema, target dimensional model, data types | Fields shown, filters, data source (which fact/dimension tables) |
| Messages | Pipeline failure/success logging conventions | User-facing confirmation/error/warning text |
| UI prototype | Not applicable | Required |
| Acceptance criteria | Data quality/transformation scenarios | User-interaction scenarios |

A story is **not** pulled into the sprint until every applicable item above is checked. If an item genuinely doesn't apply (e.g. UI prototype for a pure ETL job), it should be marked as N/A explicitly rather than skipped silently.
