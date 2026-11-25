# QA and Pull Request Review Guide — DatumLex

This guide defines how the team validates work before it is merged. Its purpose
is to keep `main` stable, make deliveries traceable, and ensure that a completed
card has evidence of review—not only a changed status.

## Roles and independence

- The author prepares the branch, Pull Request (PR), and supporting evidence.
- A reviewer validates the change. Whenever possible, the reviewer must not be
  the PR author.
- QA validates the acceptance criteria, expected behavior, and regression risk.
  A team member may perform QA for a small team, but the validation must still
  be recorded on the related card.
- Only an approved PR may be merged into `main`, following the branch standards.

## Before requesting review

The author must confirm that the PR:

- is linked to its GitHub issue, task, or user story;
- has a clear English title and description explaining the change and its
  purpose;
- includes relevant screenshots, test results, or other validation evidence;
- has the related card in **In review**; and
- is small enough to be reviewed with confidence, or clearly explains why it
  needs to be larger.

## How to review a PR

1. Read the linked card, acceptance criteria, and PR description.
2. Inspect the changed files for correctness, clarity, maintainability,
   security, and adherence to the project standards.
3. Validate the behavior when possible. For a frontend change, check the
   relevant screen and responsive behavior; for backend or data work, run or
   inspect the applicable tests and data validation.
4. Check that the evidence in the PR and card actually supports the claimed
   result.
5. Leave inline comments for specific findings and choose the appropriate PR
   decision: approve, request changes, or comment.

## Recording work on cards

**Every meaningful QA or review action must be recorded as a comment on the
related GitHub Project card/issue.** Comments are part of the project evidence
and must be written in English.

At minimum, add a card comment when:

- the PR is opened for review;
- QA starts or identifies a blocker;
- changes are requested;
- validation is completed;
- the PR is approved or rejected; and
- the item is moved to **Done** after merge.

Use a concise, factual format:

```text
QA review — PR #<number>
Scope checked: <what was reviewed>
Evidence: <test, screenshot, link, or result>
Outcome: Approved / Changes requested / Blocked
Notes: <short rationale or next action>
```

Example:

```text
QA review — PR #17
Scope checked: dashboard filters and empty indicators
Evidence: manual browser validation and production build
Outcome: Approved
Notes: empty values display "-" as specified; no blocker found.
```

## PR decisions

| Decision | Use when | Required follow-up |
|---|---|---|
| **Approve** | Acceptance criteria are met and no blocking issue remains. | Add the card comment and wait for merge. |
| **Request changes** | A defect, missing requirement, or material risk must be fixed before merge. | Describe the issue clearly in the PR and card. Re-review after the update. |
| **Comment** | Feedback is non-blocking or needs clarification. | State whether it blocks approval; do not leave ambiguity. |

An approval is not a substitute for testing. If something cannot be tested,
record the limitation and agree on the follow-up before merging.

## Closing the work item

After merge, the author or QA reviewer must:

1. Confirm that the merged result corresponds to the reviewed PR.
2. Add a final card comment with the PR link and validation outcome.
3. Move the card to **Done** only when the Definition of Done is satisfied.
4. Record any deferred issue as a new linked card; do not hide it in a comment.

## Automated Quality Gates (CI/CD & SonarCloud)

Every Pull Request into `main` is verified automatically before human review approval:

1. **Automated Test Suite (`python scripts/test-report.py`)**: runs **400+ automated tests** across both Linux and Windows runners (backend Django/pytest unit & integration tests including NLP engine and append-only evidence integrity, frontend Node unit tests, and ETL/collector validation tools), producing an interactive HTML coverage dashboard (`backend/tests/relatorio-cobertura.html`) plus Sonar-compatible `backend-coverage.xml`, `backend-junit.xml`, and `frontend-lcov.info`.
2. **Static Analysis & Linting**: `ruff check backend/src --select F` (Python) and `npm --prefix frontend run lint` (ESLint) must pass with zero critical errors, alongside `npm --prefix frontend run build`.
3. **SonarCloud Quality Gate (`DatumLex_datumlex-core`)**: [public SonarCloud dashboard](https://sonarcloud.io/project/overview?id=DatumLex_datumlex-core) analyzes Security, Reliability, and Maintainability on every PR using `.sonarcloud.properties` and `sonar-project.properties`. A PR must pass the Quality Gate (`0 Bugs`, `0 Vulnerabilities`) before merge.

## Quick reviewer checklist

- [ ] Card, acceptance criteria, and PR are linked.
- [ ] Change follows branch and commit standards.
- [ ] Automated CI checks (tests, lint, build) and SonarCloud Quality Gate are **PASSED**.
- [ ] Relevant behavior was validated and evidence is available.
- [ ] Findings are clear, actionable, and recorded.
- [ ] A QA/review comment exists on the card.
- [ ] PR approval or requested changes match the evidence.
- [ ] Card moves to **Done** only after merge and final validation.

## Quality and estimation

QA effort belongs in story-level `Estimate` under the
[estimation agreement](../agile/estimation-and-prioritization.md). Do not count the
same tests in both a feature story and a shared test-infrastructure story. Priority
does not waive validation: a Should Have export still requires safe content and
reconciliation, and a Should Have NLP feature still requires evidence and quality checks.
Count completed points only when the whole story meets DoD, never when isolated
tasks or PRs finish.

## Related documents

- [Branch Standards](branch-standards.md)
- [Commit Standards](commit-standards.md)
- [Definition of Ready](../agile/definition-of-ready.md)
- [Definition of Done](../agile/definition-of-done.md)
