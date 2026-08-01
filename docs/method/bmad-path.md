# The BMAD Path

**Product:** Freathe · **Last updated:** 1 August 2026

> **Related:** [Demand](../product/demand.md) · [Requirements](../product/requirements.md) · [Initial design](../product/initial-design.md) · [Future plans](../roadmap/future-plans.md) · [Decision log](../log/decision-log.md)

BMAD splits work at the seam where this project is stuck: a **planning phase** turning thinking into a PRD and architecture, and a **development cycle** turning those into self-contained story files. We have planning input and no mechanism for producing increments.

> Role and artifact names follow the published BMAD method but change between major versions — verify against whatever gets installed.

## 1. The two phases

**Planning** — once, in a large context window. Analyst → brief. PM → PRD with epics and stories. UX Expert → front-end spec. Architect → architecture. PO → validates, then **shards** into per-epic and per-section files. The sharding matters more than it looks: a 1,000-line PRD is unusable as development context.

**Development cycle** — per story, in the IDE. SM drafts from the sharded epic → **human approves** (the cheapest place to catch a wrong direction) → Dev implements against the story file only → QA reviews and gates.

Install with `npx bmad-method install`, greenfield full-stack workflow. Not installed yet — see §3.

## 2. Where artifacts land

Our documents are **inputs**, not outputs:

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

Delivery phases in [initial design](../product/initial-design.md) §7 remain the product plan; BMAD is how Phase 1 onward gets built.

**Step 0 — Evidence. No BMAD, no code.**

1. **Find a channel, or none of the rest happens** ([D-044](../log/decision-log.md)). Two weeks, no product: reply to real posts where people describe the loop, with the real offer. Count qualified replies and people who then do a first mission by hand — not impressions. This also recruits the cohort in step 4, so it costs nothing extra and produces the plan's most missing number.
2. **Pre-register the predictions.** Write down the expected value for every threshold in demand §8, plus what result would change your mind. Commit it — the git timestamp is the proof it was decided in advance. Reuse the analysis rubric in the sibling `manipulation recognition` repo (`docs/research/05-analysis-rubric.md`).
3. **Five conversations with people who read applications** — hiring managers, admissions or sixth-form staff. Show them a real record as the product would state it (`FR-064`) and ask whether it changes how they read the candidate. Everything downstream terminates in the artifact being worth something to someone who decides; it's asserted everywhere and tested nowhere.
4. **An unpaid concierge cohort of 20–30, adults only** ([D-018](../log/decision-log.md), [D-046](../log/decision-log.md)). Forms, a spreadsheet, hand-written missions, a guaranteed responder — **no crews** ([D-033](../log/decision-log.md)). **Split the roles** ([D-047](../log/decision-log.md)): whoever writes the missions is not whoever runs the exit interviews.
5. **Interview everyone who didn't finish, and not by the operator.** They're the real product risk, the easiest group to skip, and the most likely to be polite to the person who wrote their missions.
6. **Test the name cold** ([D-015](../log/decision-log.md)). Ten strangers, five each way, before anything is bought or printed. Under 7/10, rename.
7. **Red-team the artifacts.** Run every mission, notification, and screen string past the manipulation taxonomy in the other repo. Anything that codes as a manipulation technique gets cut. A product built by someone researching manipulation should be the cleanest on the market.

Do this before installing BMAD: the planning phase converts assumptions into a structured PRD very efficiently, and on unvalidated assumptions that efficiency works against us.

*Exit: demand §8 Phase 2 thresholds met and compared against the pre-registered predictions, or the offer revised and retested.*

**Step 1 — Planning phase.** Analyst → PM → UX Expert → Architect → PO, on concierge data. Scope the PRD to the **solo MVP only** ([requirements](../product/requirements.md) §13); crews are a later increment. The Architect challenges the initial design rather than ratifying it.

*Exit: sharded PRD and architecture, plus a decision-log entry for every departure.*

**Step 2 — Development cycle.** SM → Dev → QA until the build order in [initial design](../product/initial-design.md) §7 ships: templates and mission library, data model, onboarding through first mission, completion loop, proof-of-work output, analytics.

*Exit: requirements §9 thresholds measurable against real users.*

**Step 3 — Re-plan before crews.** A second planning cycle, not a continuation. Matching, moderation and reporting change the risk profile enough to deserve their own architecture review.

## 4. Guardrails for every agent

- **Present tense.** Reject any story adding a *will* mechanic (countdown, deadline projection, goal ceremony) or a *have* mechanic (badge, streak, trophy, portfolio-as-achievement). A hard filter, not a preference ([D-024](../log/decision-log.md)).
- **Nothing is owed.** Reject any story that schedules, requires, or bills the user for something — including *are you sure* on leaving, re-entry prompts, and anything making stopping cost more than not starting ([D-042](../log/decision-log.md), `NFR-012`).
- **Show only the consequence they can't already see.** A story surfacing time lost, days missed, or a gap in activity is rejected, and not for tone: they already have that information, and repeating it is scolding ([D-042](../log/decision-log.md)).
- **No first ship into a void.** Any story routing work to an audience must name the guaranteed responder, and must not assume rung one is someone the user knows ([D-025](../log/decision-log.md), [D-043](../log/decision-log.md)).
- **Cheap in time** — `NFR-011`. A story whose flow can't complete in five minutes needs justifying.
- **AI is scaffolding, never the creator of record** ([D-005](../log/decision-log.md)), and **no AI path without its non-AI fallback** — `FR-024`, `NFR-009`.
- **No clinical framing, no shame** — binds generated copy, mission text, and notifications ([requirements](../product/requirements.md) §11).
- **Never describe the user, only what they did.** Reject any string implying they are lazy, behind, or failing — including empty states and low-activity weeks, where it's easiest to slip in ([D-027](../log/decision-log.md)).
- **Private data stays private** — discomfort ratings and reflections never reach a crew view, admin view, public page, or analytics event.
- **Prefer the smaller story.** Hold stories to the standard the product holds its missions to.
