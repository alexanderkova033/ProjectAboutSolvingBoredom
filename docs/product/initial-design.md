# Initial Product and Technical Design

| | |
|---|---|
| **Product** | ForgePath *(placeholder name — to be replaced)* |
| **Status** | Draft — a starting position, not a ratified architecture |
| **Author** | alexanderkova033 |
| **Last revised** | 1 August 2026 |
| **Superseded by** | `architecture.md`, after the BMAD Architect run |
| **Reviewers** | None yet |

> **Related:** [Demand](demand.md) · [Requirements](requirements.md) · [BMAD path](../method/bmad-path.md) · [Repo structure](../roadmap/repo-structure.md) · [Decision log](../log/decision-log.md)

> Deliberately contains no code, schemas, or interface definitions. Those are verbose, carry detail that isn't load-bearing at this stage, and go stale faster than the decisions around them. What belongs here is the shape of the thing and the trade-offs behind it.

## 1. Overview

People spend evenings consuming and end them feeling the time was lost. Existing tools fight for *less* — blocking apps, capping screen time — and hand nothing back.

This is a product that turns an idle moment into one small act of making, gets the result in front of a real person quickly, and shows the user, weekly, how many hours they authored. It sells reclaimed time; it proves that time with something that exists outside the user's head.

**The platform is an open decision** ([D-037](../log/decision-log.md)). This document previously assumed mobile-first web, which no longer follows: the missions produce real artifacts — writing, tools, designs, recordings — and almost none of that is made on a phone. The recommendation is desktop web, with mobile at most a thin later surface for the moment boredom actually strikes. Nothing else in this design depends on the answer.

## 2. Background

The full argument is in [demand.md](demand.md). What the design depends on:

- **Boredom is upstream.** The chain runs boredom → consumption → not creating → no confidence → fear → *"I'm just lazy"*, and the last link feeds the first. Because boredom is first, the intervention is making, not fear-management ([D-023](../log/decision-log.md)).
- **The last link is a verdict, not a cause.** Laziness is what users report while fear is what happens, and it is the only link phrased as an identity — which is what makes the loop stable. The design disputes it with a record and never names it ([D-027](../log/decision-log.md)).
- **Autonomy is load-bearing.** A prescribed programme reproduces what makes courses inert. The user picks what to make; the product never asks how big or by when ([D-016](../log/decision-log.md), [D-028](../log/decision-log.md)).
- **Payoff must arrive fast.** Creating will always be harder than consuming, so it can't win on ease — only on payoff size, and only if the payoff arrives soon enough to compete.
- **The internet's default response is silence.** Any design promising external validation must engineer it rather than hope for it.

## 3. Goals and non-goals

**Goals**

1. First mission started within ten minutes of opening the product, **without an account**; something shipped within 72 hours.
2. Make authored hours visible and undeniable, without scoring the user.
3. Guarantee that a first ship receives a response.
4. Keep the core loop completable in five minutes.
5. Degrade to full usefulness without the language model.

**Non-goals**

Diagnosing or treating anything · promising happiness, income, or the removal of boredom · a public feed or general social network · users under 16 · blocking third-party apps · generating the user's work · streaks, badges, or any punitive mechanic.

**Future goals** — deliberately out of this design: crew matching, native mobile, blocker integrations, employer matching, adaptive personalisation. See [future-plans.md](../roadmap/future-plans.md).

## 4. Product design

### 4.1 Principles

1. **Show, don't tell.** Show what the user can do. Never tell them what to feel, what to achieve, or what they already know about themselves ([D-029](../log/decision-log.md)).
2. **The session must be good to be in.** Enjoyable while it happens, not only rewarding afterwards. Every cheap route is banned — streaks, points, badges, confetti — which leaves the real ones: a task worth doing, visible change under the user's hands, speed, and an interface that stays quiet ([D-035](../log/decision-log.md)).
3. **Never ask what they want to improve.** They don't know. That is the condition, not a gap to fill in before starting ([D-036](../log/decision-log.md)).
4. **Present tense.** Anything living in *will* (countdowns, deadlines, goal ceremonies) or *have* (badges, streaks, trophies, portfolio-as-achievement) does not ship. A filter to run against every screen, not a sentiment ([D-024](../log/decision-log.md)).
5. **No scope, no finish line.** Never ask how big or by when. When someone is doing what they want, those questions don't help, and the pressure they add is a reason people stop ([D-028](../log/decision-log.md)).
6. **One next action.** The default screen shows one mission, never a backlog.
7. **The user decides; the product proposes.** Every suggestion is a default with a visible override.
8. **Choice reveals preference.** Don't ask what they love — they know, and asking changes nothing. Show real options and record which one they take ([D-030](../log/decision-log.md)).
9. **Nothing required to start.** No account, no questionnaire, no goal-setting in front of the first mission ([D-032](../log/decision-log.md)).
10. **Ship early, ship small.** Work nobody sees isn't progress.
11. **No first ship into a void.**
12. **Boredom is faced, not removed.** When scrolling stops it arrives undiluted. Say so.
13. **Never describe the user, only what they did.** Nothing may imply they are lazy, behind, or failing ([D-027](../log/decision-log.md)).
14. **AI is scaffolding, never the creator of record.**

### 4.2 Surfaces

**Now** — one mission, already on screen, with controls to start, swap, shrink, or flag a blocker. No selector of any kind. **Project** — what is being made, stages, things made so far. **Evidence** — what was made, what shipped, what came back. **Profile** — privacy, notifications, export and deletion. Administrators get a separate **Cohort** area. A **Crew** surface is specified but unscheduled ([D-033](../log/decision-log.md)).

### 4.3 Key flows

**Welcome.** *Your evenings are going somewhere. This is how you get them back.*

**Pick something.** No questionnaire, no account, no goal-setting. The first screen after the welcome is a small set of real, concrete things the user could make — a researched explainer, a simple tool, a product concept, a local problem-and-solution report, a short visual or audio story, a tiny service experiment for a real person. Each shown as the thing itself, with an example of what someone else's finished version looked like.

They pick one and start. The choice is the signal; nothing is asked about their interests ([D-030](../log/decision-log.md)). What they passed over is recorded too.

**No scope screen and no date screen exist** ([D-028](../log/decision-log.md)). The user is never asked how big the thing is or when it will be done. The 72-hour first ship keeps the work small without anyone having to declare a size, and the absence of a deadline is the point rather than an omission.

**The loop.** Open it, and one mission is already on screen. No time question, no sizing question, no menu ([D-034](../log/decision-log.md)).

The card carries a title, an instruction, and one definition of done. It does **not** show a duration — every mission is small enough to start now, and telling someone a task will take twenty minutes gives them a reason to postpone it. The user can start, swap it, make it smaller, or say what's in the way.

When it's done, the next one is right there if they want it. Stopping needs no action and produces no comment. Duration is **observed, not declared** — the session records how long it actually took, which is better data than an estimate and no work for the user.

**Session feeling.** One tap before, one tap after — a small row of faces or a 1–5, no words, no explanation asked for. Skippable and skippable permanently. The user can see their own history; nobody else ever can, it is never turned into a score or a profile, and the product never comments on it ([D-031](../log/decision-log.md)).

This is the single exception to measuring only behaviour, and it earns the exception by being the only direct measure of the promise: that the time felt different afterwards. The distinction that keeps it safe is the subject — the product never rates the user; the user rates a session.

**Ship.** The audience ladder, one rung at a time, each guaranteed to respond before the next unlocks: one person the user already knows → one stranger who fits the thing → a small public. In hand-run cohorts the operator is the guaranteed responder for rung one. The user chooses the rung; the product never routes a first ship somewhere silence is likely.

**The first reckoning — at 72 hours, and the model for every mirror after it.** Two screens, in this order ([D-038](../log/decision-log.md)).

First, one question in the user's own words:

> *What have you got done so far?*

Free text, no numbers requested, no list to fill in, skippable. It fires only if there is something in the record — asking what someone achieved when they achieved nothing is the worst screen in the product.

Then the record, beside their answer:

> **You said:** *not much really, messed about with the intro*
>
> **Recorded:** 3 sessions · 1 hour 40 minutes · 2 things made · 1 shipped · 1 response

**Nothing narrates the gap.** No delta, no arrow, no percentage, no *"actually"*, no *"you did more than you thought"*. Both are simply present. If the user notices, the noticing is theirs — the product pointing it out would be the product describing the user, which is banned.

This runs the other way sometimes. Someone will say they did loads and the record will say forty minutes. That screen looks identical: both shown, neither judged, nothing flagged. A record that only speaks up when it's flattering isn't a record.

**Words for it.** Offered after the record, and again on the receipt ([D-039](../log/decision-log.md)). Not a valuation — a sentence they could actually use, assembled only from facts already in the record:

> **For a personal statement**
>
> *"I built and published a small tool that converts handwritten recipe cards into a searchable list. Three people used it; one asked for a change and I made it the same week."*
>
> [ Copy ] [ Reword ] · For: **personal statement** / interview answer / application form
>
> **What's in the record, plainly:** returned to it on 7 separate days · revised after feedback from someone outside the project · published it publicly

The audience selector matters: persona D is writing to admissions, personas A–C to employers, and the same facts want different sentences.

**Three hard rules.** The product never says the work is impressive, valuable, or what a reader will think of it — that claim is unfalsifiable and it is precisely where every competitor in this category over-claims. It never names an outcome, a company, or a course. And it **never inflates**: one small thing is described as one small thing, because a padded sentence collapses under the first follow-up question in the room, which is the same way an AI-written artifact fails ([D-005](../log/decision-log.md)).

The sentence is a draft the user edits, not a certificate the product issues.

**Time mirror.** Weekly thereafter, same shape, with the self-report step becoming occasional rather than every time. Backward-looking: hours authored, things made, things shipped, responses received. No target, no projection, no red, no comparison to other users.

Its job is narrow and worth stating: **make *"I'm just lazy"* untenable against a record.** Not to inform, not to motivate — to dispute a verdict the user has already passed on themselves. That is why it counts what was made and stays silent about the rest, and why a low week must still read as a record rather than a shortfall. If it ever reads as judgment it has become the thing the product is fighting.

After two stalled weeks, one question: *is this still the thing you want to be making?* Shown alongside what they picked and passed over at the start. Dropping it is a good outcome.

**Completion.** A page recording what the thing is, what it took, and what came back. A receipt that the hours were real — generated as a by-product, never presented as the reason for the work ([D-026](../log/decision-log.md)).

## 5. Detailed design

### 5.1 Domain model

The important structural decision is that **making, shipping, and being responded to are three separate things**. An earlier model recorded that work happened but not that it landed — which is the only thing this thesis cares about.

| Entity | Holds | Why it's separate |
|---|---|---|
| **Project** | Title, artifact type, stage, visibility | Deliberately holds **no target date and no scope estimate** ([D-028](../log/decision-log.md)). There is no field to leave blank and no field to nag about, because the schema shouldn't make a deadline easy to add back later |
| **Session mood** | An optional pair of taps, before and after a session | Stored against the session and only ever readable by its owner. Kept separate from every other record so no query can accidentally join it to a profile ([D-031](../log/decision-log.md)) |
| **Mission** | Instruction, definition of done, duration, difficulty, stage, and a **kind** — *produce*, *distribute*, or *reset* | Making shipping a mission kind rather than a phase is what stops distribution being deferred forever. *Reset* missions (go outside, clear the table) are modelled as missions but excluded from every production total — the kind field is what makes that exclusion enforceable rather than a convention ([D-040](../log/decision-log.md)) |
| **Mission attempt** | Attempted, completed, blocker, optional predicted and actual discomfort | Attempts are preserved separately from missions so a skip is data rather than an absence |
| **Artifact** | The thing itself, and when it shipped | Distinct from evidence-of-work. Evidence proves effort; an artifact is what a stranger could actually receive |
| **Ship** | An artifact sent to one rung of the ladder, and the guaranteed responder for that rung | Modelling the rung explicitly is what makes "no first ship into a void" enforceable rather than aspirational |
| **Response** | An external reaction, its kind, and **whether it came from someone who knows the user** | A friend's kindness and a stranger's use are not the same evidence and must not be counted together |
| **Production session** | Minutes, and whether anything was produced | The unit the time mirror sums. Time is the product, so time is a first-class record |

Projects own missions and artifacts; artifacts own ships; ships own responses; users own sessions. Private reflections and session-mood records sit under stricter row-level policies than anything shippable, and are stored apart from anything that could reach a public page.

### 5.2 Mission generation

Generation takes the project stage, the definition of done, remaining milestones, observed session lengths, experience, recent blockers, and what already exists. **It is never given a time budget**, because the user is never asked for one ([D-034](../log/decision-log.md)) — the system infers a workable size from how long their sessions have actually run.

A generated mission must start with one observable verb, produce or ship something real, be small enough to start immediately, carry a testable definition of done, cover one task rather than several, and never produce the user's work for them. Difficulty sits mostly at 2–4.

> Bad: *Think about your target customer.*
> Better: *Write three sentences on one customer, the moment the problem hits, and what they do instead.*

Output is validated against a strict schema; two consecutive failures fall back to a hand-written template mission. Every project stage has template coverage, so the product is fully usable with the model switched off entirely.

**Distribution missions are first-class.** Every template carries ship-shaped missions, and the generator must offer one as soon as anything is shippable.

**Reset missions are the exception to "produce something real"** ([D-040](../log/decision-log.md)). *Go outside for ten minutes. Clear the table you're working at. Put the thing down and come back tomorrow.*

They are framed as **conditions for making**, never as wellbeing — a cleared table removes the reason you won't start, and going outside is what you do when ninety minutes of staring hasn't worked. That framing is the only thing separating this from the generic tip-app genre, which the demand doc scores at the bottom of the market.

Three constraints, all enforceable rather than advisory:

- **They never count** toward authored hours, things made, or things shipped. The record's value is that it is true; padding it with walks would destroy the thing that disputes the verdict.
- **One per session, maximum**, and they never accumulate.
- **Never offered as a swap for a mission the user is avoiding.** They punctuate work; they don't replace it. Otherwise the product becomes a well-designed way to procrastinate.

Offered when a blocker is reported, after a long session, after a ship, or when a session opens with several rapid swaps.

**Adaptation changes one variable at a time** — duration, visibility, ambiguity, social exposure, or technical complexity. A high ship rate with no repeated blocker raises difficulty. Two consecutive skips reduce mission size or prompt a scope review. Something shipped to two rungs with no response drops a rung to one with a guaranteed responder. Reported overwhelm never increases difficulty.

### 5.3 Templates

Templates are authored by hand before any model involvement — the model adapts a tested path, it does not invent the pedagogy. Two selection criteria decide what enters the library: a first version must ship in days, and someone must plausibly want the result. A template that cannot answer *who would want this* does not go in.

### 5.4 Measurement

Four transparent quantities, never combined into a score: authored hours, things made, things shipped, responses received. No internal state is ever rated. The user is shown the evidence and draws their own conclusion — which is also the only version consistent with the agency principle, since the conclusion is theirs to reach.

### 5.5 Interface surface

The application needs capabilities for: managing what is being made, requesting and resolving missions, recording artifacts and shipping them to a rung, recording responses against a ship, recording an optional session-mood pair, retrieving the weekly mirror, and aggregate cohort metrics for administrators.

Authorisation is enforced server-side on every resource. Hidden UI controls are never the access-control mechanism. Mission submission is idempotent and recoverable after a network interruption, because the core loop runs on phones with bad connections.

### 5.6 Privacy and safety

Three data classes. **Private:** email, session-mood records, reflections, moderation reports, billing. **Shared-on-purpose:** display name, what they are making, deliberately shared artifacts. **Public:** only what the user explicitly selects, with AI assistance attributed. Administrators receive aggregate metrics and never reflections or per-user mood.

Content moderation runs before crew publication, with file-type restrictions, malware scanning, reporting, blocking, a moderator audit trail, and rate limits. Model output is constrained by prohibited mission categories, risk classification, schema validation, and prompt-injection resistance for user-supplied project text, with escalation to a human for ambiguous flags.

Notifications are concrete, user-scheduled, and reduce in frequency after repeated dismissal. No shame, no false urgency, no countdowns.

> Good: *Your next step takes 15 minutes: write the rough opening paragraph.*
> Bad: *You are losing your streak.* / *Only 4 days left.*

For minors, additional constraints apply: guardian consent, no mixed-age crews, no direct messaging, private-by-default publishing, and a named responsible adult per cohort. See [requirements](requirements.md) §11.

### 5.7 Failure modes

| Failure | Behaviour |
|---|---|
| Language model unavailable | Template missions serve every stage; the user sees no degradation in the core loop |
| Model output fails validation twice | Falls back to a template mission silently |
| Network drops mid-submission | Submission is idempotent; the attempt is recoverable |
| A ship receives no response | Adaptation drops a rung to one with a guaranteed responder |
| A first ship gets no response | The guaranteed responder for rung one is a named person, not a pool. If they are unreachable the ship is held rather than sent onward |

### 5.8 Testing

Unit coverage for mission schema validation, authored-hours arithmetic, ladder progression, permission rules, and stage transitions. Integration coverage for anonymous first mission through to registration without data loss, a first ship with a guaranteed responder, session-mood records staying private, time-mirror generation, account deletion, and model-failure fallback. End-to-end coverage for opening the product to a first ship in one session without an account, a response recorded against an artifact, changing what is being made without losing prior evidence, a minor account blocked from public publishing, and an administrator seeing aggregates without per-user mood or reflections.

**Model evaluation set:** at least 100 fixed project states covering vague and overambitious projects, low energy, short time windows, repeated avoidance, unshippable projects, unsafe requests, prompt injection, and interpersonal missions. Scored for specificity, feasibility, duration fit, shippability, safety, and preserved user agency. This is why the generation and scoring rules must be callable without a browser or database — see [repo-structure.md](../roadmap/repo-structure.md).

## 6. Alternatives considered

**A fixed 30-day programme.** Rejected. A prescribed container removes the independence of choice that resolving boredom depends on, and reproduces the thing that makes courses inert. Cost accepted: "in 30 days" was concrete marketing and a genuine deadline effect, and both are given up ([D-016](../log/decision-log.md)).

**A forward deadline projection at the weekly review** — *at this rate you finish in February.* Rejected after being drafted. It is a *will*-tense mechanic: future anxiety wearing the costume of information. Replaced by the backward-looking time mirror ([D-024](../log/decision-log.md)).

**The portfolio page as the product's promise.** Rejected. Things you *have* devalue — a portfolio page is worth little in five years, while hours authored do not devalue. The page survives as a receipt ([D-026](../log/decision-log.md)).

**Treating fear directly, with graded exposure.** Rejected. Fear is the last link in the chain, not the first, so exposure work treats a symptom. The discomfort-prediction machinery is retained but deliberately minor.

**Crews at all, for now.** Deferred to *maybe* ([D-033](../log/decision-log.md)). A social component at signup is a barrier for precisely the person this targets — someone already avoiding being seen. This breaks the audience ladder's original first rung, which assumed a crew; rung one becomes one person the user already knows, and in hand-run cohorts the operator is the guaranteed responder. Crews remain specified in the requirements so the work isn't lost.

**Asking the user for scope and a finish line.** Rejected ([D-028](../log/decision-log.md)). It survived the removal of the fixed 30-day programme and shouldn't have — the deadline projection was already cut as a *will* mechanic while the date feeding it was left in place. When someone is doing what they actually want, size and deadline are irrelevant, and the pressure they add is itself a reason people stop.

**A recall questionnaire at onboarding.** Rejected ([D-030](../log/decision-log.md)). *"When did you last lose track of time?"* is a self-help cliché and, worse, redundant: people already know what absorbs them. Knowing was never the missing piece. Replaced by showing real options and recording the pick.

**Requiring an account before the first mission.** Rejected ([D-032](../log/decision-log.md)). Registration in front of value is a gate on the only thing that matters. Cost accepted: anonymous sessions complicate storage, analytics, and the age gate.

**Measuring no internal state at all.** Rejected in one narrow place ([D-031](../log/decision-log.md)). A before/after session pair is the only direct evidence that the time felt different, which is the actual promise. It is safe only because the user is the one rating, and the rating never becomes a score.

**Competing on blocking.** Rejected. The category is crowded and it is not where this differentiates — what appears *after* the block is. Integration with existing blockers stays open as future work ([D-007](../log/decision-log.md)).

**A single confidence score.** Rejected. Unfalsifiable, invites comparison, and drifts toward measuring the person rather than the behaviour ([D-009](../log/decision-log.md)).

## 7. Third-party considerations

Two viable stacks. The fastest managed path is Next.js with Supabase for Postgres, auth, and storage, using row-level security. The more portable path is Next.js with self-managed PostgreSQL, an ORM, Auth.js, and S3-compatible storage. The trade is speed of first delivery against lock-in; the decision is the Architect's to make, and either satisfies this design.

Everything else is conventional: managed hosting, error monitoring, privacy-conscious analytics, and transactional email.

**The language model is the only dependency with an open-ended cost.** It is contained by a provider-agnostic interface, template caching, per-user generation limits, and the requirement that every path degrade to templates. Cost per active user must be measured during the first cohort, not estimated after launch. Model choice is deliberately not made here.

**Data protection.** A UK deployment involving minors engages UK GDPR and the ICO Age Appropriate Design Code, and a school pilot engages that school's safeguarding policy. These are identified, not discharged — see [requirements](requirements.md) §11.

## 8. Roll-out

| Phase | Contains | Proves |
|---|---|---|
| **0 — Concierge** | No product. Forms, a spreadsheet, hand-written missions, the operator as guaranteed responder, unpaid | That the loop works at all, and what the options should be |
| **1 — Solo** | Auth, recall, onboarding, templates, mission loop, evidence, ship missions, time mirror | That people ship in week one without community machinery |
| **2 — Reach** | Upper ladder rungs, moderation. Crews only if the cohort asks for them ([D-033](../log/decision-log.md)) | Whether a guaranteed audience changes ship rate |
| **3 — Institutional** | Cohort codes, aggregate dashboard, facilitator tools, data-processing terms | Distribution, and eventually willingness to pay |
| **4 — Personalisation** | Adaptive difficulty, blocker detection, template expansion | That completion improves without AI cost running away |

**Build order within phase 1:** hand-written templates and mission library first, then the data model, then recall through first mission, then the ship flow and first ladder rung, then the time mirror, then analytics. The templates come first because everything else degrades to them.

## 9. Open questions

1. How large must a first response be before it changes how someone sees themselves? A crew member being kind may be dismissible as politeness; a stranger's use is not.
2. Does reclaimed time sell, or does the finished thing sell? The demand doc leaves this deliberately unresolved.
3. Which project category ships fastest while still feeling like the user's own?
4. Does anyone actually want a crew, or is it a barrier dressed as a feature?
5. How much facilitation does an acceptable ship rate require?
