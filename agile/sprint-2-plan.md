# Sprint 2 — Planning and Assignment Guide

Refined **2026-10-07** from the [live Project](https://github.com/orgs/DatumLex/projects/1),
the repositories and the [September 22/25 client direction](../product/client-alignment.md).
This is the planning handoff for the team's assignment meeting. It is not a
completed sprint report or a claim that all source access is already available.
Issue bodies hold the full acceptance criteria and start/completion dependencies;
the Project remains authoritative for live status, owners, dates and estimates.

Open the saved [Sprint 2 Planning view](https://github.com/orgs/DatumLex/projects/1/views/15)
for the meeting. It filters Sprint 2 and shows the epic → story → task hierarchy,
Priority, Assignees, Status and story-only Estimate.

## Sprint goal

Let a professional select a Civil Liability research scope, inspect TJDFT/STJ
results and initial BDJur context, understand extracted theses through supporting
passages, compare relevant precedent evidence, and export the same analysis to PDF.
The journey must show where evidence came from and what its coverage permits.

## Scope and planning state

- **4 epics, 13 stories, 28 tasks**: 45 Sprint 2 items, all open, unassigned and
  in **Backlog** at refinement. No execution dates were invented.
- Existing Sprint 2 stories and the moved PDF story retain their September 17
  estimates: **100 SP across 10 stories**, including 8 SP Should Have and 8 SP
  Could Have. This excludes three unestimated new stories and is **not** a complete
  sprint estimate, capacity commitment or velocity. Revalidate changed scope.
- New implementation US-43, US-44 and US-45 have blank Estimate. Epics and tasks
  have no points. Discuss splitting the 13 SP stories into usable outcomes.
- Civil Liability stays the subject. BDTD, SciELO and other source candidates are
  not automatically included. XLSX, generative narratives, Consumer Law, Contracts
  and further professional workflow improvements remain Sprint 3.
- Divergence remains **Should Have** and temporal exploration **Could Have**.
  Any deferral requires an explicit scope decision; those labels do not remove
  the quality requirements of a delivered feature. Basic explainable NLP ranking
  and Ver fontes remain Must Have in US-33, even if temporal work is deferred.
- Matching task #105 and the required PDF template task #128 are now Must Have:
  they provide necessary traceability and report acceptance inputs. This does
  not make optional visual polish or every future matching method mandatory.

## Complete issue map

### [Epic 8: Cross-Source Legal Data Foundation](https://github.com/DatumLex/datumlex-core/issues/96)

| Story / value | Priority | Estimate reference | Child tasks |
|---|---|---|---|
| [US-43 — Retrieve Traceable TJDFT Decision Text](https://github.com/DatumLex/datumlex-core/issues/161) | Must Have | Pending | [Validate TJDFT decision-text access and coverage](https://github.com/DatumLex/datumlex-core/issues/162); [Ingest and reconcile TJDFT decision text](https://github.com/DatumLex/datumlex-core/issues/163) |
| [US-28 — Integrate STJ Jurisprudence and Precedents](https://github.com/DatumLex/datumlex-core/issues/97) | Must Have | 8 SP | [Validate STJ source access and retrieval scope](https://github.com/DatumLex/datumlex-core/issues/98); [Implement auditable STJ jurisprudence ingestion](https://github.com/DatumLex/datumlex-core/issues/99) |
| [US-29 — Integrate BDJur and Approved Open Doctrine](https://github.com/DatumLex/datumlex-core/issues/100) | Must Have | 8 SP | [Assess BDJur and open-doctrine source feasibility](https://github.com/DatumLex/datumlex-core/issues/101); [Implement doctrine ingestion with rights and provenance](https://github.com/DatumLex/datumlex-core/issues/102) |
| [US-30 — Normalize and Link Cross-Source Legal Records](https://github.com/DatumLex/datumlex-core/issues/103) | Must Have | 13 SP | [Extend the model for cross-source provenance](https://github.com/DatumLex/datumlex-core/issues/104); [Implement traceable cross-source matching](https://github.com/DatumLex/datumlex-core/issues/105) |

### [Epic 9: NLP Thesis and Legal Reasoning Extraction](https://github.com/DatumLex/datumlex-core/issues/106)

| Story / value | Priority | Estimate reference | Child tasks |
|---|---|---|---|
| [US-31 — Extract Legal Grounds and Thesis Candidates](https://github.com/DatumLex/datumlex-core/issues/107) | Must Have | 13 SP | [Define the legal NLP taxonomy and annotation guide](https://github.com/DatumLex/datumlex-core/issues/108); [Implement the thesis and grounds extraction pipeline](https://github.com/DatumLex/datumlex-core/issues/109) |
| [US-32 — Validate NLP Quality with Human Review](https://github.com/DatumLex/datumlex-core/issues/110) | Must Have | 13 SP | [Build a representative legal NLP benchmark](https://github.com/DatumLex/datumlex-core/issues/111); [Evaluate NLP quality and approve release thresholds](https://github.com/DatumLex/datumlex-core/issues/112) |
| [US-33 — Expose Explainable NLP Results](https://github.com/DatumLex/datumlex-core/issues/113) | Must Have | 8 SP | [Persist versioned NLP evidence and corrections](https://github.com/DatumLex/datumlex-core/issues/114); [Add explainable thesis endpoints and interface states](https://github.com/DatumLex/datumlex-core/issues/115) |

### [Epic 10: Comparative Legal Intelligence](https://github.com/DatumLex/datumlex-core/issues/116)

| Story / value | Priority | Estimate reference | Child tasks |
|---|---|---|---|
| [US-34 — Measure Adherence to Superior-Court Precedents](https://github.com/DatumLex/datumlex-core/issues/117) | Must Have | 13 SP | [Define precedent-adherence methodology](https://github.com/DatumLex/datumlex-core/issues/118); [Implement adherence metrics and evidence drill-down](https://github.com/DatumLex/datumlex-core/issues/119) |
| [US-35 — Identify Divergent Understandings](https://github.com/DatumLex/datumlex-core/issues/120) | Should Have | 8 SP | [Define divergence detection and safeguards](https://github.com/DatumLex/datumlex-core/issues/121); [Implement chamber and panel comparison views](https://github.com/DatumLex/datumlex-core/issues/122) |
| [US-36 — Explore Temporal Trends and Main Theses](https://github.com/DatumLex/datumlex-core/issues/123) | Could Have | 8 SP | [Implement version-aware temporal aggregates](https://github.com/DatumLex/datumlex-core/issues/124); [Build the temporal and thesis exploration experience](https://github.com/DatumLex/datumlex-core/issues/125) |

### [Epic 13: Dynamic Research, PDF Reports, and Sprint 2 Delivery](https://github.com/DatumLex/datumlex-core/issues/160)

| Story / value | Priority | Estimate reference | Child tasks |
|---|---|---|---|
| [US-44 — Explore a Shared Dashboard with Dynamic Multiselect Filters](https://github.com/DatumLex/datumlex-core/issues/164) | Must Have | Pending | [Define multiselect filters and analytical-context semantics](https://github.com/DatumLex/datumlex-core/issues/165); [Implement multiselect API queries and source options](https://github.com/DatumLex/datumlex-core/issues/166); [Build and validate dynamic multiselect dashboard controls](https://github.com/DatumLex/datumlex-core/issues/167) |
| [US-45 — Validate and Publish the Sprint 2 Increment](https://github.com/DatumLex/datumlex-core/issues/168) | Must Have | Pending | [Audit Sprint 1 baseline and Sprint 2 delivery blockers](https://github.com/DatumLex/datumlex-core/issues/169); [Reconcile and test the Sprint 2 end-to-end increment](https://github.com/DatumLex/datumlex-core/issues/170); [Deploy Sprint 2 and publish release and demo evidence](https://github.com/DatumLex/datumlex-core/issues/171) |
| [US-37 — Export a Reproducible PDF Report](https://github.com/DatumLex/datumlex-core/issues/127) | Must Have | 8 SP | [Design the professional PDF report template](https://github.com/DatumLex/datumlex-core/issues/128); [Implement and validate server-side PDF export](https://github.com/DatumLex/datumlex-core/issues/129) |

## Suggested execution sequence

| Sequence | Work that can start together | Required output before the next dependent implementation |
|---|---|---|
| 1 — Baseline and access | Baseline audit #169; STJ research #98; BDJur research #101; TJDFT text research #162; draft filter contract #165 | Verified source samples/access/rights; baseline blockers; canonical scope/denominator decisions. Confirm owners and bounded research timeboxes. |
| 2 — Contracts and design | Model/dictionary #104; NLP taxonomy #108; benchmark sampling design #111; filter contract #165; PDF template #128 | Reviewed relevant schema/mapping, taxonomy, API/UI/PDF context and template. Design can proceed with labeled fixtures; real-data acceptance cannot. |
| 3 — Data and implementation | STJ #99, BDJur #102 and TJDFT text #163 after their contracts; matching #105; extraction #109; persistence #114; filter API #166 and UI #167 | Reproducible real records/texts, accurate links, versioned extractions and query/evidence APIs. Source-specific implementation can advance when its own inputs are ready. |
| 4 — Quality and analysis | Benchmark/evaluation #111/#112; evidence API/UI #115; adherence method/implementation #118/#119; selected divergence #121/#122 and temporal #124/#125 | Reviewed quality thresholds/results, calculable metrics, source-linked UI and consistent multiselect behavior. Method design can start earlier with source examples. |
| 5 — Export and release | PDF implementation #129; integrated reconciliation #170; deployment/demo #171 | Identical source/API/UI/PDF context, required tests and rendered/link checks, deployed smoke evidence, documented limits and PO acceptance. Test design/release documentation can start earlier. |

This table is a sequencing aid, not a global phase gate. Follow each task's own
start inputs. A story can contain dependent tasks within the same sprint; it
does not need every downstream integration result before independent work starts.

## Decisions to record in the team meeting

1. Confirm the goal and capacity; select the Should/Could scope explicitly and
   split oversized work if needed. Estimate the three new stories and revalidate
   changed estimates without counting feature tests or shared dependencies twice.
2. Assign each task and an independent reviewer, then agree dates/sequence and
   research timeboxes. Keep legal/PO methodology review available when needed.
3. Confirm source access and evidence, bounded sample/period coverage, text rights,
   and the fallback decision route when a required source is unavailable.
4. Resolve counting/filter semantics and establish numeric NLP/matching quality
   thresholds with the relevant reviewers; do not invent them in implementation.
5. Confirm hosting with current deployment evidence and the academic constraint.
   Audit the G1/G2/merit distinction and remaining Sprint 1 blockers in #169.
6. Apply [DoR](definition-of-ready.md) to each selected item before moving it to
   Ready. Refinement, a planned date or an assigned owner alone does not prove readiness.

## Integrated acceptance demonstration

- Start with **TJDFT alone**, then select **TJDFT + STJ** in the same dashboard;
  combine outcomes and legal sources, clear/reset, and inspect honest empty or
  partial-source results. Doctrine must not inflate decision/outcome counts.
- Inspect a ranked thesis/ground, its uncertainty/version and **Ver fontes** card;
  open the exact supporting passage and original source. Show initial BDJur
  evidence separately from binding/persuasive precedent authority.
- Explain adherence using numerator, denominator, eligible population and evidence.
  Demonstrate selected divergence/trend work with its method and limitations.
- Export the same context to PDF. Check indicators/charts, clickable source links,
  excerpts, counting unit, coverage, NLP criteria, versions and limitations.
- Link real-data reconciliation, required automated/static checks, rendered PDF
  checks, deployed smoke results, independent review and PO acceptance under
  [DoD](definition-of-done.md). Approval of a mockup/sample is not release acceptance.

## Refinement audit

All 33 pre-existing Sprint 2/moved-PDF items were refined; 12 issues were added
(#160–#171). PDF #127 was reparented from Sprint 3 epic #126 to Sprint 2 epic #160;
its tasks #128/#129 kept their parent. The 17 remaining Sprint 3 issues received
clarified dependencies/boundaries without moving their delivery into Sprint 2.
Sprint 1 history and assignments were preserved. Existing story estimates were
retained as dated references; no work was marked started, reviewed or complete.

See the [45-story catalog](user-stories.md), [product roadmap](../product/product-roadmap.md)
and [client planning follow-up](../product/client-alignment.md#planning-follow-up--october-7-2026).
