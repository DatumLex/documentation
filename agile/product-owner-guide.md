# Product Owner Guide — DatumLex

## Purpose

The Product Owner (PO) maximizes product value by maintaining a clear Product
Goal and an ordered, understandable Product Backlog. In DatumLex, the PO also
protects the legal decision-support purpose of the product: analytical results
must be useful, explainable, evidence-based, and never presented with false
precision.

The PO owns product decisions and backlog ordering. Quality, technical design,
and delivery remain collaborative team responsibilities.

## Core responsibilities

- Explain the product vision, users, expected outcomes, and current Product Goal.
- Order backlog items by value, risk, dependency, learning, and available team
  capacity.
- Write or validate user stories, scope, acceptance criteria, and business rules.
- Keep epics, stories, and tasks traceable without using duplicate backlogs.
- Clarify what is required now, what is deferred, and what is explicitly out of
  scope.
- Make timely decisions when the team identifies ambiguity or competing needs.
- Validate completed user-story outcomes and record acceptance or required
  follow-up.
- Communicate with stakeholders and turn feedback into transparent backlog
  decisions rather than informal hidden requests.

The PO may delegate backlog writing, research, or analysis, but remains
accountable for backlog clarity and ordering.

## Backlog structure

Use the hierarchy defined in the [Agile Glossary](glossary.md):

- **Epic:** a broad product objective that may span sprints.
- **User Story:** a valuable, testable outcome from a user's perspective.
- **Task:** focused work required to deliver or validate a story.

Use the [GitHub Product Backlog](https://github.com/orgs/DatumLex/projects/1) as
the live source for priorities, assignees, status, sprint, and dates. Acceptance
criteria, dependencies, evidence, and discussion belong in the linked issue.

## Writing and refining a user story

A useful story identifies the user, need, and value:

```text
As a <user or role>,
I want <capability>,
so that <measurable value or outcome>.
```

Each story should also include:

- product scope and explicit exclusions;
- verifiable acceptance criteria, using `Given / When / Then` when helpful;
- legal or analytical rules, including denominator, exclusions, unknown values,
  source limitations, and refresh expectations;
- dependencies and required inputs;
- expected error, empty, unavailable, and partial-data behavior;
- evidence required for acceptance; and
- links to designs, API contracts, data definitions, research, or decisions.

During refinement, use the [Definition of Ready](definition-of-ready.md) with
developers and reviewers. Moving an unclear item to `Ready` does not resolve its
ambiguity.

## Prioritization

Consider the following together rather than using a single score mechanically:

1. User and stakeholder value.
2. Alignment with the Product Goal and sprint objective.
3. Legal, data-quality, security, accessibility, and delivery risk.
4. Dependencies and opportunities to unblock parallel work.
5. Learning value where feasibility is uncertain.
6. Effort, available capacity, and review time.
7. Cost of delay and consequences of being wrong.

Technical enablers, research, testing, documentation, and debt belong in the
backlog when they protect delivery or product quality. Do not hide them behind
feature work.

## Sprint activities

### Before Sprint Planning

- Review the Product Goal and order the relevant backlog.
- Ensure candidate stories have clear value, scope, acceptance criteria,
  dependencies, and validation expectations.
- Confirm stakeholder inputs and reference artifacts are available.
- Work with the team to split oversized stories without losing user value.

### During Sprint Planning

- Explain the highest-value items and negotiate a realistic Sprint Goal with
  the Scrum Team.
- Answer product questions without prescribing unnecessary implementation
  details.
- Respect developer capacity, technical sequencing, and quality work.

### During the Sprint

- Remain available for decisions and clarify product behavior promptly.
- Review board comments, blockers, and scope changes.
- Reorder future backlog items as new information appears without silently
  changing the active Sprint Backlog.
- Record material decisions on the relevant issue.

### Sprint Review and acceptance

- Evaluate the integrated outcome against the story criteria and intended user
  value, not only screenshots or task completion.
- Consider stakeholder feedback and create or reorder follow-up items.
- Record acceptance, rejection, limitation, or deferred work on the story.
- Do not accept fabricated data, missing required evidence, or unmet quality
  criteria merely to close a sprint.

## Board and communication practices

Follow the transitions documented in the
[Definition of Ready](definition-of-ready.md) and
[Definition of Done](definition-of-done.md):

```text
Backlog → Ready → In progress → In review → Done
```

The PO should:

- keep priority and sprint fields current;
- avoid changing technical task status without coordinating with its assignee;
- comment when scope or acceptance criteria change;
- identify the reason and next action for blocked work;
- use links to decisions and evidence instead of private confirmation; and
- distinguish implementation progress from a complete, integrated outcome.

## Story acceptance record

```markdown
## Product Owner acceptance
- Story outcome reviewed: <what was demonstrated>
- Acceptance criteria: <passed items and evidence>
- User value: <observed result>
- Known limitations: <details or none>
- Follow-up issues: <links or none>
- Decision: Accepted / Changes required / Blocked
- Product Owner / date: <name / YYYY-MM-DD>
```

PO acceptance applies to the user-story outcome. It does not replace technical
review, QA, security checks, automated tests, or the shared Definition of Done.

## Quick checklist

- [ ] Product Goal and sprint objective are understandable.
- [ ] Backlog order reflects current value, risk, and dependencies.
- [ ] Stories describe users, outcomes, scope, and verifiable criteria.
- [ ] Required business, legal, metric, and data rules are linked.
- [ ] Decisions and changes are recorded on GitHub issues.
- [ ] Reviews assess an integrated result with real evidence.
- [ ] Acceptance and follow-up work are explicit before `Done`.

## Related documents

- [Product Vision](../product/product-vision.md)
- [Personas and Primary Audiences](../product/personas.md)
- [Product Roadmap](../product/product-roadmap.md)
- [Agile Glossary](glossary.md)
- [Definition of Ready](definition-of-ready.md)
- [Definition of Done](definition-of-done.md)
- [Scrum Master Guide](scrum-master-guide.md)
- [Developer Guide](../development/developer-guide.md)
- [QA Guide](../devops/qa-guide.md)
- [Product Backlog](https://github.com/orgs/DatumLex/projects/1)
