# Definition of Ready (DoR) — DatumLex

## Purpose

Definition of Ready is the team's agreement on what must be understood and available before work starts. It reduces interruptions caused by unclear scope, missing inputs, and unresolved dependencies. DoR is a local working agreement, not a mandatory Scrum artifact. It supports refinement without requiring every implementation detail to be decided in advance.

DoR answers **“Can we start this item responsibly?”** [Definition of Done](definition-of-done.md) answers **“Does the result meet our quality standard?”** Acceptance criteria describe the specific result expected from one issue; neither checklist replaces them.

This agreement applies across sprints and can evolve through reviewed team decisions. A new sprint does not require a new DoR.

## Scope and responsibilities

- **User Stories:** clarify value, scope, acceptance criteria, feasibility, and delivery plan during refinement and Sprint Planning. A story may contain dependent tasks sequenced within the sprint.
- **Tasks:** check the inputs required for that particular task before moving it to `Ready`. Later story integration requirements need not block independent work whose own inputs are available.
- **Epics:** group a product objective and related stories. They may span multiple sprints; their entire scope need not be specified before a child story starts.

The PO validates story value and acceptance criteria. Assignees and relevant reviewers confirm technical readiness. Ed Wilson supports refinement and impediment removal. Routine tasks inherit agreed story scope without needing separate PO approval for every technical detail.

## Readiness checklist

- [ ] **Clear outcome and scope:** purpose, boundaries, and parent story/epic are identified where applicable.
- [ ] **Verifiable acceptance criteria:** expected behavior or deliverables, including relevant failure and edge cases, are explicit. Use `Given / When / Then` where helpful; documentation or research can use deliverable checklists.
- [ ] **Sufficient rules and inputs:** required references, business rules, data types/sources, validation, null handling, or contracts are linked. Unknowns being investigated are explicit research questions.
- [ ] **Start dependencies resolved:** prerequisite issues and required outputs are linked, with evidence that inputs are available. Accepting a risk does not make an unavailable input available.
- [ ] **Access available:** required tools, repository permissions, environments, and source access work. Reference secret configuration instructions without exposing credentials.
- [ ] **Feasible plan:** assignee, estimate or timebox, planned start/end dates, capacity, sequencing, and review time are understood. Split oversized work.
- [ ] **Validation planned:** identify applicable tests or artifact checks, expected results, and evidence location.
- [ ] **Scope aligned:** the PO has validated the story; the assignee and relevant reviewers understand the task and its start conditions.

Record `N/A — <reason>` for an inapplicable criterion. Do not check an unmet requirement or use N/A to hide a blocker. Clarify missing information during refinement before treating an item as executable; ambiguity is not automatically a dependency on another task.

## Required inputs by type of work

| Work | Inputs needed to start |
|---|---|
| Research / feasibility | Question, source, timebox, expected evidence or decision. The answer need not be known before research begins. |
| Modeling / dictionary | Source evidence, agreed grain, and prior modeling artifacts where required. The artifact being created is not its own prerequisite. |
| ETL / database implementation | Relevant reviewed model/dictionary baseline, source/target mapping, deduplication and quality rules, reproducible sample. |
| API | Contract, parameter/error semantics, metric rules, and required data access. |
| Dashboard / UI | Mockup/design references, API contract, filter behavior, loading/error/empty/unavailable states. |
| Automated tests | Scenarios, independently checked expected results, fixtures, runnable target when execution requires it. Test design can start earlier. |
| Deployment | Deployable version, platform access, configuration, health checks, recovery approach. Provisioning can be an earlier separate task. |
| Documentation | Audience, scope, authoritative references, file location, review criteria. |

Approved contracts and clearly labeled fixtures can enable independent frontend or test development. They do not satisfy later real-data integration requirements. Record **start prerequisites** separately from **completion dependencies** to make parallel work explicit.

## Board transitions

| Status | Meaning in DatumLex |
|---|---|
| `Backlog` | Execution waits on another item or required input. Record the blocker and next action. |
| `Ready` | Applicable readiness criteria hold and no unresolved dependency prevents starting. |
| `In progress` | The assignee has actually started work. |
| `In review` | The deliverable and validation evidence are ready for review; work is not yet Done. |
| `Done` | Applicable DoD and issue-specific acceptance criteria are satisfied. |

Before `Backlog → Ready`, the assignee checks prerequisite outputs and records evidence. Move to `In progress` when execution begins. If a new dependency pauses execution, record it and return the item to `Backlog`, preserving progress and identifying the action needed to resume. A planned date does not change readiness or prove that work has started.

## Applying the policy to issues

The [GitHub Project](https://github.com/orgs/DatumLex/projects/1) is the live source for status, assignees, and dates. Existing task sections such as **Work and acceptance**, **Dependencies**, and **Evidence** remain the item-specific requirements. Reference this policy and add a brief readiness record instead of maintaining competing definitions in each task.

```markdown
## Readiness review
Policy: https://github.com/DatumLex/documentation/blob/main/agile/definition-of-ready.md
- Scope and acceptance criteria: <link or section>
- Start prerequisites: <issue → required output → evidence available>
- Completion dependencies: <later integration/validation requirements>
- Access, estimate/timebox, assignee and dates: <record>
- Validation approach: <scenarios/checks and evidence location>
- N/A items: <criterion and reason, or none>
- Reviewed by / date: <name / YYYY-MM-DD>
- Decision: Ready / Blocked — <remaining blocker and next action>
```

For example, [task #30](https://github.com/DatumLex/datumlex-core/issues/30) investigates DataJud access. It needs a defined query scope, access method, and evidence expectations to start, not a successful collection before investigation begins. [Task #54](https://github.com/DatumLex/datumlex-core/issues/54) can build cards against an available contract and fixtures, while validation against real responses remains a completion condition.

## References

- [Definition of Done](definition-of-done.md)
- [Agile index](README.md)
- [Scrum Guide — Product Backlog and Sprint Planning](https://scrumguides.org/scrum-guide.html)
