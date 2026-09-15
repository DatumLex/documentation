# Technology Stack and Rationale

## Purpose

This document records the technologies adopted for DatumLex and the reasoning
behind each choice. It is a living architectural decision record: whenever a
material technology choice changes, this document must be updated together
with the relevant implementation and pull request.

DatumLex is a legal analytics platform that ingests judicial data, stores it in
a structured analytical database, and presents a web dashboard for exploring
appeal outcomes. The stack prioritizes clarity, maintainability, traceability,
and an accessible user experience for the scope of the project.

## Stack at a Glance

| Area | Technology | Primary responsibility |
|---|---|---|
| Backend and data processing | Python | API logic, data transformation, and integration workflows |
| Backend framework | Django | Structured web application and API foundation |
| Frontend language | JavaScript | Browser-side interface behavior |
| Frontend framework | React | Reusable dashboard components and UI state |
| Frontend styling | Tailwind CSS | Responsive, consistent interface styling |
| Relational database | PostgreSQL | Persistent analytical and application data |
| Frontend hosting | Vercel | Preview and production deployment of the dashboard |
| Backend and database hosting | Railway | Django API and PostgreSQL deployment |
| Source control and planning | GitHub | Repositories, issues, project board, pull requests, and review history |
| External legal data | DataJud / CNJ | Judicial records used by the project scope |

## Technology Decisions

### Python for the Backend and Data Workflows

Python is used for backend services and data-processing routines because it is
well suited to data ingestion, transformation, analysis, and API development.
Its ecosystem supports common tasks required by DatumLex, such as consuming
external services, handling structured data, validating records, and preparing
data for database loading.

Using Python also keeps the backend and ETL-related logic in one language. This
reduces context switching for the team and makes the data flow easier to trace:
extract data, validate it, transform it, persist it, and expose the resulting
metrics through an API.

### Django as the Backend Framework

Django provides a convention-based foundation for the backend, including data
models, migrations, administration features, validation, security defaults,
and a clear project structure. These conventions are valuable for a team
project because they make responsibilities and code locations predictable.

Django is also appropriate for a data-centered application that needs stable
database integration and documented API endpoints. It allows the team to begin
with a focused dashboard API and grow the application without introducing an
unnecessary collection of services.

### JavaScript and React for the Frontend

JavaScript is the browser-native language used by the frontend. React is used
to organize the dashboard into reusable components such as filters, metric
cards, chart states, and information popovers.

This component model keeps the interface adaptable while the API evolves. The
frontend can render explicit loading, empty, unavailable, and error states
without fabricating analytical results. When the API contract becomes stable,
mocked values can be replaced by real data with minimal change to the visual
components.

### Tailwind CSS for Frontend Styling

Tailwind CSS is used to build a consistent, responsive UI without creating a
large collection of one-off stylesheet rules. Its utility-first approach helps
the team apply approved spacing, colors, typography, borders, focus states,
and responsive layouts close to the components that use them.

For DatumLex, this improves visual consistency with the approved dashboard
mockup and makes it easier to maintain an accessible design system. Tailwind
does not replace design decisions; the project still documents its palette,
component behavior, and accessibility requirements in the `design/` folder.

### PostgreSQL for Persistent Data

PostgreSQL is the relational database for structured application and analytical
data. It was chosen because it is mature, reliable, open source, and provides
strong support for SQL, constraints, indexing, transactions, and analytical
queries.

These capabilities are important for judicial data, where consistent
relationships, repeatable calculations, and traceable transformations matter.
PostgreSQL also integrates naturally with Django and supports incremental
evolution of the dimensional model through migrations.

### Vercel for Frontend Deployment

Vercel hosts the frontend and provides deployment previews for pull requests.
Preview deployments allow the team and reviewers to validate interface changes
in a browser before merging them, which supports a documented review process.

The platform is especially appropriate for the React dashboard because it
offers a simple deployment workflow and separates the static frontend delivery
from the backend API deployment. Environment configuration must never expose
secrets in the browser; public API configuration is managed through approved
environment variables.

### GitHub for Code, Planning, and Collaboration

GitHub is the system of record for source code and the team workflow. It hosts
the `datumlex-core` code repository and this `documentation` repository, while
also providing Issues, GitHub Projects, Pull Requests, code review, branch
protection, and the commit history.

This centralizes traceability from product work to implementation:

1. An epic, user story, or task is defined on the GitHub Project board.
2. A branch follows the documented branch naming standard and references the
   related issue when possible.
3. Conventional Commits and pull requests link the implementation back to the
   issue.
4. Review and validation evidence are retained in the pull request.

The detailed rules are maintained in the [Development documentation](../development/README.md).

## Architecture Boundaries

- The frontend is responsible for presentation, interaction, and clear data
  states; it must not calculate legal metrics independently of the backend.
- The backend is responsible for exposing validated metrics and documented API
  contracts.
- PostgreSQL is the persistent source for processed project data; raw external
  data must be handled through documented ingestion and transformation steps.
- Vercel deploys the frontend; Railway hosts backend and PostgreSQL. Configure
  access independently and follow project security practices.
- GitHub records work and review evidence; it is not a replacement for the
  database or for runtime monitoring.

## Decision Review Criteria

Any future stack change should be evaluated against the following criteria:

- Alignment with the project scope and academic requirements.
- Ability to keep data transformations traceable and reproducible.
- Accessibility, responsiveness, and maintainability of the dashboard.
- Security of credentials, user data, and deployment configuration.
- Cost, learning curve, and operational overhead for the team.
- Compatibility with the documented branch, commit, review, and deployment
  workflow.

## Sprint boundaries and planning

Sprint 1 uses DataJud only, for TJDFT Civil Liability from 2023 onward. Sprint 2
adds approved STJ/jurisprudence/open-doctrine sources, provenance, and NLP. Sprint 3
adds reproducible exports, grounded narrative, Consumer Law, and Contracts. Specific
NLP/generation models and export libraries require reviewed decisions; this document
does not select them implicitly. Versions, alternatives, operational limits, and
court-selection evidence remain deliverables of US-02, not proven by this summary.

Track effort in story-level `estimativa`, including migrations, source feasibility,
validation, and documentation. See the [roadmap](../product/product-roadmap.md) and
[estimation agreement](../agile/estimation-and-prioritization.md).
