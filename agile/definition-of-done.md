# ✅ Definition of Done (DoD) — DatumLex

The **Definition of Done** is the team's shared quality standard for when an increment (a User Story, a task, or the sprint deliverable as a whole) is truly finished — not just "coded," but ready to be considered part of the product. Unlike the Definition of Ready, the DoD is official in the Scrum Guide and is mandatory.

The DoD is **fixed for the whole team** and does not change per sprint (it can evolve over time as the team matures, but it isn't redefined story by story).

An item is considered **Done** when all applicable items below are true:

## 📋 Checklist

### Code
- [ ] Code implemented according to the acceptance criteria defined in the story.
- [ ] Code reviewed and approved via Pull Request by at least one team member other than the author.
- [ ] Static code analysis run, with no unresolved critical/high-severity issues (per the Xertica non-functional requirement).
- [ ] No hard-coded secrets, credentials, or environment-specific values committed.

### Tests
- [ ] Automated unit tests written and passing for new/changed logic.
- [ ] Automated integration tests written and passing where the change crosses component boundaries (e.g. ETL step → Data Warehouse, API → database).
- [ ] Automated system-level tests (API and/or UI) added or updated when the change affects an external-facing behavior.
- [ ] All existing automated tests still pass (no regressions).

### Data & ETL (when applicable)
- [ ] ETL pipeline runs end-to-end against a representative sample without errors.
- [ ] Data quality checks pass (e.g. no unexpected nulls in required fields, referential integrity between fact and dimension tables holds).
- [ ] Dimensional model changes (if any) are reflected in the data dictionary.

### Documentation
- [ ] Minimum documentation updated: README, API documentation (endpoints, request/response), and/or data dictionary, as relevant to the change.
- [ ] Any new environment variable, dependency, or setup step documented.

### Delivery
- [ ] Merged into the target branch following the [Branch Standards](./../devops/branch-standards.md).
- [ ] Commit history follows the [Commit Standards](./../devops/commit-standards.md).
- [ ] Deployed/validated in the staging/homolog environment (when the team has one available).
- [ ] Product Owner has reviewed the increment against the story's acceptance criteria and accepted it.

## 📝 Note

Only work that satisfies every applicable item above can be counted as part of the Sprint's completed increment. A story that is "coded but untested" or "tested but undocumented" is **not Done** — it stays in progress until every checklist item is satisfied.
