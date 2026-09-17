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
There is no fixed points-to-days conversion or link between High priority and size.

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

## Priority: High, Medium, Low

This section governs the GitHub Project's implementation priorities. The
[README product backlog](../README.md#product-backlog) uses MoSCoW for the
three-sprint product delivery, with independent US IDs and product priorities.
Do not automatically copy Must/Should/Could into Project High/Medium/Low fields.
Review product value, implementation dependencies, and capacity at the appropriate
level; this distinction does not create duplicate estimates.

| Priority | Decision rule |
|---|---|
| High | Absence prevents the minimum Sprint Goal, blocks several necessary outcomes, or makes the selected release unsafe or unreliable. |
| Medium | Important planned value that follows the foundation and can be sequenced or renegotiated before the minimum core. |
| Low | Refinement that can be deferred with little impact on the sprint objective. |

Applicable DoD is mandatory at every priority. A test, security control, citation,
or provenance criterion does not alone make an optional feature High. Defer the
feature rather than dropping its protections. A blocked High stays blocked; a Ready
Medium may execute first. Do not inherit task priority mechanically from its parent
or compute story priority from its highest child.

Order within each category by dependency, value, risk, and capacity. There is no
High quota, but a backlog dominated by High needs a minimum-delivery discussion.
The [story catalog](user-stories.md) records current fields, not a claim that the
distribution is final or that proposed changes have been applied.

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
