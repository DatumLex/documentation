# ⚙️ DevOps

This folder documents the practices and tooling the LegacyTech team uses to keep the **DatumLex** codebase consistent, traceable, and maintainable — as required by the challenge's non-functional requirements around DevOps.

## Contents

- **`commit-standards.md`** — the Conventional Commits-based convention every commit must follow (types, message format, issue linking).
- **`branch-standards.md`** — the branch naming convention, base-branch strategy (`main`/`develop`/`hotfix`/`release`), and Pull Request rules.
- **CI/CD pipeline documentation** *(to be added)* — what runs automatically on push/PR: static code analysis, automated tests (unit, integration, system-level), and any deployment steps.
- **Tooling justifications** — for each DevOps tool adopted (CI provider, static analysis tool, testing frameworks), a short explanation of why it was chosen, as required by the challenge ("apply DevOps concepts and define tools with technical justification for each").

## Why it matters

The challenge explicitly grades the team's ability to justify DevOps tooling choices, not just use them. This folder is where that justification lives, alongside the day-to-day conventions (commits/branches) that keep the two repositories (`documentation` and the code monorepo) consistent across all 5 team members.