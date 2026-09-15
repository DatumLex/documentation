# Personas and Primary Audiences — DatumLex

## Purpose

This document describes the principal audiences DatumLex intends to serve. The
personas are product hypotheses based on the current project direction, not a
substitute for interviews, observation, usability testing, or legal research.

Names and demographic details are intentionally omitted. The product focuses on
roles, decisions, needs, and risks rather than fictional personal biographies.

## Audience priority

The client alignment of September 15 prioritizes **lawyers, magistrates, and
judicial advisors**. Researchers and legal operations are secondary beneficiaries
of traceable analytics and exports. Students, educators, and examination candidates
do not drive features in these sprints. All priority audiences share one dashboard
with interactive filters; specialized permissions or screens are not required.
These are client-validated audience priorities, while detailed persona behavior
remains a hypothesis to validate with representative users.

## Persona 1 — Lawyer or legal team

### Context

Works on litigation, advisory matters, or legal strategy and needs to understand
how comparable appeals have been decided within a defined court, subject, and
period.

### Needs and questions

- How often were comparable appeals granted or denied?
- Does the observed pattern change by period, court, or subject?
- What population and classification rules produced the indicator?
- Which decisions should be read for case-specific legal analysis?
- How current and complete is the available data?

### Expected value

- Reduce repetitive collection and spreadsheet work.
- Support strategy and client communication with transparent context.
- Identify patterns that deserve deeper doctrinal and case-level research.
- Avoid treating anecdotal experience as the entire evidence base.

### Risks and safeguards

- Historical frequency does not predict a specific case result.
- Different facts, procedural posture, panels, and legal changes may limit
  comparability.
- Every analytical view must disclose source, scope, exclusions, refresh date,
  and methodology.
- The product must encourage reading relevant decisions and obtaining
  professional judgment.

## Persona 2 — Magistrate or judicial advisor

### Context

Performs judicial research, prepares technical analysis, studies institutional
patterns, or supports court administration while preserving decisional
independence and case-specific reasoning.

### Needs and questions

- What outcome patterns are visible within a defined and reproducible scope?
- Are apparent differences explained by coverage, classification, or missing
  data?
- Can the analytical result be traced to official sources and rules?
- Does the interface support institutional analysis without prescribing a
  decision?

### Expected value

- Provide statistical context for research and institutional understanding.
- Make coverage and classification limitations easier to inspect.
- Support comparison across time or approved dimensions.
- Help identify questions requiring deeper qualitative analysis.

### Risks and safeguards

- DatumLex must never recommend a verdict or replace independent legal judgment.
- Individual judges, panels, parties, or sensitive attributes must not be ranked
  or profiled without an explicitly reviewed legal, ethical, and product basis.
- Methodology and uncertainty must be prominent enough to prevent false
  precision.
- Institutional use requires direct validation with representative users.

## Persona 3 — Researcher or legal operations professional (secondary)

### Context

Conducts empirical legal studies, institutional research, policy analysis, or
data exploration and requires reproducible definitions and traceable sources.

### Needs and questions

- What is the unit of analysis and eligible population?
- Which records were excluded, unknown, duplicated, or unavailable?
- How were outcomes classified and validated?
- Can results be reproduced across refreshes and versions?

### Expected value

- Access a structured analytical model rather than rebuilding every input.
- Form hypotheses and compare clearly defined populations.
- Reuse documented methodology and data definitions.
- Identify source-quality limitations before drawing conclusions.

### Risks and safeguards

- Changes to models, classifications, or sources require versioned
  documentation.
- Exports and APIs must preserve enough metadata for interpretation.
- Negative or incomplete findings must remain visible.
- Reproducibility requires stable definitions, validation evidence, and refresh
  history.

## Shared jobs to be done

Across audiences, users need to:

1. define a valid analytical scope;
2. understand how much eligible data is available;
3. compare outcomes and changes over time;
4. identify patterns for deeper investigation;
5. verify the origin and meaning of the result; and
6. communicate findings without overstating certainty.

## Cross-persona experience requirements

- Clear language and definitions for legal and analytical terms.
- Visible filters and selected-scope context.
- Honest loading, error, empty, unavailable, and partial-data states.
- Source, methodology, denominator, exclusions, and refresh information.
- Keyboard access, readable contrast, responsive layout, and screen-reader
  semantics.
- No fabricated statistics, automated verdicts, or certainty claims.
- Links or identifiers that support deeper research into relevant source
  material when legally and technically available.

## Research plan

These personas should evolve through evidence. Product discovery should include:

- semi-structured interviews with representatives of each priority audience;
- observation of current legal research and comparison workflows;
- usability tests using the dashboard and realistic questions;
- comprehension checks for indicators, charts, filters, and limitations;
- accessibility testing with representative assistive technologies;
- review of legal, ethical, privacy, and institutional risks; and
- synthesis of findings into linked backlog decisions.

Record the participant profile without unnecessary personal data. Separate
observed evidence from assumptions and avoid claiming general validity from a
small convenience sample.

## Persona validation record

```markdown
## Persona validation
- Audience and context: <role and relevant experience>
- Research method: <interview, observation, usability test, or survey>
- Date and facilitator: <YYYY-MM-DD / name>
- Questions or tasks: <summary>
- Observed needs and difficulties: <evidence>
- Assumptions confirmed or rejected: <list>
- Product decision and backlog links: <links>
- Limitations of the research: <details>
```

## Planning professional journeys

US-42 validates the shared path from research question to evidence, comparison,
and reviewed report. Capture feedback from lawyers and judicial professionals;
do not introduce student/exam workflows or separate portals. Estimate the whole
story in `estimativa`, including usability and accessibility work, under the
[Planning Poker agreement](../agile/estimation-and-prioritization.md).

## Related documents

- [Product Vision](product-vision.md)
- [Product Roadmap](product-roadmap.md)
- [Market References](market-references.md)
- [Product Owner Guide](../agile/product-owner-guide.md)
- [Design Standards](../design/datumlex-design-guide.pdf)
- [Product Backlog](https://github.com/orgs/DatumLex/projects/1)
