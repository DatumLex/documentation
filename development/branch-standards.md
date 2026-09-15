# 🌿 Branch Standards — DatumLex

To keep the repository organized and make it easy to identify what each branch is for, all branches in the **DatumLex** project must follow a consistent naming pattern, written in **English**.

## ✍️ Branch Naming Format

For work in the **documentation repository/folder**, use the area prefix:

```text
documentation/<issue-number>-<short-description>
```

The issue number is optional. For example, `documentation/backlog-estimation`
or `documentation/74-api-reference`. This applies to all documentation subfolders,
including `agile/`, `product/`, `architecture/`, and `development/`.
Create or rename the branch before committing documentation work. Do not use
`codex/` or `docs/` for this area. Commit and PR titles still use Conventional
Commits, such as `docs(planning): align stories and estimation`.

For other areas, follow their documented area-specific convention. Where none
is defined, the existing type-based convention below remains the fallback:

```
<type>/<issue-number>-<short-description>
```

- **type**: one of the allowed types below.
- **issue-number** (optional but encouraged): the related GitHub issue/User Story number, so the branch is traceable to the board.
- **short-description**: lowercase, words separated by hyphens, no articles or filler words.

*(e.g. `feat/34-court-filter-dashboard`, `fix/41-null-publication-dates`)*

## 🏷️ Allowed Branch Types

| Type | Use for |
|---|---|
| **`feat`** | A new feature |
| **`fix`** | A bug fix |
| **`refactor`** | Code restructuring with no change to external behavior |
| **`perf`** | A performance improvement |
| **`docs`** | Documentation-only changes |
| **`test`** | Adding or fixing automated tests |
| **`chore`** | General maintenance, config, or dependency updates |
| **`hotfix`** | Urgent fix applied directly against production/main |
| **`release`** | Preparing a release (e.g. `release/1.2.0`) |

## 🌳 Base Branches

- **`main`**: always stable and deployable. No direct commits — only merges via reviewed Pull Requests.
- **`develop`** *(if adopted by the team)*: integration branch for features before they reach `main`.

All `documentation`, `feat`, `fix`, `refactor`, `perf`, `docs`, `test`, and `chore` branches are created from `develop` (or `main`, if the team is not using a `develop` branch) and merged back via Pull Request. The `docs` fallback does not apply to the documentation area, which uses `documentation/`.

`hotfix` branches are created directly from `main` and merged back into both `main` and `develop` once resolved.

## 🔗 Linking to Issues

Whenever possible, include the issue number in the branch name so it's traceable to the GitHub Project board, and reference the issue again in the Pull Request description (e.g. `Resolves #34`).

## 🔀 Pull Requests

- Every branch must be merged via Pull Request — no direct pushes to `main`.
- The PR title should follow the same convention as commit messages (e.g. `feat: add court filter to precedent trends view`).
- At least one team member should review before merging.
- Delete the branch after merging to keep the repository clean.

## ✅ Examples

```
feat/34-court-filter-dashboard
fix/41-null-publication-dates
refactor/nlp-theme-classifier
documentation/update-data-dictionary
documentation/backlog-estimation
hotfix/etl-pipeline-crash
release/1.2.0
```
