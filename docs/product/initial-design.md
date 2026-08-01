# Initial Product and Technical Design

**Product:** Freathe · **Status:** Draft — a starting position, not a ratified architecture · **Superseded by:** `architecture.md` after the BMAD Architect run · **Revised:** 1 August 2026

> **Related:** [Demand](demand.md) · [Requirements](requirements.md) · [BMAD path](../method/bmad-path.md) · [Repo structure](../roadmap/repo-structure.md) · [Decision log](../log/decision-log.md)

> No code, schemas, or interface definitions. They go stale faster than the decisions around them. What belongs here is the shape of the thing and the trade-offs behind it.

## 1. Overview

Turn an idle moment into one small act of making, get the result in front of a real person quickly, and show the user weekly how many hours they authored. It sells reclaimed time and proves it with something that exists outside their head.

**The platform is an open decision** ([D-037](../log/decision-log.md)). Mobile-first no longer follows: the missions produce real artifacts — writing, tools, designs, recordings — and beginners make almost none of that on a phone. Recommendation is desktop web, with mobile at most a thin later surface for the moment boredom strikes. Nothing else here depends on the answer.

Goals and non-goals are [requirements](requirements.md) §4; principles are §3 there. Neither is restated — two copies drift, and these already had.

## 2. What the design depends on

- **Boredom is upstream**, so the intervention is making, not fear-management ([D-023](../log/decision-log.md)).
- **The last link is a verdict, not a cause**, so the design disputes it with a record and never names it ([D-027](../log/decision-log.md)).
- **Autonomy is load-bearing.** A prescribed programme reproduces what makes courses inert ([D-028](../log/decision-log.md)).
- **Payoff must arrive fast.** Creating can't win on ease, only on payoff size, and only if it arrives soon enough to compete.
- **The internet's default response is silence.** External validation has to be engineered, not hoped for.
- **Freedom, and consequence** ([D-042](../log/decision-log.md)). Discipline isn't available as a mechanism: nothing is scheduled or owed, and leaving is free at every point. The job is making the *invisible* consequence visible, never the one already felt.

## 3. Product design

### 3.1 Surfaces

**Now** — one mission, already on screen, with controls to start, swap, shrink, or flag a blocker. No selector. **Project** — what's being made, stages, things made. **Evidence** — what was made, what shipped, what came back. **Profile** — privacy, notifications, export, deletion. Administrators get **Cohort**. A **Crew** surface is specified but unscheduled ([D-033](../log/decision-log.md)).

### 3.2 Key flows

**Welcome.** *Your evenings are going somewhere. This is how you get them back.*

**Pick something.** No questionnaire, no account, no goal-setting — a small set of real, concrete things the user could make, each shown as the thing itself with an example of someone's finished version: a researched explainer, a simple tool, a product concept, a local problem-and-solution report, a short visual or audio story, a tiny service experiment. The choice is the signal, and what they passed over is recorded too.

**No scope screen and no date screen exist.** The 72-hour first ship keeps work small without anyone declaring a size; the absence of a deadline is the point, not an omission.

**The loop.** One mission is already on screen. The card carries a title, an instruction, and one definition of done — but **no duration**, because telling someone a task takes twenty minutes gives them a reason to postpone it. Start, swap, shrink, or say what's in the way. When it's done the next is right there. Stopping needs no action and produces no comment.

**What makes the session pleasant** ([D-045](../log/decision-log.md)) — five mechanisms, each a consequence of something already decided:

- **The mission removes the decision, not the work.** What's aversive about starting is deciding. A mission specific enough to begin with zero thinking has had that part taken out. This is what the definition of done is *for*, and why *think about your target customer* is banned.
- **The first move is mechanical.** Open the file, paste the three quotes in, draw the four boxes. A blank first minute is where sessions die; invention comes at minute five, once the thing is moving.
- **Visible change under your hands.** Something must look different by the end. This is a filter on the template library (§3.3), not a feature.
- **The interface does nothing.** No notification, badge, animation, or moving chrome while a mission is open (`NFR-012`).
- **Leaving is free.** No confirmation, no cost, no comment. This makes the others possible: starting is cheap only because you can walk at any second ([D-042](../log/decision-log.md)).

Whether it works is **observed, not asked** — does the user start another mission unprompted in the same session (`FR-068`)? A survey would get a polite yes from people who found it a chore.

**Session feeling.** One tap before, one after. No words, skippable permanently. The user sees their own history; nobody else ever does, it never becomes a score, and the product never comments. The single exception to measuring only behaviour, earned because it's the only direct measure of the promise, and safe because of the subject: the product never rates the user, the user rates a session.

**Ship.** The ladder, one rung at a time, each guaranteed to respond before the next unlocks: **one guaranteed responder → several → a small public.**

The rungs are a **scale sequence, not an intimacy one** ([D-043](../log/decision-log.md)). *Someone you already know* sat at rung one on the assumption that familiar means gentle. It runs the other way: a friend's judgment persists — they're at the table at Christmas, and a bad first thing becomes a thing about you — while a stranger's evaporates on contact. So the rung is defined by one property, that someone is guaranteed to respond, and **the user picks who**. A fitting stranger is the default offer. In hand-run cohorts the guarantee is a named person, not a pool.

**When a response arrives late.** Projects end and responses sometimes turn up afterwards. That response is shown (`FR-067`) as news, with no call to action — not *ready to start something else?*, not a suggested project, not reactivation dressed as a notification. It's the one piece of genuinely new information the product ever has, and it is also the retention hypothesis in its entirety: nothing else here has permission to pull anyone back.

**The first reckoning — at 72 hours, and the model for every mirror after.** Two screens, in order. First, one question in the user's own words:

> *What have you got done so far?*

Free text, no numbers, skippable. Fires only if there's something in the record — asking what someone achieved when they achieved nothing is the worst screen in the product. Then the record, beside their answer:

> **You said:** *not much really, messed about with the intro*
>
> **Recorded:** 3 sessions · 1 hour 40 minutes · 2 things made · 1 shipped · 1 response

**Nothing narrates the gap.** No delta, no arrow, no percentage, no *"you did more than you thought"*. Both are simply present; if the user notices, the noticing is theirs. This runs the other way sometimes — someone says they did loads and the record says forty minutes. That screen looks identical. A record that only speaks up when it's flattering isn't a record.

**What you did, roughly.** Offered after the record and again on the receipt ([D-041](../log/decision-log.md)). Plain facts, ordinary words, deliberately not a sentence:

> You came back to this on 7 different days.
> You made a thing that turns handwritten recipe cards into a searchable list.
> You put it in front of 3 people you don't know.
> One of them asked for a change and you made it that week.
> The first version didn't work and you kept going anyway.

**No polished sentence, no copy button, no application formatting.** A paste-ready line means they never articulate it themselves, and *"tell me about this"* then catches them with nothing. The gap this fills is **noticing** — people genuinely cannot see what they did. Saying it is their work and their skill. Two hard rules: never claim the work is impressive or predict how a reader will take it, and **never inflate** — one small thing is described as one small thing.

**Time mirror.** Weekly, same shape, with the self-report step becoming occasional. Backward-looking: hours authored, things made, things shipped, responses received. No target, no projection, no comparison. Its job is narrow — **make *"I'm just lazy"* untenable against a record.** Not to inform or motivate. That's why it counts what was made and stays silent about the rest, and why a low week must still read as a record rather than a shortfall.

After two stalled weeks, one question: *is this still the thing you want to be making?* Shown alongside what they picked and passed over. Dropping it is a good outcome.

**Completion.** A page recording what the thing is, what it took, and what came back — a receipt that the hours were real, generated as a by-product, never the reason for the work ([D-026](../log/decision-log.md)).

### 3.3 Templates

Authored by hand before any model involvement — the model adapts a tested path, it doesn't invent the pedagogy. Three entry criteria:

1. A first version must ship in days.
2. Someone must plausibly want the result. A template that can't answer *who would want this* doesn't go in.
3. **The first session must end with something the user can look at** ([D-045](../log/decision-log.md)). Not progress, not a plan, not notes. Projects whose opening hours are research, setup, or configuration fail this however good the eventual artifact is, because the session they produce loses to a feed.

## 4. Detailed design

### 4.1 Domain model

The important structural decision: **making, shipping, and being responded to are three separate things.** An earlier model recorded that work happened but not that it landed, which is the only thing this thesis cares about.

| Entity | Holds | Why it's separate |
|---|---|---|
| **Project** | Title, artifact type, stage, visibility | Holds **no target date and no scope estimate** ([D-028](../log/decision-log.md)) — no field to leave blank, and no field that makes a deadline easy to add back later |
| **Session mood** | An optional pair of taps | Stored against the session, readable only by its owner, kept apart so no query can join it to a profile ([D-031](../log/decision-log.md)) |
| **Mission** | Instruction, definition of done, duration, difficulty, stage, and a **kind** — *produce*, *distribute*, or *reset* | Shipping as a kind rather than a phase is what stops distribution being deferred forever. The kind field is also what makes the reset exclusion enforceable rather than a convention ([D-040](../log/decision-log.md)) |
| **Mission attempt** | Attempted, completed, blocker, optional discomfort | Preserved separately so a skip is data rather than an absence |
| **Artifact** | The thing itself, and when it shipped | Evidence proves effort; an artifact is what a stranger could actually receive |
| **Ship** | An artifact sent to one rung, and that rung's guaranteed responder | Modelling the rung is what makes "no first ship into a void" enforceable |
| **Response** | An external reaction, its kind, and **whether it came from someone who knows the user** | A friend's kindness and a stranger's use are not the same evidence |
| **Production session** | Minutes, and whether anything was produced | Time is the product, so time is a first-class record |

Projects own missions and artifacts; artifacts own ships; ships own responses; users own sessions. Reflections and mood records sit under stricter row-level policies than anything shippable.

### 4.2 Mission generation

Takes stage, definition of done, remaining milestones, observed session lengths, experience, recent blockers, and what already exists. **Never given a time budget**, because the user is never asked for one ([D-034](../log/decision-log.md)) — size is inferred from how long their sessions actually run.

A generated mission starts with one observable verb, produces or ships something real, is small enough to start immediately, carries a testable definition of done, covers one task, **opens on a mechanical first move rather than a decision** ([D-045](../log/decision-log.md)), and never produces the user's work. Difficulty sits mostly at 2–4.

> Bad: *Think about your target customer.*
> Better: *Write three sentences on one customer, the moment the problem hits, and what they do instead.*

Output is schema-validated; two consecutive failures fall back to a hand-written template. Every stage has template coverage, so the product is fully usable with the model off. **Distribution missions are first-class** — the generator offers one as soon as anything is shippable.

**Reset missions are the exception to *produce something real*** ([D-040](../log/decision-log.md), `FR-047`–`FR-049`). *Go outside for ten minutes. Clear the table.* Offered on a reported blocker, after a long session, after a ship, or when a session opens with rapid swaps — never as a swap for the mission being avoided.

**Adaptation changes one variable at a time** — duration, visibility, ambiguity, social exposure, or technical complexity. High ship rate with no repeated blocker raises difficulty. Two consecutive skips reduce size or prompt a scope review. Something shipped to two rungs with no response drops a rung. Reported overwhelm never increases difficulty.

### 4.3 Interface, privacy, safety

Capabilities needed: managing what's being made, requesting and resolving missions, recording artifacts and shipping them to a rung, recording responses and an optional mood pair, retrieving the weekly mirror, and cohort aggregates. Authorisation is server-side on every resource — hidden UI controls are never the access-control mechanism. Mission submission is idempotent and recoverable.

Three data classes. **Private:** email, mood records, reflections, moderation reports, billing. **Shared-on-purpose:** display name, what they're making, deliberately shared artifacts. **Public:** only what the user explicitly selects, with AI assistance attributed. Administrators get aggregates, never reflections or per-user mood.

Moderation runs before publication — file-type restrictions, malware scanning, reporting, blocking, an audit trail, rate limits. Model output is constrained by prohibited categories, risk classification, schema validation, and prompt-injection resistance. Notifications are concrete, user-scheduled, and reduce after repeated dismissal.

> Good: *Your next step takes 15 minutes: write the rough opening paragraph.*
> Bad: *You are losing your streak.* / *Only 4 days left.*

Safeguarding obligations, and why the minor segment is **blocked** rather than scheduled, are [requirements](requirements.md) §11.

### 4.4 Failure modes

| Failure | Behaviour |
|---|---|
| Language model unavailable | Template missions serve every stage; no degradation in the core loop |
| Model output fails validation twice | Falls back to a template silently |
| Network drops mid-submission | Idempotent; the attempt is recoverable |
| A ship receives no response | Adaptation drops a rung to one with a guaranteed responder |
| A first ship gets no response | Rung one's responder is a named person, not a pool. If unreachable, the ship is held rather than sent onward |

### 4.5 Testing

Unit: mission schema validation, authored-hours arithmetic, ladder progression, permissions, stage transitions. Integration: anonymous first mission through registration without data loss, a first ship with a guaranteed responder, mood records staying private, mirror generation, deletion, model-failure fallback. End-to-end: opening to a first ship in one session without an account, a response recorded against an artifact, changing what's being made without losing evidence, an administrator seeing aggregates without mood or reflections.

**Model evaluation set:** 100+ fixed project states covering vague and overambitious projects, low energy, short windows, repeated avoidance, unshippable projects, unsafe requests, prompt injection, and interpersonal missions. Scored for specificity, feasibility, duration fit, shippability, safety, and preserved agency — which is why generation must be callable without a browser or database ([repo-structure](../roadmap/repo-structure.md)).

## 5. Alternatives considered

Eleven were drafted and rejected, and each one lives in the [decision log](../log/decision-log.md) with its reasoning and its cost: the fixed 30-day programme ([D-016](../log/decision-log.md)), forward deadline projection ([D-024](../log/decision-log.md)), the portfolio page as the promise ([D-026](../log/decision-log.md)), asking for scope and a finish line ([D-028](../log/decision-log.md)), the recall questionnaire ([D-030](../log/decision-log.md)), measuring no internal state at all ([D-031](../log/decision-log.md)), requiring an account first ([D-032](../log/decision-log.md)), crews at signup ([D-033](../log/decision-log.md)), a ladder ordered by intimacy ([D-043](../log/decision-log.md)), competing on blocking ([D-007](../log/decision-log.md)), and a single confidence score ([D-009](../log/decision-log.md)).

They were restated here for a while, which meant every reversal had to be written twice and one of the copies was always stale. The log is the record; this section is an index.

Treating fear directly with graded exposure is the one rejection with no decision of its own: fear is the last link, not the first, so exposure work treats a symptom. The discomfort machinery survives as `FR-032`, deliberately minor.

## 6. Third-party considerations

Two viable stacks: Next.js with Supabase for Postgres, auth, and storage using row-level security, or Next.js with self-managed PostgreSQL, an ORM, Auth.js, and S3-compatible storage. The trade is speed of first delivery against lock-in; the decision is the Architect's, and either satisfies this design. Everything else is conventional.

**The language model is the only dependency with an open-ended cost.** Contained by a provider-agnostic interface, template caching, per-user generation limits, and the requirement that every path degrade to templates. Cost per active user is measured during the first cohort, not estimated after launch.

## 7. Roll-out

| Phase | Contains | Proves |
|---|---|---|
| **0 — Concierge** | No product. Forms, a spreadsheet, hand-written missions, a guaranteed responder, unpaid, **18+ only** ([D-046](../log/decision-log.md)), with operator, responder and interviewer split ([D-047](../log/decision-log.md)) | That the loop works at all, and what the options should be. Also the first channel test ([D-044](../log/decision-log.md)) — the cohort is recruited from somewhere, and where that is, is data |
| **1 — Solo** | Auth, onboarding, templates, mission loop, evidence, ship missions, time mirror | That people ship in week one without community machinery |
| **2 — Reach** | Upper ladder rungs, moderation. Crews only if a cohort asks ([D-033](../log/decision-log.md)) | Whether a guaranteed audience changes ship rate |
| **3 — Institutional** | Cohort codes, aggregate dashboard, facilitator tools, data-processing terms | Distribution, and eventually willingness to pay |
| **4 — Personalisation** | Adaptive difficulty, blocker detection, template expansion | That completion improves without AI cost running away |

**Build order within phase 1:** templates and mission library, then the data model, then first mission, then ship flow and rung one, then the time mirror, then analytics. Templates come first because everything else degrades to them.

## 8. Open questions

1. **Where does anyone encounter this?** No channel is validated and there's no search demand ([D-044](../log/decision-log.md)). Nothing else here matters if this has no answer.
2. **Does a late response bring anyone back?** The only re-entry mechanism the principles permit, and a guess.
3. How large must a first response be before it changes how someone sees themselves?
4. Does reclaimed time sell, or does the finished thing sell?
5. Which project category ships fastest while still feeling like the user's own — and which survive the third template criterion at all?
6. Does anyone actually want a crew, or is it a barrier dressed as a feature?
7. How much facilitation does an acceptable ship rate require?
