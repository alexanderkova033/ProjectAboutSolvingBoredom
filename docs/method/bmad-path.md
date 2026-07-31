# The BMAD Path

**Product:** ForgePath *(placeholder name — to be replaced)* · **Last updated:** 31 July 2026

> **Related:** [Demand](../product/demand.md) · [Requirements](../product/requirements.md) · [Initial design](../product/initial-design.md) · [Future plans](../roadmap/future-plans.md) · [Decision log](../log/decision-log.md)

BMAD splits work at the seam where this project is stuck: a **planning phase** turning thinking into a PRD and architecture, and a **development cycle** turning those into self-contained story files. We have 1,900 lines of planning input and no mechanism for producing increments.

> Role and artifact names follow the published BMAD method but change between major versions — verify against whatever gets installed.

## 1. The two phases

**Planning** — once, in a large context window. Analyst → brief. PM → PRD with epics and stories. UX Expert → front-end spec. Architect → architecture. PO → validates, then **shards** into per-epic and per-section files. The sharding matters more than it looks: a 1,000-line PRD is unusable as development context, and the shards are what the next phase consumes.

**Development cycle** — per story, in the IDE. SM drafts from the sharded epic → **human approves** (cheapest place to catch a wrong direction) → Dev implements against the story file only → QA reviews and gates.

Install with `npx bmad-method install`, greenfield full-stack workflow. Not installed yet — see §3.

## 2. Where artifacts land

Our documents are **inputs**, not outputs. BMAD's outputs land alongside them:

```text
docs/product/
├── demand.md · requirements.md · initial-design.md   exists — inputs
├── brief.md · prd.md · front-end-spec.md · architecture.md   ← generated
└── prd/ · architecture/                              ← PO shards
docs/stories/                                         ← SM output
docs/qa/                                              ← assessments and gates
```

1. **Inputs are never silently replaced.** `requirements.md` stays as the record of what we believed before the PRD. Contradictions resolve for the PRD and get a [decision-log](../log/decision-log.md) entry.
2. **`FR-`/`NFR-` identifiers survive.** Stories cite them rather than renumbering, so a story traces to a requirement and a requirement to a market claim.

## 3. Sequence

Delivery phases in [initial design](../product/initial-design.md) §17 remain the product plan; BMAD is how Phase 1 onward gets built.

**Step 0 — Evidence. No BMAD, no code.**

- **Five hiring-manager conversations first.** Does a self-directed project of this kind change how they read a candidate? This is the cheapest de-risking available, because everything downstream terminates in the artifact being worth something to someone who hires. Currently asserted, never tested.
- **Then a paid concierge cohort of 20–30.** Forms, a spreadsheet, hand-written missions. **Hand-pick the crews** — matching is an algorithm for a liquidity problem we don't have yet, and manual assembly must become the obvious bottleneck before it's worth building.
- **Interview the people who didn't finish.** They are the real product risk and the group it will be tempting to skip. Someone who doesn't finish has paid to be reminded they don't finish; whether that lands as a bad week or a betrayal decides whether this is a business.

Do this before installing BMAD: the planning phase converts assumptions into a structured PRD very efficiently, and on unvalidated assumptions that efficiency works against us.

*Exit: demand §9 Phase 2 thresholds met, or the offer revised and retested.*

**Step 1 — Planning phase.** Analyst → PM → UX Expert → Architect → PO, on concierge data. Scope the PRD to the **solo MVP only** ([requirements](../product/requirements.md) §14 first release); crews are a later increment. The Architect challenges initial-design §5–15 rather than ratifying it.

*Exit: sharded PRD and architecture, plus a decision-log entry for every departure from the initial design.*

**Step 2 — Development cycle.** SM → Dev → QA until design §18 priorities 1–6 ship: templates and mission library, data model, onboarding through first mission, completion loop, proof-of-work output, analytics.

*Exit: requirements §10 thresholds measurable against real users.*

**Step 3 — Re-plan before crews.** A second planning cycle, not a continuation. Matching, moderation and reporting change the risk profile enough to deserve their own architecture review.

## 4. Guardrails for every agent

- **No clinical framing** — binds generated copy, mission text, notifications (requirements §12).
- **AI is scaffolding, never the creator of record.** A story letting AI produce the user's artifact is wrong however well it tests. This costs conversion; it is the accepted price of the artifact meaning anything ([D-005](../log/decision-log.md)).
- **No AI path without its non-AI fallback** — `FR-024`, `NFR-009`. Missing fallback means not done.
- **Private data stays private** — discomfort ratings and reflections never reach a crew view, admin view, portfolio page, or analytics event.
- **Prefer the smaller story.** Hold stories to the same bounded-and-completable standard the product holds its missions to.
