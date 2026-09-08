# 📋 Agile

This folder holds the artifacts related to how the LegacyTech team plans, prioritizes, and tracks work on **DatumLex** using Scrum.

## Contents

- **`definition-of-ready.md`** — the team's fixed checklist defining when a User Story is ready to enter a Sprint.
- **`definition-of-done.md`** — the team's fixed checklist defining when an increment is truly finished.
- **`sprint-<n>-user-stories.md`** *(one per sprint)* — the User Stories worked on in that sprint, each with its DoR checklist filled in and its acceptance criteria written out (Gherkin format: `Dado / Quando / Então`).

## What does NOT live here

- The live Product Backlog and Sprint Backlog — these are managed as a **GitHub Project** linked to the code repository, not as static files.
- Sprint retrospective notes or meeting minutes, unless the team decides to formalize them as an artifact (in which case they'd go in a `retrospectives/` subfolder).

## Why it matters

DoR and DoD are team-wide agreements that don't change per sprint — they're the "quality gates" for entering and leaving development. The per-sprint User Story files are where those gates get applied to actual work, and are also the evidence submitted to the FATEC evaluators for the Sprint deliverables.