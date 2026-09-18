# MoSCoW and Planning Poker — DatumLex

## Purpose

Use this guide with the [README product backlog](../README.md#product-backlog).
The README keeps the client-facing stories, priorities, estimates, and planned
sprints together. This guide explains how to make and maintain those decisions.
The [estimation agreement](estimation-and-prioritization.md) defines the operational
rules for the GitHub Project's `estimativa` field and sprint reporting.

| Backlog column | Question it answers | Owner |
|---|---|---|
| MoSCoW priority | How necessary is this capability for the agreed delivery? | PO, informed by client goals and team dependencies |
| Estimate (SP) | How much relative effort does the agreed story scope require? | Delivery contributors together |
| Planned sprint | In which increment do we intend to deliver it? | PO and team, considering capacity and dependencies |

A Must Have can be small and a Could Have can be large. A priority is not a point
value, and an estimate is not a delivery date or proof that work is complete.

## MoSCoW: decide what the delivery needs

The README applies MoSCoW to the product delivered across **Sprints 1–3**.

| Category | Decision test | DatumLex application |
|---|---|---|
| Must Have | Would omission make the agreed minimum product unviable or untrustworthy? | Evidenced merit analytics, source transparency, cross-source thesis evidence, and reproducible PDF reporting. |
| Should Have | Is it important, with a workable temporary alternative? | XLSX and reviewed AI narratives remain planned; professionals can inspect evidence and prepare a narrative manually. |
| Could Have | Can it be deferred with a smaller impact on the delivery goal? | Additional convenience in an already usable professional workflow. |
| Won't Have this time | Has it been explicitly excluded from this delivery window? | Student/exam features and case/deadline management have no planned sprint. |

For each story, record the value lost if it is deferred and any alternative.
Protect dependencies necessary for Must Have outcomes. Keep quality, provenance,
privacy, and review requirements for every delivered feature; reduce scope when
needed. Review the balance by estimated effort, not by counting story rows.

These categories follow the [Agile Business Consortium's MoSCoW model](https://www.agilebusiness.org/resource/what-is-moscow-prioritization/).
DatumLex's current classifications are explained in the
[README criteria](../README.md#moscow-criteria). The Project's **Priority** field
uses these same four options under the [prioritization policy](estimation-and-prioritization.md#priority-moscow).
Map product capabilities to implementation scope and dependencies; independent US
numbers are not a mapping. Reprioritization does not establish new client approval.

## Planning Poker: discuss effort together

Planning Poker combines private estimates, simultaneous reveal, discussion of
differences, and another vote when needed. The people doing the work estimate;
the PO clarifies the outcome and the Scrum Master facilitates. See
[Mountain Goat Software's explanation](https://www.mountaingoatsoftware.com/agile/story-points/planning-poker).

DatumLex uses **1, 2, 3, 5, 8, 13, 21 story points (SP)**. This Fibonacci scale and
the thresholds below are local planning agreements. Compare with reference stories
agreed by this team; do not convert points into hours or infer them from priority.

| Card or state | DatumLex rule |
|---|---|
| 1, 2, 3, 5, 8 | Increasing relative effort, complexity, and uncertainty against the team's reference stories. |
| 13 | Discuss whether smaller, independently useful stories would make delivery clearer. |
| 21 | Coarse refinement estimate; split before sprint selection. |
| ? | Clarify missing scope or evidence before agreeing a number. |
| Pending | No agreed estimate is recorded; it is neither zero nor a numerical card. |

Follow the [Planning Poker procedure](estimation-and-prioritization.md#planning-poker):
clarify acceptance criteria and dependencies, include all work needed for DoD,
choose cards privately, reveal together, discuss different assumptions, and
agree a value. Include data preparation, validation, testing, review, documentation,
and integration where applicable. Do not average away disagreement or present a
single person's proposed number as a team vote.

## Apply the model to the product stories

1. Read the story, its MoSCoW category, and its planned sprint in the README.
2. Agree the scope and acceptance evidence before sizing it. For example,
   **README US-05** still needs G1/G2 reconciliation; a number cannot resolve that
   scope question. For **README US-15**, discuss reproducibility, sources, charts,
   and validation together with the PDF layout.
3. Identify the implementation issues that deliver that outcome and clarify shared
   work. Broad or overlapping product stories may need refinement before estimation.
4. Run Planning Poker using the agreed scope and reference stories.
5. Replace `Pending` in **Estimate (SP)** only after agreement, and retain a linked
   session record with date, participants, scope, assumptions, and agreed points.
6. Review capacity and dependencies separately. Revise planned delivery only through
   an explicit planning decision; estimates do not move board status or dates.

All 20 README estimates initially remain **Pending** because no team voting record
has been supplied. This introduces the model without inventing historical estimates.
For work already started, label later sizing as remaining-work or retrospective
analysis, following the estimation agreement.

## Keep the README and Project consistent

README product US IDs and [implementation story IDs](user-stories.md) are independent.
Always identify the document or issue URL when recording a vote; matching numbers
do not establish a relationship.

- **README Estimate (SP):** a product planning view, with scope and session evidence.
  It is not an additional sprint velocity total.
- **Project `estimativa`:** the numeric estimate for each implementation user story,
  including enabler stories. Tasks and epics remain unscored; unresolved values stay
  blank, because the field cannot contain `Pending` or `?`.
- Copy a value between views only when the team explicitly confirms that both
  represent exactly the same scope and estimate. Record that mapping. Do not copy
  by US number or mechanically sum child tasks to size a product story.
- For a sprint forecast, count unique selected Project stories once. Never add
  README estimates, Project story estimates, and task estimates together. If a
  product-level forecast is needed, first resolve overlap and use that view alone.

Use the [session record template](estimation-and-prioritization.md#planning-poker),
specifying either `README US-xx` or the implementation issue URL and linking any
confirmed mapping. Revisit estimates when scope changes, preserving the previous
planning record. Review missing estimates before presenting a capacity forecast.

## Related agreements

- [Definition of Ready](definition-of-ready.md)
- [Definition of Done](definition-of-done.md)
- [Client alignment and open decisions](../product/client-alignment.md)
- [Product roadmap](../product/product-roadmap.md)
