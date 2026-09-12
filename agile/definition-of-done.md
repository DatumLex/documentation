# Definition of Done (DoD) — DatumLex

## Purpose

Definition of Done is the shared quality standard for a usable product Increment and a commitment defined by Scrum. DatumLex applies the relevant checks below to tasks and stories so their outputs can contribute to that Increment. Finishing a task alone does not mean a usable Increment has been delivered.

DoD answers **“Is the result complete, verified, and traceable?”** [Definition of Ready](definition-of-ready.md) addresses whether work can start. Acceptance criteria specify what one issue must deliver; DoD adds common quality conditions. A task's existing **“Done when…”** sentence is an item-specific criterion, not a replacement for this policy.

This standard applies across sprints and can evolve through reviewed team agreements. Sprint scope changes do not justify lowering quality or silently waiving requirements.

## Common completion checklist

- [ ] **Acceptance criteria satisfied:** each applicable criterion has verifiable evidence; no unresolved defect prevents the agreed outcome.
- [ ] **Deliverable versioned and linked:** the issue references the document, diagram, source change, report, or deployed artifact and relevant version/commit.
- [ ] **Independent review complete:** at least one teammate other than the author has approved the change, with required corrections resolved and review recorded.
- [ ] **Applicable validation passes:** tests or artifact checks below have been executed and results linked. A screenshot or unchecked checklist alone does not prove success.
- [ ] **Documentation matches the result:** affected instructions, contracts, models, dictionary entries, decisions, limitations, and environment configuration are updated.
- [ ] **No secrets exposed:** credentials are absent from commits, reports, samples, screenshots, and logs. Evidence includes only data needed to reproduce the result.
- [ ] **Repository delivery rules followed:** changes are merged through a reviewed PR into the target branch following [Branch Standards](../devops/branch-standards.md) and [Commit Standards](../devops/commit-standards.md).
- [ ] **Evidence recorded before closing:** validation, reviewer, N/A reasons, and any non-blocking follow-ups are linked in the issue.

Mark an inapplicable check `N/A — <reason>` and have the reviewer confirm it. Documentation-only changes need content and link review, not unrelated application tests. An unavailable test environment, failed required test, or missing required deployment is a blocker, not N/A.

## Additional checks by type of work

### Code and automated quality

- [ ] New/changed logic has meaningful automated unit tests; relevant integration tests cover component boundaries and persistence.
- [ ] External behavior changes have appropriate automated system tests: HTTP scenarios for the running API and browser scenarios for UI behavior.
- [ ] Relevant regression suites pass for the reviewed version; reports identify commit, commands/CI run, environment, and result.
- [ ] Static analysis meets project quality rules, with no unresolved critical/high-severity findings. Relevant configured CI checks pass; missing required CI remains work to complete.
- [ ] Dependencies and configuration are reproducible and documented, without hard-coded secrets or machine-specific values.

### Data modeling, dictionary, and ETL

- [ ] Affected conceptual, logical, physical, and dictionary artifacts are consistent, readable, versioned, and reviewed before dependent implementation begins.
- [ ] The dictionary covers relevant tables, fields, types, keys, constraints, relationships, meanings, and lineage.
- [ ] Applicable ETL runs on a representative real sample; source, query scope, collection time, and refresh metadata are traceable.
- [ ] Quality checks cover grain, duplicates, required fields, referential integrity, and reconciliation. Loading/migrations satisfy agreed idempotency and recovery requirements.
- [ ] Classification and denominators follow documented rules. Unknown or missing evidence is not silently treated as denied; exclusions and limitations are recorded.

### API and dashboard

- [ ] API behavior matches its contract, including invalid inputs, errors, empty results, and unavailable data.
- [ ] Dashboard values and filters reconcile with the API and underlying data; loading/error/empty/unavailable states are verified.
- [ ] Relevant responsive behavior, accessibility checks, and approved visual references are verified.
- [ ] Development fixtures are clearly identified. Features requiring real data are validated with real responses; illustrative values are not a production fallback.

### Documentation, research, and design

- [ ] The artifact explains purpose, scope, decisions/findings, and limitations, with supporting references.
- [ ] Examples, links, diagrams, and instructions are checked for the intended audience; relevant generated artifacts are reproducible.
- [ ] Files use the appropriate folder and are discoverable from its index. Research distinguishes findings, assumptions, and unresolved questions.
- [ ] A qualified teammate reviews correctness and consistency. Research may finish with an evidenced negative result; a dependent feature cannot claim success on that basis.

### Deployment and operations

- [ ] Required deployment succeeds for the agreed environment/version, with service URLs and configuration documented.
- [ ] Applicable deployed smoke checks pass; setup, environment variables, execution, and recovery are documented without secret values.
- [ ] Evidence identifies the tested release/commit and linked API/UI test results.

## Completion at each level

| Level | Completion condition |
|---|---|
| Task | Its deliverable, acceptance criteria, and applicable checks are satisfied. A documentation task does not wait for unrelated deployment. |
| User Story | Required child tasks and story criteria are satisfied, the result is integrated and validated, and PO acceptance is recorded as a DatumLex agreement. |
| Epic | Its product objective and agreed story scope are satisfied. It may span sprints; a sprint boundary does not close it. |
| Sprint Increment / release | The integrated result meets shared DoD and agreed delivery scope. Finished tasks do not replace integrated validation. |

For **Sprint 1**, release evidence must link the reviewed conceptual/logical/physical models and dictionary, stack and court-selection rationale, API and execution documentation, real DataJud validation, passing automated unit/integration and system-level API/UI tests, static analysis results, and Vercel frontend plus Railway backend/database deployment and smoke evidence. This is the sprint's delivery scope, not a separate DoD. [Task #89](https://github.com/DatumLex/datumlex-core/issues/89) assembles references; it does not replace the underlying checks.

## Review and board workflow

1. The assignee completes the deliverable, performs applicable validation, attaches evidence, and moves `In progress → In review`.
2. A reviewer checks the artifact and evidence. Diego coordinates QA, technical owners review their domains, and Ed Wilson supports documentation and traceability. Quality remains a team responsibility.
3. Corrections requiring active work return the item to `In progress`. If a dependency pauses work, record it and use `Backlog` under the [DoR workflow](definition-of-ready.md#board-transitions).
4. After review, merge, and required deployment/acceptance, record completion and move to `Done`. Opening or merging a PR, reaching a planned date, or automatically closing an issue does not by itself prove DoD; check actual evidence.

PO acceptance of stories is a team agreement. It does not waive quality checks, require PO approval for every technical task, or make Sprint Review a release approval gate. Work failing DoD is not counted as a completed Increment.

## Completion evidence template

Use the existing **Evidence** or **Completion evidence** section. Reference this policy instead of maintaining competing copies.

```markdown
## Completion evidence
Policy: https://github.com/DatumLex/documentation/blob/main/agile/definition-of-done.md
- Acceptance criteria results: <criterion → evidence>
- Deliverable / merged PR / version: <links>
- Tests or artifact checks: <commands/CI run, environment, result>
- Documentation and data/model changes: <links or N/A with reason>
- Deployment and smoke checks: <version, URLs, results or N/A with reason>
- Independent reviewer / review record: <name and link>
- PO acceptance: <story record or N/A for routine task>
- N/A criteria and reasons: <reviewed list, or none>
- Non-blocking follow-ups: <issues, or none>
- Completion date: <YYYY-MM-DD>
```

## References

- [Definition of Ready](definition-of-ready.md)
- [Agile index](README.md)
- [Scrum Guide — Increment and Definition of Done](https://scrumguides.org/scrum-guide.html#increment)
