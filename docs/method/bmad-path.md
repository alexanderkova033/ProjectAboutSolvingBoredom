# The BMAD Path

**Product:** ForgePath *(placeholder name — to be replaced)* · **Last updated:** 1 August 2026

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

Delivery phases in [initial design](../product/initial-design.md) §8 remain the product plan; BMAD is how Phase 1 onward gets built.

**Step 0 — Evidence. No BMAD, no code.**

1. **Pre-register the predictions.** Before anything runs, write down the expected value for every threshold in demand §8, plus what result would change your mind. Commit it — the git timestamp is the proof it was decided in advance. The method is already built in the analysis rubric in the sibling `manipulation recognition` repo (`docs/research/05-analysis-rubric.md`); reuse it rather than reinventing it.
2. **Five conversations with people who read applications** — hiring managers for the adult segment, admissions or sixth-form staff for persona D. Show them a real generated sentence (`FR-064`) and ask whether it changes how they read the candidate. Everything downstream terminates in the artifact being worth something to someone who decides; it is asserted everywhere and tested nowhere.
3. **An unpaid concierge cohort of 20–30** ([D-018](../log/decision-log.md)). Forms, a spreadsheet, hand-written missions, **hand-picked crews**. Unpaid weakens the evidence and that limitation travels with every result it produces — record it wherever the numbers are quoted.
4. **Interview everyone who didn't finish.** They are the real product risk and the easiest group to skip, and a free cohort makes skipping them easier still.
5. **Red-team the artifacts.** Run every mission, notification, and screen string past the manipulation taxonomy in the other repo. Anything that codes as a manipulation technique gets cut. A product built by someone researching manipulation should be the cleanest one on the market.

Do this before installing BMAD: the planning phase converts assumptions into a structured PRD very efficiently, and on unvalidated assumptions that efficiency works against us.

*Exit: demand §8 Phase 2 thresholds met and compared against the pre-registered predictions, or the offer revised and retested.*

**Step 1 — Planning phase.** Analyst → PM → UX Expert → Architect → PO, on concierge data. Scope the PRD to the **solo MVP only** ([requirements](../product/requirements.md) §13 first release); crews are a later increment. The Architect challenges initial-design §5 rather than ratifying it.

*Exit: sharded PRD and architecture, plus a decision-log entry for every departure from the initial design.*

**Step 2 — Development cycle.** SM → Dev → QA until design §8 build order steps 1–6 ship: templates and mission library, data model, onboarding through first mission, completion loop, proof-of-work output, analytics.

*Exit: requirements §9 thresholds measurable against real users.*

**Step 3 — Re-plan before crews.** A second planning cycle, not a continuation. Matching, moderation and reporting change the risk profile enough to deserve their own architecture review.

## 4. Guardrails for every agent

- **Present tense.** Reject any story that adds a *will* mechanic (countdown, deadline projection, goal ceremony) or a *have* mechanic (badge, streak, trophy, portfolio-as-achievement). This is a hard filter, not a preference ([D-024](../log/decision-log.md)).
- **No first ship into a void.** Any story routing a user's work to an audience must name the guaranteed responder ([D-025](../log/decision-log.md)).
- **Cheap in time** — `NFR-011`. A product promising reclaimed hours cannot demand large ones. A story whose flow can't complete in five minutes needs justifying.
- **AI is scaffolding, never the creator of record.** A story letting AI produce the user's work is wrong however well it tests ([D-005](../log/decision-log.md)).
- **No AI path without its non-AI fallback** — `FR-024`, `NFR-009`.
- **No clinical framing, no shame** — binds generated copy, mission text, and notifications (requirements §11).
- **Never describe the user, only what they did.** Reject any string implying they are lazy, behind, or failing — including empty states and low-activity weeks, where it is easiest to slip in ([D-027](../log/decision-log.md)).
- **Private data stays private** — discomfort ratings and reflections never reach a crew view, admin view, public page, or analytics event.
- **Prefer the smaller story.** Hold stories to the standard the product holds its missions to.
