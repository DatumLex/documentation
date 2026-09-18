# Estimation and Prioritization — DatumLex

## Purpose and ownership

Separate product priority, relative effort, and execution readiness. The PO orders
the backlog; delivery contributors estimate together; the Scrum Master facilitates.
Neither priority nor points automatically changes status, assignee, dates, or Sprint.

## Project field: `estimativa`

| Property | Agreement |
|---|---|
| Exact name | `estimativa` (requested Portuguese field name; documents remain in English) |
| GitHub type | Number |
| Unit | Story points: relative effort, complexity, and uncertainty, including quality work |
| Allowed team scale | `1, 2, 3, 5, 8, 13, 21` |
| Default | Blank; never automatically zero |
| Applies to | User stories, including existing technical/enabler stories |
| Does not apply to | Child tasks or epics |
| Source of truth | [GitHub Project](https://github.com/orgs/DatumLex/projects/1) |

The existing numeric `Estimate` field was renamed to `estimativa` and exposed in
the **Product Backlog** table, preserving its field identity. Do not create another
points field or use `Size` as a competing points total. GitHub exposes fields to all
item types: story-only use is a team agreement, not a UI restriction. Number fields
support totals but do not enforce Fibonacci values; check the scale during refinement.

## README product estimates

The README combines MoSCoW priority, **Estimate (SP)**, and planned sprint for
client-facing stories. Its US IDs and scopes are independent of Project stories.
Product estimates remain `Pending` until the team records an agreed scope and vote.
Use the [MoSCoW and Planning Poker guide](moscow-and-planning-poker.md) to maintain
this view. Never copy estimates by matching US numbers or add the two views together;
sprint reporting counts unique selected Project stories only.

## Estimate stories once

Estimate the complete outcome: implementation, data work, tests, review,
documentation, integration, and applicable deployment. Tasks explain how that
outcome is delivered; scoring both levels duplicates effort. Epics group objectives
and may span sprints, so they receive no independent points.

Use task timeboxes or remaining-work notes in issue bodies when useful. Never enter
hours, dates, or task timeboxes into `estimativa`. Independent work needs a suitable
story/enabler before joining a story-point forecast. Where separate QA, modeling,
or infrastructure stories exist, agree boundaries so shared work is counted once;
feature stories still include their own validation and integration.

Points are not hours, individual performance targets, or delivery guarantees.
There is no fixed points-to-days conversion or link between Must Have priority and size.

## Planning Poker

1. The PO explains value, scope, acceptance criteria, and dependencies.
2. Delivery contributors, including QA/data/design as applicable, clarify the
   work to meet DoD. Distinguish effort from waiting for access or dependencies.
3. Establish small reference stories together and compare new work against them.
4. Each estimator privately chooses a card; everyone reveals simultaneously.
5. Discuss high and low estimates, assumptions, uncertainty, and omitted work.
6. Vote again until agreement. Do not silently average cards or call an assistant's
   or PO's assigned number team consensus.
7. Record the agreed number on the story and retain a short session record.

Use `?` during discussion for insufficient information; leave the numeric field
blank and record the question. Blank means **not yet estimated**, not zero effort.
Under this local policy, `13` triggers a splitting discussion and `21` is a coarse
refinement estimate to split before sprint selection. Neither is a calendar promise.
Research may use an explicit timebox while its answer remains unknown.

```markdown
## Planning Poker record
- Story and scope version: <issue / relevant change>
- Date and participants: <YYYY-MM-DD / delivery contributors>
- Reference stories: <links and points>
- Assumptions and uncertainties: <summary>
- Agreed estimativa: <1, 2, 3, 5, 8, 13, or 21; blank if unresolved>
- Split or follow-up: <links or none>
```

At rollout, no consensus estimates are invented. Estimate future work during
refinement. Label later sizing of started Sprint 1 stories as retrospective or
remaining-work analysis; do not fabricate a pre-sprint baseline or historical
velocity, and do not move statuses merely to introduce points.

## Priority: MoSCoW

The GitHub Project's existing **Priority** single-select field uses **Must Have**,
**Should Have**, **Could Have**, and **Won't Have this time**, matching the
[README product backlog](../README.md#product-backlog). The delivery window is
Sprints 1–3; a Must Have does not necessarily belong in Sprint 1.

| Priority | Decision rule |
|---|---|
| Must Have | Required for the viable, trustworthy minimum delivery or an essential dependency of that outcome. |
| Should Have | Important and planned, with a workable temporary alternative. Deferral requires an explicit scope decision. |
| Could Have | Useful refinement with lower impact if deferred; reconsider first when capacity is tight. |
| Won't Have this time | Explicitly excluded from Sprints 1–3; no promise of later delivery. This is not a status. |

Match capabilities, acceptance criteria, and dependencies;
README and Project US IDs remain independent. A required task is protected with
its outcome. Supporting work with an equivalent temporary approach can have a
different priority, but its acceptance criteria cannot simply be skipped.

Applicable DoD remains mandatory. Safeguards for a Should Have feature remain
required whenever that feature is delivered; defer the capability as a whole if
necessary. Tests or security words in a task title do not by themselves promote
an optional feature to Must Have. Required academic deliverables remain planned.

Keep readiness separate: a blocked Must Have stays blocked, while a Ready Should
Have may start. Do not infer story priority from its highest child or make all
children Must Have because their epic includes a core outcome. Review the actual
dependency. Never change status, Sprint, dates, assignees, or estimates as a side
effect of priority refinement.

Apply a stricter dependency test before selecting Must Have: identify the minimum
outcome that would fail and check whether a practical alternative preserves it.
An important supporting task does not automatically inherit the parent's category.

- **Consolidated documentation:** existing versioned architecture decisions and
  endpoint contracts can support implementation while a unified reference is
  completed. Required stack, API, modeling, and dictionary deliverables still belong
  in the academic release; Should Have does not cancel that obligation.
- **Environment and execution automation:** documented setup and reproducible
  commands can support development and run automated suites/static analysis while
  broader local-service standardization and CI orchestration are completed. Existing
  required CI checks must still pass; no quality gate is disabled or waived.
- **Release evidence:** reuse the same verified deployment, reconciliation, and
  smoke results across issues. A concise checklist linking those results can serve
  the release while additional automation and artifact consolidation are completed.
  Tests, deployed checks, accessible behavior, and release evidence remain required.
- **Cross-source matching:** an initial bounded set of human-reviewed links can
  preserve the core evidence journey while deterministic candidate matching is
  developed. Retain identifiers, source evidence, reviewer, method, uncertainty,
  and coverage. Never present the bounded set as exhaustive or an unvalidated link
  as established legal correspondence.

These are temporary approaches to evaluate and validate, not claims that fallback
implementations already exist. Before deferring a supporting item, verify the
alternative satisfies every affected parent criterion and DoD. If it does not,
the dependency remains protected. A lower priority neither completes the issue
nor changes its acceptance criteria, planned sprint, or required release evidence.

There is no category quota. Discuss excessive protected scope using agreed effort
and available capacity, not row counts. Splitting one core capability into many
technical tasks increases the number of Must Have rows without adding client value.
If the minimum delivery does not fit, negotiate scope explicitly.

## Sprint planning and reporting

- **Sprint** names planned delivery; **Start/End** describe execution dates. An
  epic is not a sprint even when its current Project field names one sprint.
- Sum unique selected stories only. Do not add child tasks or epic totals. Blank
  estimates make the forecast incomplete.
- Count points once when the integrated story meets DoD; no partial credit for
  finished tasks and no individual points ranking.
- Preserve the planning snapshot. Record scope changes and revised forecasts;
  do not inflate completed estimates to match actual effort.
- Plan from availability, dependencies, review, and integration. Thursday/Friday
  are strongest, Monday/Tuesday moderate, Wednesday should avoid execution
  commitments, and weekends support light work or contingency.
- Sprint 1 delivery is **2026-09-27**. Its replan starts no earlier than
  **2026-09-14**, concentrates modeling on **September 17–18** and integration/deploy
  on **September 24–25**, with little buffer. Points do not remove this risk.
- Sprint 2/3 dates require team planning; do not infer them from story counts.

## References

The scale and story-only rule are DatumLex agreements. Planning Poker is
collaborative estimation, not a mandatory Scrum technique.

- [Mountain Goat Software — Planning Poker](https://www.mountaingoatsoftware.com/agile/story-points/planning-poker)
- [Mountain Goat Software — Fibonacci estimation](https://www.mountaingoatsoftware.com/agile/why-the-fibonacci-sequence-works-well-for-estimating)
- [Definition of Ready](definition-of-ready.md)
- [Definition of Done](definition-of-done.md)
- [Roadmap](../product/product-roadmap.md)
