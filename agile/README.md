# Agile — DatumLex

This folder documents how the LegacyTech team plans, reviews, and tracks DatumLex development. Agreements apply across sprints and evolve through reviewed changes.

## Working agreements

| Document | Purpose | Applied when |
|---|---|---|
| [User-story catalog](user-stories.md) | Snapshot of all stories, current priorities, and planned delivery. | Refinement and stakeholder review. |
| [Estimation and prioritization](estimation-and-prioritization.md) | Story-only `estimativa`, Planning Poker, priority and capacity rules. | Refinement, planning, and reporting. |
| [Agile Glossary](glossary.md) | Define the backlog hierarchy, board statuses, and shared agile language. | Onboarding, refinement, and daily work. |
| [Definition of Ready](definition-of-ready.md) | Explain the clarity and available inputs required to start. | Refinement, Sprint Planning, and transition to Ready. |
| [Definition of Done](definition-of-done.md) | Explain quality, review, validation, and documentation required for completion. | Task review, story completion, integrated delivery. |
| [Product Owner Guide](product-owner-guide.md) | Define product ownership, backlog ordering, refinement, and story acceptance practices. | Product planning, stakeholder decisions, and acceptance. |
| [Scrum Master Guide](scrum-master-guide.md) | Define facilitation, impediment management, board stewardship, and continuous improvement practices. | Scrum events, daily coordination, and process improvement. |
| [Team Permanence Rule](team-permanence-rule.md) | Define the three-strike participation rule and communicated-unavailability exception. | Team accountability and participation follow-up. |
| [Strike Register](strike-register.md) | Record applied strikes using the agreed fields. | When the PO and Scrum Master confirm a strike. |

Acceptance criteria remain in each issue and describe its outcome. DoR/DoD complement the existing **Work and acceptance**, **Dependencies**, and **Evidence** sections. Both documents include reusable evidence templates and guidance for different kinds of work.

## Live planning and evidence

The [GitHub Project](https://github.com/orgs/DatumLex/projects/1) is the live source for backlog items, Priority, Sprint, `estimativa`, assignees, status, and dates. Use [datumlex-core issues](https://github.com/DatumLex/datumlex-core/issues) for stories, tasks, acceptance criteria, blockers, and deliverable/validation links.

The workflow is `Backlog → Ready → In progress → In review → Done`. Backlog tasks wait on dependencies; Ready tasks can start. See [transition rules](definition-of-ready.md#board-transitions) and [completion workflow](definition-of-done.md#review-and-board-workflow). Planned dates do not prove work has started or finished.

## Sprint records

When an academic delivery needs a snapshot, add a dated `sprint-<n>-user-stories.md` here with sprint goal, included issue links, applied readiness/acceptance evidence, and delivery references. These are historical snapshots, not a second live backlog. No snapshot is implied to exist until its file is committed.

Use English for documents and issues, including `Given / When / Then` scenarios when useful. Epics group product objectives and may span sprints; stories and tasks are planned within sprint capacity.

## Related documents

- [Branch Standards](../development/branch-standards.md)
- [Commit Standards](../development/commit-standards.md)
- [Developer Guide](../development/developer-guide.md)
- [QA Guide](../development/qa-guide.md)
- [End-to-End Development Process](../development/development-process.md)
- [Repository index](../README.md)

Review changes to these agreements with the team and record rationale and effective date in the PR. Never silently relax an unmet completion criterion to close an issue.
