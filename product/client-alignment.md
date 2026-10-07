# Client Alignment and Scope Decisions

## Source and interpretation

Updated on **2026-10-02** from the complete visible WhatsApp conversation in
`WhatsApp Video 2026-10-02 at 19.58.42.mp4`, supplied by the team. The substantive
exchanges run from **August 31 through September 25, 2026**. October 2 is the
recording filename date, not the date of a new client decision. The recording
scrolls backward and then forward; repeated messages count as one exchange.

This English summary distinguishes **team proposals**, **client responses**, and
**implementation/planning observations**. It is not a verbatim transcript or a
new approval. Later explicit direction supersedes earlier proposals. Positive
feedback on a mockup or sample report does not prove a deployed feature, source
coverage, or acceptance of a completed sprint. Phone numbers and unrelated
personal conversation are omitted; the private recording is not published here.

Dates below follow the message date separators: the questions sent on August 31
were answered on **September 1**, and those sent on September 3 were answered on
**September 5**. This corrects the earlier summary's attribution of the replies
to the question dates.

## Latest alignment at a glance

- Keep one shared analytical experience for lawyers, magistrates, and judicial
  advisors. Individual case search is secondary; student/exam features are outside
  the current focus.
- Sprint 1 is the TJDFT / Civil Liability / 2023 onward / DataJud-only foundation,
  with an initial evidenced merit indicator and a real-data deployed demo. It is
  a first increment, not the full product MVP.
- Deepen Civil Liability in Sprint 2 through TJDFT–STJ comparison, precedents,
  initial BDJur/open-doctrine integration, and explainable NLP. Preserve sources
  and supporting passages.
- The team's September 22 plan brings **PDF export into Sprint 2** and retains
  spreadsheets and grounded generative narratives in Sprint 3. On September 25,
  the client endorsed the Sprint 2 technical/visual direction and the PDF sample,
  specifically its traceability and limitations sections. The backlog still needs
  reconciliation with this sequence.
- The September 25 adjustment is **dynamic multiple selection** for courts,
  outcomes, and legal sources, with subjects following as coverage expands. The
  client explicitly wants to choose **TJDFT alone or TJDFT and STJ together**.
- The final product must explain the legal theses behind outcomes, with evidence
  users can inspect. Counts and favorable/unfavorable percentages alone are
  insufficient.

## Decision history

The approximate video positions refer to the forward-scrolling portion of the
53-second recording and help locate evidence; message dates govern chronology.

| Exchange dates | Evidence in the conversation | Product consequence | Video position |
|---|---|---|---|
| August 31 / September 1 | The PO asks about audiences, access, research pain, and the name. The client requests one dashboard with interactive filters, without different professional screens or complex permission levels; macro analytics takes priority over individual text search. Fragmented court portals, incompatible formats, and long PDF/result lists make research difficult. The client accepts DatumLex as the team's name choice. | Provide a shared analytical experience and quantitative context, with privacy-aware handling of public, personal, and sensitive data. | ~00:18–00:22 |
| September 3 / September 5 | The PO asks about doctrine and thematic scope. The client recommends public/open articles and theses, naming BDJur, BDTD with OAI-PMH, and SciELO's legal content, while flagging copyright constraints on books/manuals. The team may choose the initial subject. | Investigate each source's access, coverage, rights, and collection method. These suggestions are candidates, not proof of an integration or unrestricted reuse. | ~00:22–00:26 |
| September 8 | The PO proposes TJDFT, Civil Liability, records from 2023 onward, a DataJud-only pipeline, volume/instance indicators, and later merit analysis. The client accepts the narrow first increment and DataJud-only engineering focus, but requires an initial merit indicator already in Sprint 1; counting appeals alone is insufficient. Simple movement-based rules/keywords may precede refined NLP. | Deliver an evidenced ETL → warehouse → API → dashboard foundation with initial merit analysis; keep unavailable evidence explicit. Cross-source intelligence remains necessary for the complete product. | ~00:26–00:33 |
| September 8 | The client expects a deployed application accessible by link with real data and approves the shared-dashboard mockup, name, and visual identity. | Retain one professional analytical interface and demonstrate actual data and behavior. Mockup approval is design alignment, not release acceptance. | ~00:26–00:33 |
| September 15 | In response to the PO's nine questions, the client prioritizes depth and cross-source analysis before broader court/subject coverage. STJ is the natural next integration; BDJur/open doctrine and precedents complement judicial data. Consumer Law and Contracts are useful later subjects. | Prioritize source integration and provenance before expansion. | ~00:33–00:44 |
| September 15 | The client values adherence to precedents, divergence between chambers/panels on the same thesis, main legal grounds/theses, and temporal trends. NLP extraction and generative narratives are useful when grounded in actual sources. | Explain how conclusions relate to inspectable evidence; retain human validation and uncertainty. | ~00:33–00:44 |
| September 15 | PDF and spreadsheet export are important for professional use: formatted charts/sources support opinions and client presentations, while spreadsheets support research and legal operations. The main journeys include appeal-versus-settlement analysis and explaining the legal position to a client. | Preserve analytical context in reusable outputs. Historical analysis supports professional judgment; it is not a guaranteed probability of winning. The later September 22 proposal specifies the revised PDF timing. | ~00:33–00:44 |
| September 15 | Primary users are litigation lawyers/law firms, magistrates, and judicial advisors. Students and examination candidates are outside the focus. By the end of Sprint 3, cross-source analysis and NLP-identified theses must explain why outcomes occur. The client welcomes the proposed G1/G2 and merit direction for Sprint 1. | Validate professional journeys and retain the final thesis/evidence objective. Welcoming the proposal does not establish implemented G1/G2 merit comparison or completed delivery. | ~00:33–00:44 |
| September 22 | The PO sends a detailed Sprint 2 proposal, a five-page sample PDF, and a mockup introducing NLP. The proposal retains Civil Liability, deepens TJDFT–STJ analysis, adds initial doctrine integration, and moves PDF export into Sprint 2; spreadsheet export and grounded generative reports remain in Sprint 3. The PO also reports that previously considered hosting tools were ruled out by the professor and alternatives were being evaluated. | Record the proposed sequence and hosting constraint separately from the client's response and from implementation evidence. | ~00:44–00:48 |
| September 24 | The client acknowledges receipt and says the material will be reviewed. | This is a review acknowledgment, not approval of the scope or delivery. | ~00:48–00:49 |
| September 25 | The client says the Sprint 2 technical and visual direction is aligned, praises the PDF's evidence and limitations, and approves the explainable NLP approach. The requested adjustment is dynamic multiselect filters, especially allowing TJDFT alone or TJDFT + STJ. | Incorporate the specific review findings below. The reference to an upcoming Sprint 1 presentation does not establish release acceptance. | ~00:49–00:53 |

## September 22 proposal and September 25 review

### Team proposal for Sprint 2

The PO proposed keeping **Civil Liability** and adding depth through:

1. NLP that identifies and organizes legal theses, grounds, and precedent
   references, with a source and supporting passage for each result.
2. TJDFT–STJ integration to compare local reasoning with superior-court
   jurisprudence and precedents.
3. Indicators of precedent adherence, possible divergence, and temporal trends,
   accompanied by a sources, coverage, and limitations area.
4. Initial BDJur/open-doctrine integration relating doctrine to identified theses.
5. PDF export containing the selected filters, indicators, charts, sources,
   coverage, and limitations.

Spreadsheet export and generative reports grounded in consolidated sources and
classifications were explicitly left for **Sprint 3**. The additional NLP screen
is part of the shared product; it is not a request for separate portals by
professional role.

### Client feedback to preserve in acceptance criteria

| Area | September 25 client feedback | Implication for refinement |
|---|---|---|
| PDF evidence | The sample's page 4 is valuable because it includes supporting excerpts and direct links to sources. | Readers must be able to trace a reported thesis or finding to the supporting material. |
| PDF transparency | The sample's page 5, Sources and Limitations, is fundamental: coverage, counting unit, and NLP criteria must be clear. | Carry the analytical scope and interpretation limits into the exported report. |
| Explainable NLP | The thesis ranking and evidence cards with **“Ver fontes”** let lawyers and magistrates audit the result and avoid a black box. | Preserve the path from an NLP result to its evidence in the interface. |
| Dynamic filters | The court dropdown appeared fixed/single-selection. The client requests multiselect controls or checkboxes for courts, outcomes, and legal sources, and subjects as the product expands. | Support one or several available values. The explicit court example is **TJDFT only** versus **TJDFT + STJ together**; a permanently fixed court does not satisfy this request. |

The five-page **Sprint 2 report sample** appears as an attachment in the video;
the findings above summarize the client's comments on it. It is a different
artifact from the separately supplied eight-page **`DatumLex-Sprint1.pptx.pdf`**,
which was reviewed as presentation context. The latter still places PDF/Excel in
Sprint 3 on page 8 and lists Render on page 5. Neither the presentation nor the
client's comments prove completed export or deployment functionality.

## Shared safeguards

These are product/engineering interpretation rules retained alongside the client
record; they are not presented as verbatim client statements.

- Missing evidence remains `unknown` / `unavailable`, never automatically denied.
- Separate first-instance merits, appeal outcomes, procedural events, and instance
  volume. A G2 record alone proves neither a linked appeal nor reversal or success.
- Show population, denominator, exclusions, coverage, methodology, and refresh.
  Zero denominator is unavailable, not zero success.
- Distinguish exact links from uncertain matches; version thesis/narrative evidence
  and preserve supporting passages.
- Validate rights and minimize personal data; public access is not blanket
  permission to reproduce every document.
- Define multiselect behavior consistently across API, dashboard, evidence views,
  and exports. The client did not specify query syntax, combination rules, or
  empty-selection behavior; those need explicit contracts and validation.

## Backlog traceability

The IDs below refer to the **42 implementation stories** in the
[story catalog](../agile/user-stories.md), not the independently numbered product
stories in the repository README. This maps outcomes to refinement targets; it
does not change issue criteria, Project fields, estimates, or completion status.

| Client outcome | Implementation stories | Latest direction / planning boundary |
|---|---|---|
| Real-data merit analytics in one deployed dashboard | US-01–US-19, US-23–US-27; visual baseline US-20–US-22 | Sprint 1 foundation; acceptance requires integrated evidence. |
| STJ, doctrine, precedents, and traceable links | US-28–US-30 | Sprint 2; retain Civil Liability and verify each source. |
| Explainable extraction, thesis ranking, evidence cards, and evaluation | US-31–US-33, with US-36 for thesis/trend presentation | Sprint 2; preserve excerpts and direct source access. |
| Adherence, divergence, and temporal analysis | US-34–US-36 | Sprint 2 direction; depth precedes expanded subjects. |
| Dynamic multiple selection | Existing filter baseline US-15 / [#20](https://github.com/DatumLex/datumlex-core/issues/20), plus cross-source API/UI and export work | September 25 follow-up for Sprint 2; refine or split work rather than treating the single-court Sprint 1 control as sufficient. |
| Reproducible PDF report | US-37 / [#127](https://github.com/DatumLex/datumlex-core/issues/127) | September 22 proposal places PDF in Sprint 2; September 25 endorses the direction and sample. Project still shows Sprint 3 as of October 2. |
| Spreadsheet export and grounded generative narratives | US-38 / [#130](https://github.com/DatumLex/datumlex-core/issues/130), US-39 / [#133](https://github.com/DatumLex/datumlex-core/issues/133) | Remain in Sprint 3 in the September 22 proposal. |
| Consumer Law, Contracts, and professional journeys | US-40–US-42 | Later expansion; existing Sprint 3 plan. The September 22 proposal retains Civil Liability for Sprint 2. |

## Reconciliation items identified on September 15

The original section anchor is retained for links from other documents. These
items remain distinct from the new September 25 filter feedback.

1. **G1/G2:** the September 15 exchange welcomes results for both instances, but
   [US-14 / #19](https://github.com/DatumLex/datumlex-core/issues/19) was defined around
   replacing the earlier G1/G2-by-quarter chart with the granted-versus-denied
   chart. Reconcile US-03, API/UI contracts, mockup, and source feasibility. In the
   reviewed code, the instance chart counts DataJud documents by filing period;
   it does not establish a G1/G2 merit comparison or linked-appeal reversal rate.
2. **US-23 metadata:** [#74](https://github.com/DatumLex/datumlex-core/issues/74) describes
   Sprint 1 API documentation. Priority and Sprint were blank on September 15.
   The October 2 Project inspection shows **Should Have**, with Sprint still blank.
   Required endpoint contracts and API documentation remain part of delivery under
   the [prioritization policy](../agile/estimation-and-prioritization.md#priority-moscow).
3. **TJDFT text for NLP:** DataJud-only Sprint 1 metadata does not prove full-text
   availability for Sprint 2. US-28–US-33 need explicit TJDFT/STJ text-access and
   coverage evidence. Existing research is an input, not a validated connector.
4. **Other sources:** BDTD, SciELO, and Pangea are candidates mentioned in the
   conversations. BDJur is the named initial doctrine priority in the September 22
   proposal. Do not promise every candidate in Sprint 2 or classify each as doctrine
   without source-specific review.

## Reconciliation after the September 25 feedback

1. **PDF scheduling:** the [roadmap](product-roadmap.md), [catalog](../agile/user-stories.md),
   README product backlog, and live Project still place PDF in Sprint 3. The supplied
   Sprint 1 presentation does too. Reconcile US-37, its dependencies, sprint capacity,
   and release evidence with the September 22/25 exchange. PDF moving earlier does
   not also move spreadsheet export or generative narratives into Sprint 2.
2. **Filters:** the reviewed core has a single-court analytical filter, with TJDFT
   as the implemented integration, and single-value API filter contracts. It does
   not implement the requested combined TJDFT + STJ analysis. Refine court, outcome,
   and legal-source multiselect behavior and future subject selection, including
   available coverage and consistent analytical/export context.
3. **Evidence experience:** carry excerpts, direct source links, counting unit,
   coverage, and NLP criteria into US-31–US-33 and US-37. The client praised sample
   materials; actual source retrieval, classifications, links, and export values
   still require validation.
4. **Access design:** the reviewed core includes authentication, administrative
   roles, approval, and court permissions. Those implementation decisions are not
   requested by the conversation's shared-dashboard direction. Record their
   separate rationale and validate the resulting access experience. Administrative
   court-permission checkboxes do not satisfy analytical multiselect filters.
5. **Hosting:** the September 22 message reports an academic constraint and a
   search for alternatives, without a client-selected replacement provider. The
   reviewed core contains Render deployment configuration, and the supplied
   presentation names Render; documentation and deployment issues still refer to
   Vercel/Railway. Reconcile the technical delivery records using deployment evidence,
   without attributing the Render choice to client approval in this video.

These observations compare the conversation with documentation at
[`74c2cc2`](https://github.com/DatumLex/documentation/tree/74c2cc20a35426d8ec5647d833ecb898704edaae),
core at
[`c7e45c2`](https://github.com/DatumLex/datumlex-core/tree/c7e45c21c0bac6ad0fd1cb68fccb5e569d463d04),
and the [GitHub Project](https://github.com/orgs/DatumLex/projects/1) inspected on
**October 2, 2026**. They describe the reviewed source and planning state, not a
fresh runtime test or a claim that a release was accepted.

## Change control

The PO records subsequent decisions on affected stories. Update roadmap, catalog,
contracts, presentation, release criteria, and
[estimates](../agile/estimation-and-prioritization.md) when scope or effort changes.
Keep the dated proposal, client response, planning decision, and delivery evidence
traceable. Priority, points, dates, and actual progress remain distinct.
