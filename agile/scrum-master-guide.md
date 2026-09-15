# Scrum Master Guide — DatumLex

## Purpose

The Scrum Master helps the Scrum Team understand and apply Scrum, improve its
way of working, and remove impediments that prevent progress toward the Product
Goal. In DatumLex, the Scrum Master also promotes transparent evidence on the
GitHub board so sprint status reflects reality rather than assumptions.

The Scrum Master is a facilitator and coach, not the team's manager, task
dispatcher, or approval gate.

## Core responsibilities

### Serving the team

- Facilitate effective Scrum events and keep them focused on their purpose.
- Help the team identify, expose, and remove impediments.
- Encourage sustainable planning, collaboration, self-management, and shared
  quality ownership.
- Protect focus while keeping material risks and dependencies visible.
- Coach the team to follow its Definition of Ready, Definition of Done, review
  workflow, and evidence standards.
- Support constructive conflict resolution and psychologically safe discussion.

### Serving the Product Owner

- Support clear Product Goals, backlog refinement, and transparent ordering.
- Help stakeholders and developers understand backlog items and dependencies.
- Facilitate collaboration without taking over product decisions.

### Serving the organization

- Make systemic impediments visible and coordinate their resolution.
- Improve collaboration across product, engineering, QA, design, data, and
  academic stakeholders.
- Promote evidence-based improvement rather than activity reporting or commit
  counting.

## Scrum events

### Sprint Planning

- Confirm that the Product Owner can explain the Product Goal and ordered items.
- Help the team define a coherent Sprint Goal and realistic Sprint Backlog.
- Surface capacity, dependencies, review time, and readiness gaps.
- Prevent pressure to start work that lacks essential inputs.

### Daily Scrum

The Daily Scrum belongs to the Developers. Help them use it to inspect progress
toward the Sprint Goal and adapt their plan. A useful conversation covers:

- progress toward the goal;
- changed assumptions or dependencies;
- blockers requiring coordination;
- work that needs review, integration, or help; and
- the plan until the next Daily Scrum.

It is not a status report to the Scrum Master. Detailed problem solving should
continue with the relevant people after the event.

### Sprint Review

- Ensure the team presents an integrated, evidence-backed outcome.
- Invite useful stakeholders and collect actionable feedback.
- Compare the result with the Product Goal, sprint objective, acceptance
  criteria, data limitations, and current environment.
- Help translate feedback into explicit backlog decisions.

### Sprint Retrospective

- Create a safe environment for inspecting people, interactions, process,
  tools, quality, and Definition of Done.
- Use observations and lightweight metrics to find patterns, not to rank people.
- Select a small number of concrete improvement actions with owners and review
  dates.
- Check previous actions before adding new ones.

### Backlog refinement

Refinement is an ongoing activity rather than a formal Scrum event. Facilitate
it when helpful so stories become clear, appropriately sized, dependency-aware,
and verifiable under the [Definition of Ready](definition-of-ready.md).

## Board stewardship

The [GitHub Product Backlog](https://github.com/orgs/DatumLex/projects/1) is the
team's live planning source. The Scrum Master helps the team keep it accurate,
but assignees remain responsible for communicating their actual work.

Check regularly that:

- items have the correct epic/story/task relationship;
- assignee, sprint, priority, and status reflect current reality;
- work moves to `In progress` only after it starts;
- blockers include cause, owner, next action, and expected follow-up;
- deliverables, PRs, tests, review findings, and acceptance evidence are linked;
- partially complete work is not reported as `Done`; and
- deferred work becomes a linked issue rather than disappearing in comments.

Follow the shared workflow:

```text
Backlog → Ready → In progress → In review → Done
```

See the [Agile Glossary](glossary.md),
[Definition of Ready](definition-of-ready.md), and
[Definition of Done](definition-of-done.md) for exact meanings.

## Impediment management

When an impediment appears:

1. Record it on the affected issue.
2. Describe its impact on the Sprint Goal and dependent work.
3. Identify an owner and the next concrete action.
4. Escalate only to the person or group able to resolve it.
5. Follow up until the condition changes.
6. Record the resolution and update the plan or board.

Use this template:

```markdown
## Impediment
- Blocked work: <issue links>
- Cause: <known facts>
- Impact: <scope, date, quality, or dependency>
- Owner: <person coordinating resolution>
- Next action: <action and expected date>
- Workaround: <safe option or none>
- Status: Open / Monitoring / Resolved
```

The Scrum Master removes organizational friction but does not conceal missing
inputs, weaken acceptance criteria, or instruct the team to bypass quality.

## Metrics and reporting

Use metrics to support conversation and forecasting, never to evaluate
individual worth. Helpful team-level signals include:

- progress toward the Sprint Goal;
- completed versus planned work, with scope changes visible;
- cycle time and time waiting for review;
- age and recurrence of impediments;
- escaped defects and rework patterns;
- automated check health; and
- completion of retrospective improvement actions.

Commit counts, lines of code, hours online, and raw task counts are not reliable
measures of value or individual performance.

## Working with QA and reviews

- Reserve capacity for review, correction, integration, and validation.
- Encourage authors to attach reproducible evidence before requesting review.
- Ensure meaningful QA activity is recorded on the related card.
- Help resolve stalled reviews without pressuring a reviewer to approve.
- Use the [QA and Pull Request Review Guide](../devops/qa-guide.md) as the review
  standard and preserve reviewer independence whenever possible.

## Scrum Master checklist

- [ ] Scrum events have a clear purpose, outcome, and appropriate participants.
- [ ] Sprint Goal, active work, dependencies, and blockers are visible.
- [ ] The board matches actual progress and contains evidence links.
- [ ] The PO receives support without losing product accountability.
- [ ] Developers self-manage implementation and technical decisions.
- [ ] QA and review time are included in the delivery plan.
- [ ] Improvement actions have owners and are revisited.
- [ ] Metrics are used for learning, not individual surveillance.

## Related documents

- [Team Permanence Rule](../process/team-participation-policy.md)
- [Agile Glossary](glossary.md)
- [Definition of Ready](definition-of-ready.md)
- [Definition of Done](definition-of-done.md)
- [Product Owner Guide](product-owner-guide.md)
- [Developer Guide](../development/developer-guide.md)
- [QA Guide](../devops/qa-guide.md)
- [Branch Standards](../devops/branch-standards.md)
- [Commit Standards](../devops/commit-standards.md)
- [Product Backlog](https://github.com/orgs/DatumLex/projects/1)
