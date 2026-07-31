# The BMAD Path

**Product:** ForgePath (working title) · **Last updated:** 31 July 2026

> **Related:** [Demand](../product/demand.md) · [Requirements](../product/requirements.md) · [Initial design](../product/initial-design.md) · [Future plans](../roadmap/future-plans.md) · [Decision log](../log/decision-log.md)

BMAD splits work at the seam where this project is stuck: a **planning phase** that turns thinking into a PRD and an architecture, and a **development cycle** that turns those into self-contained story files. We have 1,900 lines of planning input and no mechanism for producing increments. The second half is what we lack.

> Role and artifact names below follow the published BMAD method, but change between major versions — verify against whatever version gets installed.

## 1. The two phases

**Planning** — run once, in a large context window:

| Role | Produces |
|---|---|
| Analyst | Project brief |
| PM | PRD with epics and stories |
| UX Expert | Front-end spec |
| Architect | Architecture document |
| PO | Validated docs, then **sharded** into per-epic and per-section files |

The sharding step matters more than it looks: a 1,000-line PRD is unusable as development context, and the sharded form is what the next phase actually consumes.

**Development cycle** — repeats per story, in the IDE:

SM drafts the story from the sharded epic → **human approves** (cheapest place to catch a wrong direction) → Dev implements against the story file only → QA reviews and gates.

Install with `npx bmad-method install`. Greenfield full-stack workflow. Not installed yet — see §3.

## 2. Where artifacts land

Our existing documents are **inputs**, not outputs. They keep their homes; BMAD's outputs land alongside:

```text
docs/product/
├── demand.md · requirements.md · initial-design.md   exists — inputs
├── brief.md · prd.md · front-end-spec.md · architecture.md   ← generated
└── prd/ · architecture/                              ← PO shards
docs/stories/                                         ← SM output
docs/qa/                                              ← assessments and gates
```

Two rules:

1. **Inputs are never silently replaced.** When `prd.md` exists, `requirements.md` stays as the record of what we believed before it. Contradictions resolve in favour of the PRD and get a [decision-log](../log/decision-log.md) entry.
2. **`FR-`/`NFR-` identifiers survive.** Stories cite them rather than renumbering, so any story traces back to a requirement and any requirement back to a market claim.

## 3. Sequence

The delivery phases in [initial design](../product/initial-design.md) §19 remain the product plan; BMAD is how Phase 1 onward gets built.

**Step 0 — Concierge test. No BMAD, no code.** Forms, a spreadsheet, hand-written missions, a paid cohort of 20–30. Do this *before* installing BMAD: the planning phase converts assumptions into a structured PRD very efficiently, and run on unvalidated assumptions that efficiency works against us — a well-organised specification for a product nobody wants is harder to abandon than a messy one. *Exit: demand §9 Phase 2 thresholds met, or the offer is revised and retested.*

**Step 1 — Planning phase.** Analyst → PM → UX Expert → Architect → PO, using the concierge data. Scope the PRD to design §19 **Phase 1 only** — solo MVP, crews explicitly excluded. The Architect challenges initial-design §5–17 rather than ratifying it. *Exit: sharded PRD and architecture, plus a decision-log entry for every departure from the initial design.*

**Step 2 — Development cycle.** SM → Dev → QA until design §20 priorities 1–6 ship: templates and mission library, the data model, onboarding through first mission, the completion loop, proof-of-work output, analytics. *Exit: requirements §10 thresholds measurable against real users.*

**Step 3 — Re-plan before crews.** A second planning cycle, not a continuation. Moderation, matching and reporting change the risk profile enough to deserve their own architecture review.

## 4. Guardrails for every agent

From constraints already committed in the product documents:

- **No clinical framing** — binds generated copy, mission text, notifications (requirements §12).
- **AI is scaffolding, never the creator of record** — a story letting AI produce the user's artifact is wrong however well it tests.
- **No AI path without its non-AI fallback** — `FR-024`, `NFR-009`. Missing fallback means not done.
- **Private data stays private** — discomfort ratings and reflections never reach a crew view, admin view, portfolio page, or analytics event.
- **Prefer the smaller story** — hold stories to the same bounded-and-completable standard the product holds its missions to.
