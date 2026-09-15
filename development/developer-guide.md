# Developer Guide — DatumLex

## Purpose

This guide explains the expected development workflow for DatumLex. It applies
to frontend, backend, data, test, infrastructure, and technical documentation
work. Its goal is to make every change understandable, reproducible,
reviewable, and traceable from a backlog item to the delivered result.

The guide complements, rather than replaces, the project's specialized
standards. Developers must follow the linked documents whenever they apply.

## Before starting work

1. Read the epic, user story, task, acceptance criteria, dependencies, and
   evidence requirements on the [Product Backlog](https://github.com/orgs/DatumLex/projects/1).
2. Confirm that the item satisfies the [Definition of Ready](../agile/definition-of-ready.md).
3. Clarify assumptions with the Product Owner when expected product behavior is
   ambiguous. Clarify technical constraints with the relevant technical owner.
4. Assign the task and move it to `In progress` only when implementation has
   actually started.
5. Add a card comment when useful to record the planned approach, dependencies,
   or a known limitation.

Do not silently expand the scope of a task. Record follow-up work as a linked
issue when it cannot be completed within the agreed item.

## Repository and environment setup

- Follow the repository README for prerequisites, installation, environment
  variables, database setup, and local execution.
- Use supported versions of the technologies recorded in the
  [Technology Stack and Rationale](../architecture/technology-stack.md).
- Keep secrets outside the repository. Commit an example environment file only
  with safe placeholder values when configuration documentation is needed.
- Install dependencies through the project's package manager and commit its
  lockfile when dependencies change.
- Avoid machine-specific paths and configuration. Another developer must be
  able to reproduce the environment from versioned instructions.

## Branch workflow

Create a focused branch from the team's current base branch. The branch name
must follow [Branch Standards](branch-standards.md):

```text
<type>/<issue-number>-<short-description>
```

Example:

```text
feat/54-dashboard-metric-cards
```

Keep the branch limited to the linked task. Update it safely when the base
branch changes, resolve conflicts deliberately, and never overwrite another
contributor's work.

## Implementation principles

- Prefer small, cohesive changes with clear ownership and boundaries.
- Follow the established architecture before introducing a new dependency,
  framework, service, or pattern.
- Keep business and legal metric rules in the backend. The frontend presents
  API results and must not independently redefine analytical calculations.
- Never use fabricated values as a fallback for unavailable production data.
  Use explicit loading, empty, unavailable, error, or partial-data states.
- Treat accessibility, responsive behavior, security, error handling, and data
  quality as implementation requirements rather than optional polish.
- Reuse approved components, colors, spacing, typography, and interaction rules
  from the [Design Standards Guide](../design/datumlex-design-guide.pdf).
- Write code and documentation in English. Use clear names and comments only
  where they explain intent or a non-obvious decision.
- Update affected documentation together with the implementation.

## Validation by area

### Frontend

- Check the relevant screen at desktop and mobile widths.
- Verify keyboard navigation, visible focus, labels, contrast, and feedback
  states.
- Validate loading, error, empty, unavailable, and partial-data behavior.
- Reconcile filters, cards, and charts with the API contract and real responses
  when integration is part of the scope.
- Run the configured build, lint, unit, and UI test commands.

### Backend and API

- Validate request parameters, response schemas, authorization, errors, empty
  results, and unavailable dependencies.
- Keep API behavior consistent with its documented contract.
- Add meaningful unit and integration tests for changed logic.
- Avoid leaking credentials, internal exceptions, or sensitive data.

### Data and database

- Preserve the agreed grain, keys, constraints, lineage, and classification
  rules.
- Test migrations and transformations on a representative sample.
- Check duplicates, null handling, referential integrity, idempotency, totals,
  exclusions, and reconciliation.
- Update the dimensional model or data dictionary when structures change.

### Documentation and design

- Verify links, examples, terminology, rendering, and intended audience.
- Record assumptions, limitations, source references, and versioned evidence.
- Ensure the artifact is indexed from the appropriate folder README.

## Commits

Commits must be written in English and follow
[Commit Standards](commit-standards.md) and Conventional Commits:

```text
<type>(<optional scope>): <short summary>
```

Make one logical change per commit. Use the body to explain important rationale
and `Refs #<issue>` when the commit contributes to an item without completing
it. Use `Resolves #<issue>` only when the entire issue is genuinely satisfied.

Before committing, confirm that the author identity is the contributor's own
configured Git identity. Automated assistants must not replace the human
author's identity or add attribution that the team did not request.

## Pull Request workflow

1. Push the branch and open a focused Pull Request (PR).
2. Use an English Conventional Commit-style PR title.
3. Explain the problem, solution, scope, validation, screenshots or evidence,
   known limitations, and linked issue.
4. Confirm that required checks pass and move the task to `In review` only when
   the deliverable is ready for independent review.
5. Add a comment to the related card with the PR and validation links.
6. Follow the [QA and Pull Request Review Guide](qa-guide.md), respond
   to findings, and request another review after material corrections.
7. Merge only after approval and required checks. Delete the merged branch when
   it is no longer needed.

No direct commit to `main` is permitted. A PR being open or merged does not, by
itself, prove that the issue is complete.

## Evidence and board updates

The GitHub issue is the durable record of the work. Add factual comments when
implementation starts, a blocker appears, a PR is ready, changes are requested,
validation finishes, or the item is completed.

Use this concise handoff format:

```markdown
## Development handoff
- Implemented: <behavior or artifact>
- Remaining: <work or none>
- Pull Request / commit: <links>
- Validation: <commands, checks, environment, and results>
- Documentation: <links or N/A with reason>
- Known limitations: <details or none>
- Ready for: Review / QA / Integration
```

Do not mark partially integrated work as complete. For example, a finished
dashboard shell may be valid implementation progress, while API binding and
real-data reconciliation remain explicit completion dependencies.

## Completion checklist

Before requesting final approval, confirm that:

- [ ] Acceptance criteria are satisfied or remaining work is explicitly linked.
- [ ] Applicable automated and manual validation passes.
- [ ] Documentation and contracts match the implementation.
- [ ] The PR, commit, screenshots, reports, and limitations are linked on the card.
- [ ] An independent reviewer has the information required to reproduce the result.
- [ ] The item satisfies the [Definition of Done](../agile/definition-of-done.md).

Move the item to `Done` only after required review, merge, integration,
deployment, validation, and acceptance are recorded.

## Estimation responsibilities

Participate in [Planning Poker](../agile/estimation-and-prioritization.md) for the
complete parent story and include implementation, validation, review, documentation,
and integration. `estimativa` contains agreed story points, not hours. Leave child
tasks and epics blank; use task timeboxes where needed. Raise new uncertainty or
scope changes explicitly rather than adjusting points to justify elapsed time.

## Quick links

- [Product Backlog](https://github.com/orgs/DatumLex/projects/1)
- [DatumLex core issues](https://github.com/DatumLex/datumlex-core/issues)
- [Technology Stack](../architecture/technology-stack.md)
- [Design Standards](../design/datumlex-design-guide.pdf)
- [Branch Standards](branch-standards.md)
- [Commit Standards](commit-standards.md)
- [QA Guide](qa-guide.md)
- [Definition of Ready](../agile/definition-of-ready.md)
- [Definition of Done](../agile/definition-of-done.md)
