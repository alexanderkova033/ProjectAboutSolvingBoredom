# Initial Product and Technical Design

**Product:** Freathe · **Status:** Draft — a starting position, not a ratified architecture · **Superseded by:** `architecture.md` after the BMAD Architect run · **Revised:** 2 August 2026

> **Related:** [Demand](demand.md) · [Requirements](requirements.md) · [BMAD path](../method/bmad-path.md) · [Repo structure](../roadmap/repo-structure.md) · [Decision log](../log/decision-log.md)

> No code, schemas, or interface definitions. They go stale faster than the decisions around them. What belongs here is the shape of the thing and the trade-offs behind it.

## 1. Overview

Turn an idle moment into one small act of making, get the result in front of a real person quickly, and show the user weekly how many hours they authored. It sells reclaimed time and proves it with something that exists outside their head.

**The platform is settled, and it is two things** ([D-051](../log/decision-log.md)). D-037 was right that beginners make almost no real artifacts on a phone, and drew the wrong conclusion from it — a desktop-only product is absent at the moment it claims to intervene, because boredom arrives on the phone. So the surfaces split by job: **the phone holds the trigger and one mission; the laptop is where the thing gets made.** Both are the same responsive web app, installed to the phone's home screen ([D-059](../log/decision-log.md)) — a native card was the better surface and is unreachable, since the beachhead carries iPhones and iOS wants a Mac, $99/year and an adult-held account. The seam between the two is an account, asked for after the introduction and not before it.

Goals and non-goals are [requirements](requirements.md) §4; principles are §3 there. Neither is restated — two copies drift, and these already had.

## 2. What the design depends on

- **Boredom is upstream**, so the intervention is making, not fear-management ([D-023](../log/decision-log.md)).
- **The last link is a verdict, not a cause**, so the design disputes it with a record and never names it ([D-027](../log/decision-log.md)).
- **Autonomy is load-bearing.** A prescribed programme reproduces what makes courses inert ([D-028](../log/decision-log.md)).
- **Payoff must arrive fast.** Creating can't win on ease, only on payoff size, and only if it arrives soon enough to compete. And **the session being enjoyable is the primary reason anyone returns** ([D-056](../log/decision-log.md)) — which means competing with entertainment on a different pleasure, not on ease.
- **The internet's default response is silence.** External validation has to be engineered, not hoped for.
- **Freedom, and consequence** ([D-042](../log/decision-log.md)). Discipline isn't available as a mechanism: nothing is scheduled or owed, and leaving is free at every point. The job is making the *invisible* consequence visible, never the one already felt.

## 3. Product design

### 3.1 Surfaces

**Home screen** — an icon the user installs, opening straight onto one mission and nothing else ([D-059](../log/decision-log.md)). **Now** — the same mission on the laptop, with controls to start, swap, shrink, or flag a blocker. No selector. **Project** — what's being made, stages, things made. **Evidence** — what was made, what shipped, what came back. **Profile** — privacy, notifications, export, deletion. Administrators get **Cohort**. A **Crew** surface is specified but unscheduled ([D-033](../log/decision-log.md)).

### 3.2 Key flows

**Welcome.** *Your evenings are going somewhere. This is how you get them back.*

**Pick something.** No questionnaire, no account, no goal-setting — a small set of real, concrete things the user could make, each shown as the thing itself with an example of someone's finished version: a researched explainer, a simple tool, a product concept, a local problem-and-solution report, a short visual or audio story, a tiny service experiment. The choice is the signal, and what they passed over is recorded too.

**No scope screen and no date screen exist.** The 72-hour first ship keeps work small without anyone declaring a size; the absence of a deadline is the point, not an omission.

**The loop.** One mission is already on screen. It carries a title, an instruction, and one definition of done — but **no duration**, because telling someone a task takes twenty minutes gives them a reason to postpone it. The engine still records one and sizes the next mission from it; the user never sees the number, on any surface, including notifications ([D-048](../log/decision-log.md)). Start, swap, shrink, or say what's in the way. When it's done the next is right there. Stopping needs no action and produces no comment.

**The home-screen surface** ([D-049](../log/decision-log.md), [D-059](../log/decision-log.md), [D-061](../log/decision-log.md)). An icon the user installs and puts on the first page, opening straight onto the current mission — title and definition of done, and nothing else. **No count, total, streak, or elapsed time**: the weekly mirror is something the user goes and looks at, while this sits where they look fifty times a day without choosing to, and that is the exact condition under which a number stops being a record and becomes a demand. Opening it **starts**; swapping is a smaller, secondary target, because a surface whose cheapest gesture is *give me a different one* teaches swapping (`FR-056`). It draws from the cached template library, so it works with no network and no account, is never empty, and never shows an error (`FR-055`).

It is a **pull surface**, and that is the whole argument for it. **The user puts it there** — it is placed, not delivered, and dragging it off takes two seconds with nothing asking why. That is the difference from a notification, which arrives whether or not it was wanted. It cannot interrupt an open mission (`NFR-012`); it is there when the phone is picked up and does nothing when it isn't. That is the only shape of re-entry the principles permit — and it is a surface rather than a reason, so it removes an excuse and answers nothing about motivation.

**Be honest about what was lost — and about what wasn't** ([D-061](../log/decision-log.md)). The intended surface was a live card showing the mission itself, with nothing to open, and the whole force of *one thing already on the screen* came from the word *already*. **That does not survive.** An icon says *this exists*, never *do this*, so the decision a mission exists to remove sits back on the user until they tap, and native is the only way to close it ([D-059](../log/decision-log.md)).

**What survives is placement.** An icon on the *first* home-screen page is in the visual field at unlock, without being looked for — which is the property [D-049](../log/decision-log.md) was actually buying, and choosing page one is a more deliberate act of placing than leaving it in an app drawer. So the install asks for it once, in plain words, with the reason, and never asks again (`FR-057`). It then competes for that page against applications engineered to be tapped, carrying no badge and no count, which means it wins on placement or not at all.

**Measure the cost rather than assuming it away.** If installs happen and openings don't, two different things could be true — it was never on page one, or it was and nobody wanted it — and **the product cannot see which**, because it cannot see where its own icon sits. So the exit interview asks where they put it and whether they noticed it. Without that answer a dead icon is uninterpretable; with it, and if the answer is *page one, saw it, didn't open it*, the missing tap is the reason and it is the strongest argument that will ever exist for buying a Mac.

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

**Your own work, cold** ([D-055](../log/decision-log.md), `FR-038`). Something made weeks ago, shown back for review with no prompt about how to feel about it — the same move as the record screen above, with your past output as the external thing. And before a ship, optionally: *what would you want someone to notice?* It surfaces what you actually care about and gives the eventual response something to land against.

**None of this is a response.** A self-response never satisfies a rung's guarantee, never counts as external, never enters `response rate` (`FR-039`). The temptation is obvious and arrives exactly when the pool is dry: it costs nothing, scales infinitely, and feels like it worked. It is the mood without the evidence, and this product's entire claim is the difference between those two. **When nothing came back, the product says nothing.**

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
| **Mission** | Instruction, definition of done, duration, difficulty, stage, and a **kind** — *produce*, *distribute*, or *reset* | Shipping as a kind rather than a phase is what stops distribution being deferred forever. The kind field is also what makes the reset exclusion enforceable rather than a convention ([D-040](../log/decision-log.md)). Duration is an **engine input, never a display field** ([D-048](../log/decision-log.md)) — it exists so adaptation can size the next one |
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

Moderation runs before publication — file-type restrictions, malware scanning, reporting, blocking, an audit trail, rate limits. Model output is constrained by prohibited categories, risk classification, schema validation, and prompt-injection resistance.

**Nothing is scheduled** ([D-049](../log/decision-log.md)). The home-screen surface is where a next mission appears, silently, and the only thing the product sends unbidden is a response that arrived (`FR-067`) — news, with nothing attached.

> Good: *Someone read the thing you sent on Tuesday and wrote back.*
> Bad: *You are losing your streak.* / *Only 4 days left.* / *Your next step takes 15 minutes* — a duration, on the surface most likely to be read as a demand ([D-048](../log/decision-log.md)).

Safeguarding obligations, and why the minor segment is **blocked** rather than scheduled, are [requirements](requirements.md) §11.

### 4.4 Failure modes

| Failure | Behaviour |
|---|---|
| Language model unavailable | Template missions serve every stage; no degradation in the core loop |
| Model output fails validation twice | Falls back to a template silently |
| Network drops mid-submission | Idempotent; the attempt is recoverable |
| A ship receives no response | Adaptation drops a rung to one with a guaranteed responder |
| A first ship gets no response | Rung one's responder is a named person, not a pool. If unreachable, the ship is held rather than sent onward |
| The home-screen surface has no network, or no account yet | Draws from the local template library (`FR-055`). Never empty, never an error — an error on a home screen is worse than a stale mission |

### 4.5 Testing

Unit: mission schema validation, authored-hours arithmetic, ladder progression, permissions, stage transitions. Integration: anonymous first mission through registration without data loss, a first ship with a guaranteed responder, mood records staying private, mirror generation, deletion, model-failure fallback. End-to-end: opening to a first ship in one session without an account, a response recorded against an artifact, changing what's being made without losing evidence, an administrator seeing aggregates without mood or reflections.

**Model evaluation set:** 100+ fixed project states covering vague and overambitious projects, low energy, short windows, repeated avoidance, unshippable projects, unsafe requests, prompt injection, and interpersonal missions. Scored for specificity, feasibility, duration fit, shippability, safety, and preserved agency — which is why generation must be callable without a browser or database ([repo-structure](../roadmap/repo-structure.md)).

## 5. Alternatives considered

Eleven were drafted and rejected, and each one lives in the [decision log](../log/decision-log.md) with its reasoning and its cost: the fixed 30-day programme ([D-016](../log/decision-log.md)), forward deadline projection ([D-024](../log/decision-log.md)), the portfolio page as the promise ([D-026](../log/decision-log.md)), asking for scope and a finish line ([D-028](../log/decision-log.md)), the recall questionnaire ([D-030](../log/decision-log.md)), measuring no internal state at all ([D-031](../log/decision-log.md)), requiring an account first ([D-032](../log/decision-log.md)), crews at signup ([D-033](../log/decision-log.md)), a ladder ordered by intimacy ([D-043](../log/decision-log.md)), competing on blocking ([D-007](../log/decision-log.md)), and a single confidence score ([D-009](../log/decision-log.md)).

They were restated here for a while, which meant every reversal had to be written twice and one of the copies was always stale. The log is the record; this section is an index.

Treating fear directly with graded exposure is the one rejection with no decision of its own: fear is the last link, not the first, so exposure work treats a symptom. The discomfort machinery survives as `FR-032`, deliberately minor.

## 6. Third-party considerations

Two viable stacks for the laptop half: Next.js with Supabase for Postgres, auth, and storage using row-level security, or Next.js with self-managed PostgreSQL, an ORM, Auth.js, and S3-compatible storage. The trade is speed of first delivery against lock-in; the decision is the Architect's, and either satisfies this design. Everything else is conventional.

**There is no native client** ([D-059](../log/decision-log.md)). The phone surface is the same web app, installed to the home screen and cached for offline use. That was not the first choice — the first choice was an Android widget forked from the sibling SapGlance repo, and the engineering case for it was strong. The market case was not: the reachable segment carries iPhones, and iOS refuses a live home-screen card to anything but a native app, which wants a Mac, $99 a year, and an account only an adult can hold.

What the SapGlance work still contributes is a rule rather than a codebase: its selection engine lives in a module with **zero Android imports**, testable on a plain JVM, and that is the same constraint [repo structure](../roadmap/repo-structure.md) independently places on `record` and `ai`. The domain logic never imports the surface. Two products, two routes to one rule.

**One thing to watch rather than assume.** Offline mission delivery on an installed web app is a service worker and a cached template library, which is ordinary — but iOS has historically been the weakest platform for exactly this, and eviction of stored data is its own failure mode. Assume nothing, test on a real iPhone early, and treat `FR-055`'s *never empty, never an error* as the thing most likely to break first.

**The language model is the only dependency with an open-ended cost.** Contained by a provider-agnostic interface, template caching, per-user generation limits, and the requirement that every path degrade to templates. Cost per active user is measured during the first cohort, not estimated after launch.

## 7. Roll-out

| Phase | Contains | Proves |
|---|---|---|
| **0 — Concierge** | No product. Forms, a spreadsheet, hand-written missions, a guaranteed responder, unpaid, **18+ only** ([D-046](../log/decision-log.md)), with operator, responder and interviewer split ([D-047](../log/decision-log.md)) | That the loop works at all, and what the options should be. Also the first channel test ([D-044](../log/decision-log.md)) — the cohort is recruited from somewhere, and where that is, is data |
| **1 — Solo** | Auth, onboarding, templates, mission loop, evidence, ship missions, time mirror, **installable home-screen surface** ([D-059](../log/decision-log.md)) | That people ship in week one without community machinery |
| **2 — Reach** | Upper ladder rungs, moderation. Crews only if a cohort asks ([D-033](../log/decision-log.md)) | Whether a guaranteed audience changes ship rate |
| **3 — Institutional** | Cohort codes, aggregate dashboard, facilitator tools, data-processing terms | Distribution, and eventually willingness to pay |
| **4 — Personalisation** | Adaptive difficulty, blocker detection, template expansion | That completion improves without AI cost running away |

**Build order within phase 1:** templates and mission library, then the data model, then first mission, then ship flow and rung one, then the time mirror, then analytics, then the card. Templates come first because everything else degrades to them — **including the card**, which renders from them with no network and no account (`FR-055`), so it cannot be built before they exist. It comes last within the phase for the same reason it comes at all: it is the surface that brings someone back to a loop, and there has to be a loop first.

## 8. Open questions

1. **Where does anyone encounter this?** No channel is validated and there's no search demand ([D-044](../log/decision-log.md)). Nothing else here matters if this has no answer.
2. **Does a late response bring anyone back?** The only re-entry *reason* the principles permit, and a guess. The home-screen icon ([D-049](../log/decision-log.md), [D-061](../log/decision-log.md)) is a re-entry *surface* and does not answer this — it makes returning cheap and supplies no motive.
3. **Does an installed icon get opened — and if it doesn't, was it ever on the first page?** Two failures look identical from inside the product and only one of them is about motive ([D-061](../log/decision-log.md)), so this is asked in the exit interview rather than measured. If it was placed, seen, and still not opened, the missing tap is why — and that is the only argument that would ever justify the cost of going native ([D-059](../log/decision-log.md)).
4. How large must a first response be before it changes how someone sees themselves?
5. Which of reclaimed time and the finished thing is legible to a funder — and what is the fundable unit, now that completion isn't one ([D-050](../log/decision-log.md), [D-060](../log/decision-log.md))?
6. Which project category ships fastest while still feeling like the user's own — and which survive the third template criterion at all?
7. Does anyone actually want a crew, or is it a barrier dressed as a feature?
8. How much facilitation does an acceptable ship rate require?
