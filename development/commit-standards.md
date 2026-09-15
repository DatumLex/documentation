# 📌 Commit Standards — DatumLex

To maintain a clean and traceable repository history, all commits for the **DatumLex** project must be written in **English**, following the [Conventional Commits](https://www.conventionalcommits.org/) convention.

Each commit should be small, descriptive, and objective — one logical change per commit.

## ✍️ Commit Message Format

```
<type>(<optional scope>): <short summary>

<optional body>

<optional footer>
```

- **Summary**: imperative mood, lowercase, no period at the end, ideally under 72 characters.
  *(e.g. `feat(search): add semantic search by legal topic`)*
- **Body** (optional but encouraged for non-trivial changes): explain **why** the change was made, not just what changed.
- **Footer** (optional): issue references, breaking changes, co-authors.

## 🏷️ Allowed Commit Types

| Type | Use for |
|---|---|
| **`feat`** | A new feature |
| **`fix`** | A bug fix or correction of unexpected behavior |
| **`refactor`** | Code restructuring with no change to external behavior |
| **`perf`** | A change that improves performance |
| **`style`** | Formatting, whitespace, linting — no logic change |
| **`docs`** | Documentation only (README, agile artifacts, data dictionary, etc.) |
| **`test`** | Adding or fixing automated tests (unit, integration, API, UI) |
| **`build`** | Changes to dependencies, build tooling, or packaging |
| **`ci`** | Changes to CI/CD pipeline configuration |
| **`chore`** | General maintenance that doesn't fit the categories above |
| **`revert`** | Reverting a previous commit |

## 💥 Breaking Changes

If a commit introduces a breaking change (e.g. an API contract change, an ETL schema change), add a footer:

```
BREAKING CHANGE: <description of what breaks and how to adapt>
```

## 🔗 Linking Issues

When a commit resolves a specific Task or User Story on the GitHub Project board, reference it in the footer to automate board tracking:

```
Resolves #12
```

Use `Refs #12` instead if the commit is related to the issue but doesn't fully resolve it.

## 📊 Traceability and Progress

Commit history is one input for tracking active work on the repository, but **it is not used as a standalone metric of individual contribution**. Sprint progress and individual delivery are tracked through the GitHub Project board (issue status, story points, sprint burndown) — not by counting commits, which can be easily gamed and doesn't reflect actual effort or quality.

## ✅ Examples

```
feat(dashboard): add court filter to precedent trends view

fix(etl): handle null publication dates from DataJud feed

Resolves #34

docs: update data dictionary with new dimension tables

refactor(nlp): extract legal-theme classifier into its own module
```
