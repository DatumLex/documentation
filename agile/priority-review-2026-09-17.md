# GitHub Project MoSCoW Review — September 17, 2026

## Scope and result

Reviewed **139 existing items** in the [DatumLex Project](https://github.com/orgs/DatumLex/projects/1):
13 epics, 42 implementation user stories, and 84 tasks. Compared current Project
values and issue scope with the [README product backlog](../README.md#product-backlog).
The team requested the same MoSCoW vocabulary and a review of excessive High usage.

The existing **Priority** field was retained. Its options changed from High,
Medium, and Low to **Must Have, Should Have, and Could Have**, preserving their
existing identities. **Won't Have this time** was added for explicit exclusions
from Sprints 1–3. No current item was moved to that category: no planned capability
was removed. Option descriptions explain the delivery decision.

Beyond renaming the options, **23 items were reclassified**: 14 tasks, 8 stories,
and 1 epic. Status, assignees, dates, Sprint, estimates, issue descriptions, and
acceptance criteria were not changed. The README product categories and planned
sprints were preserved. Existing engineering US IDs remain independent of README IDs.

## Before and after

| Item type | Before: High / Medium / Low / unset | After: Must / Should / Could / Won't |
|---|---|---|
| Epics (13) | 12 / 1 / 0 / 0 | 11 / 2 / 0 / 0 |
| User stories (42) | 37 / 4 / 0 / 1 | 32 / 7 / 3 / 0 |
| Tasks (84) | 60 / 21 / 3 / 0 | 54 / 23 / 7 / 0 |
| All items (139) | 109 / 26 / 3 / 1 | 97 / 32 / 10 / 0 |

| Task sprint | Must Have | Should Have | Could Have | Total |
|---|---|---|---|---|
| Sprint 1 | 39 | 12 | 3 | 54 |
| Sprint 2 | 14 | 2 | 2 | 18 |
| Sprint 3 | 1 | 9 | 2 | 12 |

Nine tasks left the highest category; three were promoted because they directly
provide required evidence or analytics. The net change is **60 High to 54 Must Have**.
Sprint 1 still contains many essential tasks because it establishes the real-data
pipeline, modeling, API, dashboard, deployment, and required quality baseline.
These counts measure items, not effort or capacity. Do not downgrade necessary
work merely to reach a category percentage; use team estimates to assess scope.

## Reclassifications beyond option renaming

Issue numbers below refer to `datumlex-core`, not README US numbers.

| Issue | Previous Priority | Current Priority | Reason |
|---|---|---|---|
| [#26 — Visual identity epic](https://github.com/DatumLex/datumlex-core/issues/26) | High | Should Have | Consolidation and reuse of an already approved identity support the core dashboard. |
| [#27 — Color palette story](https://github.com/DatumLex/datumlex-core/issues/27) | High | Should Have | Palette documentation has the approved mockup as a temporary reference. |
| [#28 — Style guide story](https://github.com/DatumLex/datumlex-core/issues/28) | High | Should Have | Reusable style guidance supports an existing dashboard design; required accessible behavior remains part of feature acceptance. |
| [#29 — Brand assets story](https://github.com/DatumLex/datumlex-core/issues/29) | High | Could Have | Asset organization and usage convenience can follow the approved usable assets. |
| [#43 — Extraction audit evidence](https://github.com/DatumLex/datumlex-core/issues/43) | Medium | Must Have | Traceable source evidence supports README US-06. |
| [#55 — Data-quality notes and states](https://github.com/DatumLex/datumlex-core/issues/55) | Medium | Must Have | Coverage and unknown/unavailable states directly implement README US-06 and US-07. |
| [#74 — Analytics API documentation story](https://github.com/DatumLex/datumlex-core/issues/74) | Unset | Must Have | The API contract and methods support integration and trustworthy core metrics. Sprint stays unset. |
| [#119 — Adherence metrics and drill-down](https://github.com/DatumLex/datumlex-core/issues/119) | Medium | Must Have | Delivers the precedent-adherence capability in README US-12. |
| [#120 — Divergence story](https://github.com/DatumLex/datumlex-core/issues/120) | High | Should Have | Matches README US-13. |
| [#121 — Divergence methodology and safeguards](https://github.com/DatumLex/datumlex-core/issues/121) | High | Should Have | Supports the Should Have divergence capability; its safeguards remain required when delivered. |
| [#123 — Temporal trends story](https://github.com/DatumLex/datumlex-core/issues/123) | Medium | Could Have | Matches README US-14; core thesis inspection remains Must Have elsewhere. |
| [#124 — Temporal aggregates](https://github.com/DatumLex/datumlex-core/issues/124) | Medium | Could Have | Implements the optional temporal exploration capability. |
| [#125 — Temporal exploration UI](https://github.com/DatumLex/datumlex-core/issues/125) | Medium | Could Have | Implements README US-14 after the core analytical foundation. |
| [#131 — Spreadsheet contract](https://github.com/DatumLex/datumlex-core/issues/131) | High | Should Have | Matches the XLSX capability in README US-16. |
| [#132 — Spreadsheet implementation and tests](https://github.com/DatumLex/datumlex-core/issues/132) | High | Should Have | Matches README US-16; safe content handling and reconciliation remain required. |
| [#133 — Grounded AI narrative story](https://github.com/DatumLex/datumlex-core/issues/133) | High | Should Have | Matches README US-17; users can inspect evidence and write a narrative manually. |
| [#134 — Generation architecture and safeguards](https://github.com/DatumLex/datumlex-core/issues/134) | High | Should Have | Enables the Should Have narrative feature; no unsafe version is an acceptable fallback. |
| [#135 — Cited generation and human review](https://github.com/DatumLex/datumlex-core/issues/135) | High | Should Have | Matches README US-17, including mandatory citations and review when selected. |
| [#138 — Consumer Law scope validation](https://github.com/DatumLex/datumlex-core/issues/138) | High | Should Have | Matches README US-18; Civil Liability remains the initial usable scope. |
| [#141 — Contracts scope validation](https://github.com/DatumLex/datumlex-core/issues/141) | High | Should Have | Matches README US-19; subject expansion follows the validated foundation. |
| [#143 — Professional workflow refinement story](https://github.com/DatumLex/datumlex-core/issues/143) | High | Could Have | Matches convenience improvements in README US-20. |
| [#144 — Validate refined professional journeys](https://github.com/DatumLex/datumlex-core/issues/144) | High | Could Have | Evaluates the additional workflow improvements; baseline usability validation remains required for core features. |
| [#145 — Refine the professional experience](https://github.com/DatumLex/datumlex-core/issues/145) | High | Could Have | Improves an already working research/evidence/report journey under README US-20. |

## Dependency and quality interpretation

STJ, approved doctrine, cross-source provenance, NLP extraction, human evaluation,
explainable evidence, adherence, and reproducible PDF export retain Must Have
outcomes. XLSX, grounded narratives, divergence, and subject expansion are Should
Have. Temporal exploration and additional workflow convenience are Could Have.

The PDF implementation and story remain Must Have. The separate design task #128
remains Should Have: a readable report using the existing approved layout can be
the temporary presentation approach. Reproducibility, citations, usable pagination,
and correct charts remain mandatory for the PDF itself. No visual fallback waives
the PDF story's acceptance criteria.

Implementation priorities are reviewed against actual scope, including overlap and
available alternatives. A lower-priority supporting task does not authorize skipping
the parent outcome's required evidence. If it is the only way to satisfy a Must Have
criterion, protect that dependency or agree an equivalent approach before deferral.
Do not interpret MoSCoW as permission to remove security, accessibility, provenance,
validation, or human review from a delivered feature.

## Verification and remaining planning work

All 139 item priorities were checked against the intended values after changes.
Visible Sprint, assignee, and status values matched the pre-change capture. Only
Priority controls were edited. The existing `estimativa`, Start, and End fields
were not edited. The 42-story catalog and priority guidance now use MoSCoW.

G1/G2 reconciliation, the blank Sprint field on #74, and real Planning Poker
estimates remain separate planning matters. This review did not resolve those
items by inventing data or changing scope. Consult the
[estimation policy](estimation-and-prioritization.md#priority-moscow) and
[client alignment record](../product/client-alignment.md) for those boundaries.
