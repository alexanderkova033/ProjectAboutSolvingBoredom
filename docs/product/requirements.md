# Product Requirements

**Product:** ForgePath *(placeholder name — to be replaced)*  
**Status:** MVP specification · **Superseded by:** `prd.md` once the BMAD PM run produces it  
**Research snapshot:** 1 August 2026

> **Related:** [Demand](demand.md) · [Initial design](initial-design.md) · [BMAD path](../method/bmad-path.md) · [Decision log](../log/decision-log.md)

> `FR-`/`NFR-` identifiers are stable handles. PRD stories cite them rather than renumbering. Retired IDs are never reused.

## 1. Summary

> **Time is control. Generic apps took the control. This gives it back.**

The product turns an idle moment into one small act of making, and accumulates those acts into hours the user can see they authored. The promise is a week that left something behind. The proof is something real that exists outside their head.

Not a confidence app, therapy product, social network, course, or blocker.

## 2. Problem

Boredom is time you can feel passing. The chain runs **boredom → consumption → not creating → no confidence → fear → "I'm just lazy"** — and the last link feeds back into the first.

Boredom is upstream, so the intervention point is *making*, not fear-management ([D-023](../log/decision-log.md)) — confidence is a by-product of having made things, and the fear machinery here is deliberately minor for that reason.

**Laziness is the last link and it is a verdict, not a cause** ([D-027](../log/decision-log.md)). It is what users will report — nobody says "I'm afraid to make a website", they say "I couldn't be bothered" — and it is the only link phrased as an identity rather than a state. Fear says *this might go badly*; laziness says *I am someone who doesn't do things*, which explains away every future instance and makes the loop stable rather than a bad week. The product disputes that verdict with a record, and never uses the word.

Existing tools each take one piece: blockers remove the app and return nothing; task managers assume you know what to do; courses hand you someone else's plan; AI assistants produce output without the user acting or learning.

## 3. Principles

1. **Show, don't tell.** Show the user what they can do. Never tell them what to feel, what to achieve, or what they already know about themselves ([D-029](../log/decision-log.md)).
2. **The session must be good to be in.** Not rewarding afterwards — enjoyable *while it happens*. Creating can't beat consuming on ease, so the work itself has to be pleasant, or the product loses every evening to a feed. Every cheap route to this is banned (streaks, points, badges, confetti), which leaves the real ones: a task worth doing, visible change under your hands, speed, and an interface that stays quiet ([D-035](../log/decision-log.md)).
3. **Never ask what they want to improve.** They don't know — that's the condition, not a gap to fill in ([D-036](../log/decision-log.md)).
4. **Present tense.** If a feature lives in *will* (countdowns, deadlines, goal ceremonies) or *have* (badges, streaks, trophies), it doesn't ship ([D-024](../log/decision-log.md)).
5. **No scope, no finish line.** The product never asks how big the thing is or when it will be done. When someone is doing what they want, those questions don't help and the pressure they add is the thing that stops people ([D-028](../log/decision-log.md)). *Done* is defined per mission, never per project.
6. **The user decides; the product proposes.** Every suggestion is a default with a visible override.
7. **Choice reveals preference.** Don't ask what someone loves — they already know, and the question is a cliché that changes nothing. Put real options in front of them and watch which one they pick ([D-030](../log/decision-log.md)).
8. **Consequence visibility, not discipline.** No streaks, no obligation, no guilt ([D-017](../log/decision-log.md)).
9. **Agency is real before it is legible.** Manufacturing a feeling of control the user doesn't have is a dark pattern; every screen is audited against the manipulation taxonomy ([D-021](../log/decision-log.md)).
10. **Boredom is faced, not removed.** When the scrolling stops it arrives undiluted. Say so.
11. **Never describe the user, only what they did.** No copy, mission, notification, or empty state may imply they are lazy, behind, or failing ([D-027](../log/decision-log.md)).
12. **AI is scaffolding, never the creator of record.**

## 4. Goals and non-goals

Goals are stated as things the product **does**, not states the user should reach. Nothing here is a feeling to be produced.

**The product must:**

1. Get someone from opening it to making something in under ten minutes, without an account.
2. Put one appropriately sized thing to do in front of them whenever they have a spare five minutes.
3. Get the first made thing in front of a real person within 72 hours.
4. Guarantee that first thing receives a response.
5. Show, weekly, what was made — never what was missed.
6. Keep working with the language model switched off.

**Non-goals.** Diagnose or treat anything. Promise happiness, purpose, or income. Ask what the user wants to become. Set deadlines or scope. General social network or public feed. Job placement. Users under 16. App blocking. Generate the user's work. Creator monetisation, tokens, prizes. Streaks or any punitive mechanic.

## 5. Users

**A — Directionless graduate (21–26):** evenings that vanish, nothing that's hers. **B — Creator who never publishes (18–30):** ideas and drafts, nothing shipped. **C — Student with unstructured time (18–24):** boredom, no peers who make things. **D — Sixth-former (16–18), second segment:** nothing to point at that isn't coursework.

**Secondary buyer:** schools, universities, workforce programmes, bootcamps, employers.

## 6. Core experience

Nine things must be true. Screens and copy are in [initial design](initial-design.md) §4.

1. **Nothing is required to start.** No account, no questionnaire, no goal-setting, and no question about what they want to improve — they don't know, and being asked is where people stall ([D-032](../log/decision-log.md), [D-036](../log/decision-log.md)). The first thing anyone sees is something to do.
2. **Options, not questions.** The user is shown real things they could make and picks one. No interview about their interests — the pick is the signal, and the direction emerges from what they keep choosing ([D-030](../log/decision-log.md)).
3. **No scope, no date, and no time budget are ever requested** ([D-028](../log/decision-log.md), [D-034](../log/decision-log.md)).
4. **The loop is one small thing at a time.** Open it → one mission is already there → do it → it's saved. Every mission is small by default, with the next available immediately if they want to keep going. Duration is **observed, not declared** — nobody is asked how long they have.
5. **Shipping happens in week one, repeatedly.** Getting something in front of a real person is a mission kind, not an end-state.
6. **The audience ladder guarantees a response** ([D-025](../log/decision-log.md)): one person the user already knows → one stranger who fits the thing → a small public. During hand-run cohorts the operator is the guaranteed responder. No first ship goes into a void.
7. **They say what they did; then the record says what they did; nothing comments** ([D-038](../log/decision-log.md)). First at the 72-hour mark, occasionally after. Asked in words rather than numbers, never fired against an empty record, and never asked *before* work — questions before work are friction, questions after work are reflection.
8. **The record is translated into words, never into a valuation** ([D-039](../log/decision-log.md)). A sentence the user could put in a personal statement or an interview answer, built only from recorded facts, audience-selectable, editable, and never inflated. The product never says the work is good or predicts how a reader will take it.
9. **The weekly view shows what was made.** Authored hours, things made, things shipped, responses received. No projection, no deadline, no comparison, and never a word about time lost — the user already knows where that went. Its job is to make *"I'm just lazy"* untenable against a record ([D-027](../log/decision-log.md)).

**Session feeling, optionally, before and after** ([D-031](../log/decision-log.md)). One tap each side. This is the only internal state the product records, it belongs to the user rather than to us, and it is never scored, never averaged into anything, and never shown to anyone else. It exists because the delta is the only direct measure of the actual promise — that the time felt different afterwards.

A project ends when the user stops, and stopping is not failure. The proof-of-work page is a **by-product** ([D-026](../log/decision-log.md)) — the receipt that the hours were real, not the reason for the work.

## 7. Functional requirements

| ID | Requirement |
|---|---|
| **FR-001** | Start and complete a first mission with **no account**. Work is held locally until there is something worth keeping |
| **FR-002** | Offer registration only when work would otherwise be lost, never as a gate before it |
| **FR-003** | Confirm age eligibility and accept terms at registration |
| **FR-004** | Set timezone, availability, privacy preferences. Never asked at onboarding |
| **FR-005** | Export or delete account data |
| **FR-010** | Present real, concrete things the user could make and let them pick. Never interview them about their interests |
| **FR-011** | Create a custom project with a title and an artifact type. **No target date, no declared scope** |
| **FR-012** | Never request, infer, display, or act on a project deadline or size estimate |
| **FR-013** | Reduce or change what is being made without losing evidence of what came before |
| **FR-014** | Stages: define, explore, build, **ship**, respond, revise |
| **FR-015** | One active project at a time |
| **FR-016** | Record which options the user chose and passed over, and use that as suggestion input |
| **FR-018** | After two stalled weeks, ask once whether this is still what they want to make. Stopping is valid and unpenalised, and is recorded as a completed decision rather than an abandonment |
| **FR-019** | Weekly time mirror: hours that produced something, things made, things shipped, responses received. No projection, no target, no comparison |
| **FR-028** | Ask, in free text, what the user thinks they have got done — first at 72 hours, occasionally after. Never numeric, never before a work session, never fired when the record is empty |
| **FR-029** | Display the self-report beside the record without narrating the difference: no delta, no arrow, no percentage, no evaluative language, in **either** direction ([D-038](../log/decision-log.md)) |
| **FR-020** | Generate or select missions from stage, available time, energy, skill, and recent behaviour |
| **FR-021** | Every mission has title, instruction, definition of done, estimated duration, difficulty, and stage |
| **FR-022** | Accept, replace, simplify, skip, or report a blocker |
| **FR-023** | Repeated replacement triggers a scope or blocker review |
| **FR-024** | Non-AI fallback missions exist for every stage |
| **FR-025** | Never generate dangerous, illegal, exploitative, or clinically framed missions |
| **FR-026** | Distribution missions exist for every project type — getting the thing in front of someone is a mission, not an afterthought |
| **FR-047** | Support a **reset** mission kind — go outside, clear the table, stop for today. Framed as conditions for making, never as wellbeing ([D-040](../log/decision-log.md)) |
| **FR-048** | Reset missions are excluded from authored hours, things made, and things shipped. No production total may include one |
| **FR-049** | Reset missions are capped at one per session, never accumulate, and are never offered as a swap for a mission the user is currently avoiding |
| **FR-027** | Audience ladder: each rung has a guaranteed responder before the next is offered. Never route a first ship to an unguaranteed audience |
| **FR-030** | Submit text, URL, image, or file evidence |
| **FR-031** | Attempts preserve planned, attempted, completed, skipped |
| **FR-032** | Optionally record predicted and actual discomfort, stored separately. Minor by design — fear is downstream |
| **FR-033** | Transparent progress metrics |
| **FR-034** | No universal "confidence score" is displayed, and no internal state is ever scored |
| **FR-035** | Browse the evidence timeline |
| **FR-036** | Record external responses against the thing that caused them |
| **FR-037** | Optionally record how the user feels before and after a session, one tap each. Private to that user, never scored, never averaged, never surfaced to anyone else ([D-031](../log/decision-log.md)) |
| **FR-045** | Moderators can remove content and suspend accounts |
| **FR-046** | Cohort codes for institution-led pilots |
| **FR-050** | Schedule one daily production reminder |
| **FR-051** | Notifications reference a concrete next mission — never guilt, streak loss, or time-remaining |
| **FR-052** | Disable all non-essential notifications |
| **FR-060** | Generate a proof-of-work page as a by-product of completion |
| **FR-062** | Public, unlisted, or private visibility, user-controlled |
| **FR-064** | Generate a usable sentence describing what the user made, assembled **only** from facts in the record, with the audience selectable (personal statement, interview answer, application form). Editable by the user; offered as a draft, never issued as a certificate |
| **FR-065** | Never assert or imply the work's value, quality, or how a reader will receive it. No named outcomes, companies, or courses. Never inflate a small result into a larger-sounding one ([D-039](../log/decision-log.md)) |
| **FR-063** | Public pages never expose discomfort or reflection data |
| **FR-070** | Administrators create a cohort and invite users |
| **FR-071** | Administrators view aggregate participation and completion |
| **FR-072** | Administrators cannot read private reflections |
| **FR-080** | Age captured at registration; under 16 refused |
| **FR-081** | Under-18 accounts require verifiable guardian consent |
| **FR-082** | Crews never mix under-18 and adult members |
| **FR-083** | Under-18 accounts default to private; public publishing needs separate consent |
| **FR-084** | Under-18 data minimised; no reflection data used beyond showing it back |
| **FR-085** | Minor cohorts have a named responsible adult and an escalation path |
| **FR-086** | No direct messaging for under-18 accounts |

**Retired:** `FR-017` (deadline projection — a *will* mechanic, replaced by `FR-019`) · `FR-053`, `FR-061`, `FR-073` (folded into neighbours).

**Deferred with crews** ([D-033](../log/decision-log.md)) — specified, not scheduled: `FR-040` join a crew · `FR-041` matching · `FR-042` leave, mute, report · `FR-043` chronological bounded posts · `FR-044` crew as guaranteed first audience.

## 8. Measurement

Observable only: things made · things shipped · external responses received · hours that produced something · sessions per week · stage progression · project completion · continued production afterwards.

```text
authored hours   = time in production sessions
ship rate        = things shipped / things made
response rate    = things receiving an external response / things shipped
consistency      = active production days / planned production days
```

Never measure how the user feels. The internal outcome is the product; the external numbers are the only honest evidence of it.

## 9. Success criteria

Pilot thresholds, not benchmarks.

- **Activation:** 60% ship something within 72 hours · median open→first mission under 10 minutes · 50% reach a first mission **before** registering.
- **Engagement:** 50% produce in three separate sessions in week one · 40% active in week three.
- **Outcome:** 30% receive at least one unsolicited external response · 25% start something else within 14 days · **median session mood delta positive across a cohort** ([D-031](../log/decision-log.md)) — the one direct measure of the promise, reported in aggregate and never per user.
- **The gap** ([D-038](../log/decision-log.md)): the direction and size of the difference between what users say they did and what the record shows. Predicted to skew toward under-reporting, since the laziness verdict is harsher than reality — and if it doesn't, the product's central premise is wrong and worth knowing early. Aggregate only; never shown to a user as a number.
- **Commercial:** *deferred* ([D-018](../log/decision-log.md)). The first cohort is unpaid, so nothing here is evidence of willingness to pay.

## 10. Monetisation

All deferred until payments are possible. Hypotheses only: bounded outcome purchase (one project to completion, USD 29–79) · membership after a first completed project · per-seat institutional · facilitated premium. Bounded by outcome, never by calendar.

## 11. Safety and trust

Not therapy, and it says so. No shame, no status withdrawal, no punitive streaks. No encouragement of overwork, dangerous challenges, harassment, or exposure without consent. Reporting, blocking, moderation throughout. Minimal sensitive data. Discomfort ratings never shown to crews or administrators. AI output passes content and schema validation. The core loop is completable without ever sharing publicly. Acute distress stops productivity coaching and presents location-appropriate crisis guidance — it does not attempt counselling.

**Minors.** Persona D adds guardian consent, data minimisation, no mixed-age crews, no direct messaging, private-by-default publishing, and a named responsible adult (`FR-080`–`FR-086`). A UK deployment engages the ICO Age Appropriate Design Code and UK GDPR; a school pilot engages that school's safeguarding policy. **These are not self-certifiable** — confirm with the school's designated safeguarding lead before any minor uses this. This document identifies the obligations; it does not discharge them.

## 12. Non-functional requirements

| ID | Requirement |
|---|---|
| **NFR-001** | Core pages usable within three seconds on a typical domestic connection |
| **NFR-002** | Mission submission idempotent and recoverable after interruption |
| **NFR-003** | WCAG 2.2 AA for core flows |
| **NFR-004** | *Pending the platform decision* ([D-037](../log/decision-log.md)). The 360 px floor is withdrawn — it assumed mobile-first, which no longer follows |
| **NFR-005** | Encryption in transit and at rest |
| **NFR-006** | Private reflections stored separately from anything publishable |
| **NFR-007** | Structured logging with no reflection text in analytics |
| **NFR-008** | Export project and evidence data as JSON or CSV |
| **NFR-009** | Core flows usable when the language-model provider is down |
| **NFR-010** | Templates cached; per-user generation limits |
| **NFR-011** | **Cheap in time.** A product promising reclaimed hours cannot demand large ones. Core loop completable in 5 minutes; nothing requires more than 60 |

## 13. Release boundary

Phased per [initial design](initial-design.md) §8 ([D-013](../log/decision-log.md)).

**First — solo:** auth, recall, onboarding, templates plus custom project, mission generation with fallback, evidence, ship missions, time mirror, proof-of-work by-product, analytics.  
**Second — reach:** upper ladder rungs, moderation. Crews only if a cohort asks for them ([D-033](../log/decision-log.md)).  
**Third — institutional:** cohort administration, aggregate dashboard, facilitator tools.

Native mobile, app blocking, live coworking, employer matching, recommenders, and public discovery are later.

## 14. Open questions

1. Which project category ships fastest and still feels like the user's own?
2. Is the primary payer the individual, school, university, or employer?
3. Does anyone actually want a crew, or is it a barrier dressed as a feature?
4. How much facilitation does an acceptable ship rate require?
5. How large must the first external response be to change how someone sees themselves? Someone the user knows being kind may be dismissible as politeness; a stranger's use is not.
6. Does reclaimed time sell, or does the finished thing sell? (§6 of the demand doc leaves this open on purpose.)
7. First market: local, English-speaking global, or institution-specific?
