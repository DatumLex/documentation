# Agile Glossary and Working Agreements

## Purpose

This document defines the language and working agreements used to manage the
DatumLex Product Backlog. It gives every team member the same understanding of
what an Epic, User Story, and Task represent, and how work moves from an idea
to a reviewed product increment.

The live backlog is maintained in the GitHub Project. This document explains
how to use that backlog; it does not replace it.

## Backlog Hierarchy

DatumLex uses a three-level hierarchy for product work:

```text
Epic
└── User Story
    └── Task
```

### Product Backlog

The Product Backlog is the ordered list of work that may be needed for
DatumLex. It includes product capabilities, technical work, documentation,
quality activities, and deployment work. The Product Owner owns the priority
order, while the whole team helps refine the items.

The backlog must remain transparent: every item should have a meaningful title,
an owner when active, a clear status, and a link to its parent item when it is
part of a larger delivery.

### Epic

An **Epic** is a broad product outcome that is too large to complete as one
piece of work in a sprint. It groups related User Stories that deliver the same
capability or milestone.

Example: *Legal Analytics Dashboard* is an Epic because it includes filters,
metric cards, charts, API integration, styling, testing, and deployment.

An Epic is completed only when its agreed User Stories have met their
acceptance criteria and the resulting outcome is accepted by the Product Owner.
It is not completed merely because child items were created or started.

### User Story

A **User Story** describes a small, valuable product behavior from the
perspective of the person who benefits from it. It should be understandable by
both technical and non-technical stakeholders.

DatumLex uses the following format when applicable:

```text
As a <user or role>,
I want <capability>,
so that <benefit or outcome>.
```

Example:

```text
As a legal analyst,
I want to see merit indicator cards,
so that I can understand appeal outcomes in the selected scope.
```

A User Story should also include scope, business rules, dependencies,
acceptance criteria, and a test approach. For UI work, it should reference the
approved prototype or visual assets. The story must satisfy the
[Definition of Ready](definition-of-ready.md) before it enters a sprint.

### Task

A **Task** is a concrete piece of work needed to complete a User Story. Tasks
describe implementation or validation activities; they are not independent
product promises.

Examples:

- Build the three metric cards from the API contract.
- Add data-quality notes and card states.
- Implement the merit distribution chart.
- Configure and publish the Vercel frontend.

Tasks should be small enough to show clear progress, but large enough to leave
meaningful evidence of work. A task should identify its expected output, such
as a component, endpoint, test, migration, document, or deployment
configuration.

### Acceptance Criteria

**Acceptance Criteria** are the observable conditions that determine whether a
User Story delivers its intended result. They define behavior, boundaries,
states, and data rules; they are not a list of coding steps.

When possible, use the Gherkin style documented in the Definition of Ready:

```text
Given <context>,
when <action or event>,
then <expected result>.
```

For example, an analytical dashboard story must specify what happens when data
is loading, empty, unavailable, or invalid. The interface must not replace
missing real data with invented metrics.

### Sprint Backlog

The **Sprint Backlog** is the set of backlog items selected for the current
sprint, together with the team plan for delivering them. It is not a frozen
contract: the team may refine tasks during the sprint as long as the Sprint Goal
is protected and changes remain visible on the GitHub Project.

### Sprint Goal

A **Sprint Goal** is the single outcome that gives the sprint focus. It helps
the team decide whether new work, scope changes, or implementation details
support the agreed delivery.

### Increment

An **Increment** is a usable, integrated result of the sprint. It must meet the
[Definition of Done](definition-of-done.md), including relevant testing,
documentation, review, and validation. Code that only works on one developer's
machine is not an increment.

## GitHub Project Statuses

DatumLex tracks item flow with the following statuses:

| Status | Meaning | Expected action |
|---|---|---|
| Backlog | Known work not yet selected or started. | Refine, prioritize, or wait for sprint planning. |
| Ready | The item satisfies the Definition of Ready. | It can be selected for a sprint. |
| In progress | Active work is underway. | Keep the assignee, linked branch, and progress visible. |
| In review | Implementation is ready for peer review. | Open or update the PR and address review feedback. |
| Done | The item satisfies the Definition of Done. | Retain the evidence and close the item. |

Moving an item to **In progress** means that active work has actually begun.
Moving it to **Done** means the quality gates have been met; it is not a way to
indicate that coding is merely finished.

## Working Agreements

### Before Starting Work

1. Confirm that the item has a parent Epic or User Story when applicable.
2. Read the scope, acceptance criteria, dependencies, and relevant design or
   architecture documents.
3. Confirm that the item meets the Definition of Ready, or make the missing
   information explicit before implementation begins.
4. Assign the active item to its owner and move it to **In progress** only when
   work starts.
5. Create a branch following the [Branch Standards](../devops/branch-standards.md),
   preferably including the related issue number.

### During Development

1. Keep commits small, in English, and compliant with the
   [Commit Standards](../devops/commit-standards.md).
2. Reference the related issue with `Refs #<number>` when the work contributes
   to it but does not complete it. Use `Resolves #<number>` only when the
   completed change truly closes the item.
3. Keep implementation notes, blockers, decisions, and changed assumptions on
   the relevant GitHub Issue or Pull Request so that the board remains the
   source of truth.
4. Do not claim real analytical values when the API or validated data is not
   available. Use explicit loading, empty, unavailable, or error states.
5. Update documentation whenever a decision, dependency, environment variable,
   API contract, or operating procedure changes.

### Review and Completion

1. Open a Pull Request against the correct target branch and use a Conventional
   Commit-style title.
2. Describe the user-facing outcome, implementation summary, validation steps,
   and issue references in the PR.
3. Request review from at least one team member other than the author.
4. Resolve review feedback and re-run the relevant checks before merging.
5. Validate the resulting increment against the acceptance criteria and the
   Definition of Done.
6. Only then move the item to **Done** and retain the PR, test, deployment, or
   other validation evidence.

## Anti-Patterns to Avoid

- Creating tasks with vague titles such as “fix frontend” or “work on API.”
- Starting stories with unknown data rules, missing dependencies, or no
  acceptance criteria.
- Marking an item as Done before review, testing, documentation, or Product
  Owner acceptance.
- Treating commits as a measure of individual contribution instead of using
  delivered, reviewed work and board evidence.
- Hiding blockers, changing scope silently, or using the board status as a
  substitute for a clear written update.
- Adding mock values that could be mistaken for verified legal analytics data.

## Related Documents

- [Definition of Ready](definition-of-ready.md)
- [Definition of Done](definition-of-done.md)
- [Branch Standards](../devops/branch-standards.md)
- [Commit Standards](../devops/commit-standards.md)
- [Technology Stack and Rationale](../architecture/technology-stack.md)
