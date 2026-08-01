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

This is a mobile-first web product that turns an idle moment into one small act of making, gets the result in front of a real person quickly, and shows the user, weekly, how many hours they authored. It sells reclaimed time; it proves that time with something that exists outside the user's head.

## 2. Background

The full argument is in [demand.md](demand.md). What the design depends on:

- **Boredom is upstream.** The chain runs boredom → consumption → not creating → no confidence → fear → *"I'm just lazy"*, and the last link feeds the first. Because boredom is first, the intervention is making, not fear-management ([D-023](../log/decision-log.md)).
- **The last link is a verdict, not a cause.** Laziness is what users report while fear is what happens, and it is the only link phrased as an identity — which is what makes the loop stable. The design disputes it with a record and never names it ([D-027](../log/decision-log.md)).
- **Autonomy is load-bearing.** A prescribed programme reproduces what makes courses inert. The user picks project, scope, and finish line ([D-016](../log/decision-log.md)).
- **Payoff must arrive fast.** Creating will always be harder than consuming, so it can't win on ease — only on payoff size, and only if the payoff arrives soon enough to compete.
- **The internet's default response is silence.** Any design promising external validation must engineer it rather than hope for it.

## 3. Goals and non-goals

**Goals**

1. First mission accepted within ten minutes of signup; something shipped within 72 hours.
2. Make authored hours visible and undeniable, without scoring the user.
3. Guarantee that a first ship receives a response.
4. Keep the core loop completable in five minutes.
5. Degrade to full usefulness without the language model.

**Non-goals**

Diagnosing or treating anything · promising happiness, income, or the removal of boredom · a public feed or general social network · users under 16 · blocking third-party apps · generating the user's work · streaks, badges, or any punitive mechanic.

**Future goals** — deliberately out of this design: crew matching, native mobile, blocker integrations, employer matching, adaptive personalisation. See [future-plans.md](../roadmap/future-plans.md).

## 4. Product design

### 4.1 Principles

1. **Present tense.** Anything living in *will* (countdowns, goal ceremonies, deadline projections) or *have* (badges, streaks, trophies, portfolio-as-achievement) does not ship. This is a filter to run against every screen, not a sentiment ([D-024](../log/decision-log.md)).
2. **One next action.** The default screen shows one mission, never a backlog.
3. **The user decides; the product proposes.** Every suggestion is a default with a visible override.
4. **Consequence visibility, not discipline.** Show where the time went; impose nothing.
5. **Agency is real before it is legible.** Manufacturing a feeling of control the user lacks is a dark pattern ([D-021](../log/decision-log.md)).
6. **Recall over aspiration.** What already absorbed them, not what they want to become.
7. **Ship early, ship small.** Work nobody sees isn't progress.
8. **No first ship into a void.**
9. **Boredom is faced, not removed.** When scrolling stops it arrives undiluted. Say so.
10. **Never describe the user, only what they did.** Nothing may imply they are lazy, behind, or failing — that reinforces the verdict the product exists to overturn ([D-027](../log/decision-log.md)).
11. **AI is scaffolding, never the creator of record.**

### 4.2 Surfaces

**Now** — time-available selector, one mission, controls. **Project** — definition of done, stages, things made, scope adjustment. **Crew** — bounded chronological updates, guaranteed responses, reporting. **Evidence** — what was made, what shipped, what came back. **Profile** — schedule, privacy, notifications, export and deletion. Administrators get a separate **Cohort** area.

### 4.3 Key flows

**Welcome.** *Your evenings are going somewhere. This is how you get them back.*

**Recall**, before anything is chosen — three past-tense questions: when did you last lose track of time; what have you made or fixed, even badly; what do you read about when nobody set it. Free text, skippable, under 90 seconds. Never asks what the user wants to *become*; that question gets a performed answer.

**Project and finish line.** A small curated library — a researched explainer, a simple tool, a product concept, a local problem-and-solution report, a short visual or audio story, a tiny service experiment for a real person. The user writes their own definition of done and picks their own date. The system reflects the implication — *about four hours a week for six weeks* — and flags inconsistency with stated availability without blocking it.

**The loop.** *How much time do you have?* → one mission → done. The mission card carries a title, an instruction, a definition of done, a duration, and a difficulty. The user can accept, simplify, replace, or report a blocker.

**Ship.** The audience ladder, one rung at a time, each guaranteed to respond before the next unlocks: crew → people they know → one stranger who fits the thing → a small public. The user chooses the rung; the product never routes a first ship somewhere silence is likely.

**Time mirror.** Weekly, backward-looking: hours authored, things made, things shipped, responses received. No target, no projection, no red, no comparison to other users.

Its job is narrow and worth stating: **make *"I'm just lazy"* untenable against a record.** Not to inform, not to motivate — to dispute a verdict the user has already passed on themselves. That is why it counts what was made and stays silent about the rest, and why a low week must still read as a record rather than a shortfall. If it ever reads as judgment it has become the thing the product is fighting.

After two stalled weeks, one question with the user's own recall answers above it: *is this still the thing you want to be making?* Dropping it is a good outcome.

**Completion.** A page recording what the thing is, what it took, and what came back. A receipt that the hours were real — generated as a by-product, never presented as the reason for the work ([D-026](../log/decision-log.md)).

## 5. Detailed design

### 5.1 Domain model

The important structural decision is that **making, shipping, and being responded to are three separate things**. An earlier model recorded that work happened but not that it landed — which is the only thing this thesis cares about.

| Entity | Holds | Why it's separate |
|---|---|---|
| **Project** | Title, outcome, user-written definition of done, user-set target date, stage, visibility | Target date is revisable without penalty; the model must not treat a moved date as failure |
| **Mission** | Instruction, definition of done, duration, difficulty, stage, and a **kind** — *produce* or *distribute* | Making shipping a mission kind rather than a phase is what stops distribution being deferred forever |
| **Mission attempt** | Attempted, completed, blocker, optional predicted and actual discomfort | Attempts are preserved separately from missions so a skip is data rather than an absence |
| **Artifact** | The thing itself, and when it shipped | Distinct from evidence-of-work. Evidence proves effort; an artifact is what a stranger could actually receive |
| **Ship** | An artifact sent to one rung of the ladder, and the guaranteed responder for that rung | Modelling the rung explicitly is what makes "no first ship into a void" enforceable rather than aspirational |
| **Response** | An external reaction, its kind, and **whether it came from someone who knows the user** | A friend's kindness and a stranger's use are not the same evidence and must not be counted together |
| **Production session** | Minutes, and whether anything was produced | The unit the time mirror sums. Time is the product, so time is a first-class record |

Projects own missions and artifacts; artifacts own ships; ships own responses; users own sessions and belong to crews. Private reflections sit under stricter row-level policies than anything shippable, and are stored apart from anything that could reach a public page.

### 5.2 Mission generation

Generation takes the project stage, the definition of done, remaining milestones, available time, self-reported energy, experience, recent blockers, and what already exists.

A generated mission must start with one observable verb, produce or ship something real, fit the requested duration, carry a testable definition of done, cover one task rather than several, and never produce the user's work for them. Difficulty sits mostly at 2–4.

> Bad: *Think about your target customer.*
> Better: *Write three sentences on one customer, the moment the problem hits, and what they do instead.*

Output is validated against a strict schema; two consecutive failures fall back to a hand-written template mission. Every project stage has template coverage, so the product is fully usable with the model switched off entirely.

**Distribution missions are first-class.** Every template carries ship-shaped missions, and the generator must offer one as soon as anything is shippable.

**Adaptation changes one variable at a time** — duration, visibility, ambiguity, social exposure, or technical complexity. A high ship rate with no repeated blocker raises difficulty. Two consecutive skips reduce mission size or prompt a scope review. Something shipped to two rungs with no response drops a rung to one with a guaranteed responder. Reported overwhelm never increases difficulty.

### 5.3 Templates

Templates are authored by hand before any model involvement — the model adapts a tested path, it does not invent the pedagogy. Two selection criteria decide what enters the library: a first version must ship in days, and someone must plausibly want the result. A template that cannot answer *who would want this* does not go in.

### 5.4 Measurement

Four transparent quantities, never combined into a score: authored hours, things made, things shipped, responses received. No internal state is ever rated. The user is shown the evidence and draws their own conclusion — which is also the only version consistent with the agency principle, since the conclusion is theirs to reach.

### 5.5 Interface surface

The application needs capabilities for: managing a project and its scope, requesting and resolving missions, recording artifacts and shipping them to a rung, recording responses against a ship, retrieving the weekly mirror, crew membership and posting, and aggregate cohort metrics for administrators.

Authorisation is enforced server-side on every resource. Hidden UI controls are never the access-control mechanism. Mission submission is idempotent and recoverable after a network interruption, because the core loop runs on phones with bad connections.

### 5.6 Privacy and safety

Three data classes. **Private:** email, recall answers, discomfort ratings, reflections, moderation reports, billing. **Crew-visible:** display name, project title, deliberately shared artifacts. **Public:** only what the user explicitly selects, with AI assistance attributed. Administrators receive aggregate metrics and never reflections.

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
| A crew falls below three active members | The crew is flagged for manual repair; matching is not automated at this stage |

### 5.8 Testing

Unit coverage for mission schema validation, authored-hours arithmetic, ladder progression, permission rules, and stage transitions. Integration coverage for signup through first mission, a first ship with a guaranteed responder, private-versus-crew evidence separation, time-mirror generation, account deletion, and model-failure fallback. End-to-end coverage for signup to first ship in one session, a response recorded against an artifact, scope reduced without losing evidence, a minor account blocked from public publishing, and an administrator seeing aggregates without reflections.

**Model evaluation set:** at least 100 fixed project states covering vague and overambitious projects, low energy, short time windows, repeated avoidance, unshippable projects, unsafe requests, prompt injection, and interpersonal missions. Scored for specificity, feasibility, duration fit, shippability, safety, and preserved user agency. This is why the generation and scoring rules must be callable without a browser or database — see [repo-structure.md](../roadmap/repo-structure.md).

## 6. Alternatives considered

**A fixed 30-day programme.** Rejected. A prescribed container removes the independence of choice that resolving boredom depends on, and reproduces the thing that makes courses inert. Cost accepted: "in 30 days" was concrete marketing and a genuine deadline effect, and both are given up ([D-016](../log/decision-log.md)).

**A forward deadline projection at the weekly review** — *at this rate you finish in February.* Rejected after being drafted. It is a *will*-tense mechanic: future anxiety wearing the costume of information. Replaced by the backward-looking time mirror ([D-024](../log/decision-log.md)).

**The portfolio page as the product's promise.** Rejected. Things you *have* devalue — a portfolio page is worth little in five years, while hours authored do not devalue. The page survives as a receipt ([D-026](../log/decision-log.md)).

**Treating fear directly, with graded exposure.** Rejected. Fear is the last link in the chain, not the first, so exposure work treats a symptom. The discomfort-prediction machinery is retained but deliberately minor.

**Building crew matching now.** Deferred. Matching solves a liquidity problem that does not exist yet, and the inactive-replacement rule assumes a bench of spare users only available at scale. Hand-picking until manual assembly is the obvious bottleneck ([D-014](../log/decision-log.md)).

**Shipping crews with the core loop.** Rejected. Crews are the largest single source of scope, risk, and cold-start difficulty; shipping them together would make it impossible to tell which one failed ([D-013](../log/decision-log.md)).

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
| **0 — Concierge** | No product. Forms, a spreadsheet, hand-written missions, hand-picked crews, unpaid | That the loop works at all, and what the templates should be |
| **1 — Solo** | Auth, recall, onboarding, templates, mission loop, evidence, ship missions, time mirror | That people ship in week one without community machinery |
| **2 — Crews** | Chronological updates, the ladder's first rung, moderation | Whether a guaranteed audience changes ship rate |
| **3 — Institutional** | Cohort codes, aggregate dashboard, facilitator tools, data-processing terms | Distribution, and eventually willingness to pay |
| **4 — Personalisation** | Adaptive difficulty, blocker detection, template expansion | That completion improves without AI cost running away |

**Build order within phase 1:** hand-written templates and mission library first, then the data model, then recall through first mission, then the ship flow and first ladder rung, then the time mirror, then analytics. The templates come first because everything else degrades to them.

## 9. Open questions

1. How large must a first response be before it changes how someone sees themselves? A crew member being kind may be dismissible as politeness; a stranger's use is not.
2. Does reclaimed time sell, or does the finished thing sell? The demand doc leaves this deliberately unresolved.
3. Which project category ships fastest while still feeling like the user's own?
4. Do crews form at onboarding, or after a first ship?
5. How much facilitation does an acceptable ship rate require?
