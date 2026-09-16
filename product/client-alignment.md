# Client Alignment and Scope Decisions

## Source and interpretation

English summary of client conversations dated **2026-08-31, 2026-09-03,
2026-09-08, and 2026-09-15**, supplied by the team for this review. This is not a
verbatim transcript or new client approval. Later explicit direction supersedes
earlier proposals. Team statements about progress are not independent proof of
source coverage or completed releases.

## Decision history

| Date | Client direction | Product consequence |
|---|---|---|
| August 31 | One dashboard and interactive filters; no differentiated professional screens or complex permissions. Analytics comes before individual case search. | Address fragmented portals and missing quantitative indicators through a shared experience, with privacy-aware data handling. |
| September 3 | The team chooses the subject. BDJur, BDTD, and SciELO are suggested open-doctrine research candidates. | Validate access, rights, coverage, and collection method individually; suggestions do not authorize unrestricted reuse. |
| September 8 | TJDFT, Civil Liability, 2023 onward and DataJud alone are accepted for Sprint 1; this is a valid first increment, not the full MVP. | Prove the pipeline with an initial merit indicator. Appeal volume alone is insufficient. Use evidenced simple rules; refined NLP follows later. |
| September 8 | Deployed application with real data expected; mockup, name, and identity approved. | Demonstrate by link with methodology, tests, and release evidence. |
| September 15 | Depth and cross-source analysis precede expansion; integrate STJ, precedents, and open doctrine. | Sprint 2 prioritizes provenance, source integration, NLP, human validation, adherence, divergence, and trends. |
| September 15 | PDF/XLSX and cited, grounded narratives support strategy and client presentations. | Sprint 3 preserves analytical context and requires user review; historical evidence is not a guaranteed chance of winning. |
| September 15 | Lawyers, magistrates, and advisors are primary; students/examination candidates are outside focus. Consumer Law and Contracts follow. | Validate professional journeys and subject expansion without educational or examination features. |
| September 15 | Final product must connect courts, jurisprudence/doctrine, and precedents with NLP-identified theses. | Explain the evidenced theses behind outcomes, not only win/loss counts, by the end of Sprint 3. |

## Shared safeguards

- Missing evidence remains `unknown` / `unavailable`, never automatically denied.
- Separate first-instance merits, appeal outcomes, procedural events, and instance
  volume. A G2 record alone proves neither a linked appeal nor reversal or success.
- Show population, denominator, exclusions, coverage, methodology, and refresh.
  Zero denominator is unavailable, not zero success.
- Distinguish exact links from uncertain matches; version thesis/narrative evidence
  and preserve supporting passages.
- Validate rights and minimize personal data; public access is not blanket
  permission to reproduce every document.

## Backlog traceability

| Client outcome | Stories | Planned delivery |
|---|---|---|
| Real-data merit analytics in one deployed dashboard | US-01–US-19, US-23–US-27; visual baseline US-20–US-22 | Sprint 1 |
| STJ, doctrine, precedents, and traceable links | US-28–US-30 | Sprint 2 |
| Explainable extraction and human evaluation | US-31–US-33 | Sprint 2 |
| Adherence, divergence, and temporal analysis | US-34–US-36 | Sprint 2 |
| Reproducible exports and grounded narratives | US-37–US-39 | Sprint 3 |
| Consumer Law, Contracts, and professional journeys | US-40–US-42 | Sprint 3 |

The [complete catalog](../agile/user-stories.md) links individual issues and current
priorities. Technical/enabler stories implement client outcomes; they are not
presented as verbatim client requests.

## Reconciliation items identified on September 15

1. **G1/G2:** the latest client exchange welcomes results for both instances, but
   [US-14 / #19](https://github.com/DatumLex/datumlex-core/issues/19) explicitly replaces
   the earlier G1/G2-by-quarter chart with the granted-versus-denied chart. The PO
   and data team must reconcile US-03, API/UI contracts, mockup, and source feasibility.
   The roadmap records the latest expectation; this review does not rewrite issue
   acceptance criteria or claim a G1/G2 merit comparison is implemented.
2. **US-23 metadata:** [#74](https://github.com/DatumLex/datumlex-core/issues/74) describes
   Sprint 1 API documentation but has blank Priority and Sprint fields. High /
   Sprint 1 is recommended alignment, not an applied Project mutation in this review.
3. **TJDFT text for NLP:** DataJud-only Sprint 1 evidence does not prove full-text
   availability for Sprint 2. US-28–US-33 need explicit TJDFT/STJ text-access and
   coverage evidence. Existing research is an input, not a validated connector;
   link missing retrieval work during refinement.
4. **Other sources:** BDTD, SciELO, and Pangea are candidates mentioned in the
   conversations. BDJur is the current named doctrine priority. Do not promise all
   candidates in Sprint 2 or classify each as doctrine without source-specific review.

## Change control

The PO records subsequent decisions on affected stories. Update roadmap, catalog,
contracts, and [estimates](../agile/estimation-and-prioritization.md) when effort or
scope changes. Priority, points, dates, and actual progress remain distinct.
