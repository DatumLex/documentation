# 🌿 Branch Standards — DatumLex

To keep the repository organized and make it easy to identify what each branch is for, all branches in the **DatumLex** project must follow a consistent naming pattern, written in **English**.

## ✍️ Branch Naming Format

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

All `feat`, `fix`, `refactor`, `perf`, `docs`, `test`, and `chore` branches are created from `develop` (or `main`, if the team is not using a `develop` branch) and merged back via Pull Request.

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
docs/update-data-dictionary
hotfix/etl-pipeline-crash
release/1.2.0
```
