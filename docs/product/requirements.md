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

1. **Present tense.** If a feature lives in *will* (countdowns, goal ceremonies, aspiration) or *have* (badges, streaks, trophies), it doesn't ship. The product operates in *now* ([D-024](../log/decision-log.md)).
2. **The user decides; the product proposes.** They pick the project, scope, and finish line. Every suggestion is a default with a visible override.
3. **Consequence visibility, not discipline.** No streaks, no obligation, no guilt. Show where the time went and let them choose ([D-017](../log/decision-log.md)).
4. **Agency is real before it is legible.** Manufacturing a feeling of control the user doesn't have is a dark pattern, and every screen is audited against the manipulation taxonomy ([D-021](../log/decision-log.md)).
5. **Recall over aspiration.** Ask what someone already lost track of time doing, not what they want to become.
6. **Boredom is faced, not removed.** When the scrolling stops it arrives undiluted. Say so.
7. **Never describe the user, only what they did.** No copy, mission, notification, or empty state may imply the user is lazy, behind, or failing — that reinforces the verdict the product exists to overturn ([D-027](../log/decision-log.md)).
8. **AI is scaffolding, never the creator of record.**

## 4. Goals and non-goals

**Goals.** Ship something within 72 hours of signing up. Make the week's authored hours visible. Produce one real external response. Reduce the gap between an idle moment and a made thing. Measure behaviour, never feelings.

**Non-goals.** Diagnose or treat anything. Promise happiness, purpose, or income. General social network or public feed. Job placement. Users under 16. App blocking. Generate the user's work. Creator monetisation, tokens, prizes. Streaks or any punitive mechanic.

## 5. Users

**A — Directionless graduate (21–26):** evenings that vanish, nothing that's hers. **B — Creator who never publishes (18–30):** ideas and drafts, nothing shipped. **C — Student with unstructured time (18–24):** boredom, no peers who make things. **D — Sixth-former (16–18), second segment:** nothing to point at that isn't coursework.

**Secondary buyer:** schools, universities, workforce programmes, bootcamps, employers.

## 6. Core experience

Six things must be true. Screens and copy are in [initial design](initial-design.md) §4.

1. **Recall precedes choosing.** Three past-tense questions — what absorbed you, what you've made, what you read unprompted — before any project is selected. Under 90 seconds, skippable.
2. **The user sets scope and finish line.** The system reflects the implication and flags inconsistency without blocking. A suggested date is a default, never a container.
3. **The loop is one mission at a time.** *I have 5 / 15 / 30 / 60 minutes* → one mission with a testable definition of done → done.
4. **Shipping happens in week one, repeatedly.** Getting something in front of a real person is a mission kind, not an end-state.
5. **The audience ladder guarantees a response** ([D-025](../log/decision-log.md)): crew → people they know → one fitting stranger → a small public. No first ship goes into a void.
6. **The weekly view looks backward.** Authored hours, things made, things shipped, responses received. No projection, no deadline, no comparison. It counts what was made and stays silent about the rest. Its job is to make *"I'm just lazy"* untenable against a record ([D-027](../log/decision-log.md)) — not to inform, and not to motivate.

Completion means the user's own definition of done is met and the thing exists. The proof-of-work page is a **by-product** ([D-026](../log/decision-log.md)) — the receipt that the hours were real, not the reason for the work.

## 7. Functional requirements

| ID | Requirement |
|---|---|
| **FR-001** | Register with email or supported OAuth |
| **FR-002** | Confirm age eligibility and accept terms |
| **FR-003** | Set timezone, availability, interests, privacy preferences |
| **FR-004** | Export or delete account data |
| **FR-010** | Select from project templates |
| **FR-011** | Create a custom project with title, outcome, artifact type, **user-set target date**, and definition of done |
| **FR-012** | Help the user set scope and finish line, and flag scope/availability inconsistency. Never impose a programme length |
| **FR-013** | Reduce scope without losing evidence |
| **FR-014** | Stages: define, explore, build, **ship**, respond, revise, reflect |
| **FR-015** | One active project at a time |
| **FR-016** | Capture recall answers at onboarding; use as suggestion input and re-surface when momentum dips |
| **FR-018** | After two stalled weeks, show the user their recall answers and ask whether this is still what they want to make. Abandoning is valid and unpenalised |
| **FR-019** | Weekly time mirror: hours that produced something, things made, things shipped, responses received. No projection, no target, no comparison |
| **FR-020** | Generate or select missions from stage, available time, energy, skill, and recent behaviour |
| **FR-021** | Every mission has title, instruction, definition of done, estimated duration, difficulty, and stage |
| **FR-022** | Accept, replace, simplify, skip, or report a blocker |
| **FR-023** | Repeated replacement triggers a scope or blocker review |
| **FR-024** | Non-AI fallback missions exist for every stage |
| **FR-025** | Never generate dangerous, illegal, exploitative, or clinically framed missions |
| **FR-026** | Distribution missions exist for every project type — getting the thing in front of someone is a mission, not an afterthought |
| **FR-027** | Audience ladder: each rung has a guaranteed responder before the next is offered. Never route a first ship to an unguaranteed audience |
| **FR-030** | Submit text, URL, image, or file evidence |
| **FR-031** | Attempts preserve planned, attempted, completed, skipped |
| **FR-032** | Optionally record predicted and actual discomfort, stored separately. Minor by design — fear is downstream |
| **FR-033** | Transparent progress metrics |
| **FR-034** | No universal "confidence score" is displayed, and no internal state is ever scored |
| **FR-035** | Browse the evidence timeline |
| **FR-036** | Record external responses against the thing that caused them |
| **FR-040** | Join a crew by invitation or matching |
| **FR-042** | Leave, mute, or report a crew |
| **FR-043** | Crew posts are chronological and bounded |
| **FR-044** | Crew members act as guaranteed first audience: a shipped thing surfaced to a crew must receive a response |
| **FR-045** | Moderators can remove content and suspend accounts |
| **FR-046** | Crew codes for institution-led pilots |
| **FR-050** | Schedule one daily production reminder |
| **FR-051** | Notifications reference a concrete next mission — never guilt, streak loss, or time-remaining |
| **FR-052** | Disable all non-essential notifications |
| **FR-060** | Generate a proof-of-work page as a by-product of completion |
| **FR-062** | Public, unlisted, or private visibility, user-controlled |
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

**Retired:** `FR-017` (deadline projection — a *will* mechanic, replaced by `FR-019`) · `FR-041` (matching criteria — deferred, [D-014](../log/decision-log.md)) · `FR-053`, `FR-061`, `FR-073` (folded into neighbours).

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

- **Activation:** 60% ship something within 72 hours · median signup→first mission under 10 minutes.
- **Engagement:** 50% produce in three separate sessions in week one · 40% active in week three.
- **Outcome:** 40% report the week felt different · 30% reach their own definition of done · 30% receive at least one unsolicited external response · 25% start something else within 14 days.
- **Commercial:** *deferred* ([D-018](../log/decision-log.md)). The first cohort is unpaid, so nothing here is evidence of willingness to pay.

## 10. Monetisation

All deferred until payments are possible. Hypotheses only: bounded outcome purchase (one project to completion, USD 29–79) · membership after a first completed project · per-seat institutional · facilitated premium. Bounded by outcome, never by calendar.

## 11. Safety and trust

Not therapy, and it says so. No shame, no status withdrawal, no punitive streaks. No encouragement of overwork, dangerous challenges, harassment, or exposure without consent. Reporting, blocking, moderation throughout. Minimal sensitive data. Discomfort ratings never shown to crews or administrators. AI output passes content and schema validation. The core loop is completable without ever sharing publicly. Acute distress stops productivity coaching and presents location-appropriate crisis guidance — it does not attempt counselling.

**Minors.** Persona D adds guardian consent, data minimisation, no mixed-age crews, no direct messaging, private-by-default publishing, and a named responsible adult (`FR-080`–`FR-086`). A UK deployment engages the ICO Age Appropriate Design Code and UK GDPR; a school pilot engages that school's safeguarding policy. **These are not self-certifiable** — confirm with the school's designated safeguarding lead before any minor uses this. This document identifies the obligations; it does not discharge them.

## 12. Non-functional requirements

| ID | Requirement |
|---|---|
| **NFR-001** | Core pages usable within three seconds on typical mobile connections |
| **NFR-002** | Mission submission idempotent and recoverable after interruption |
| **NFR-003** | WCAG 2.2 AA for core flows |
| **NFR-004** | All flows work at 360 px |
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
**Second — crews:** chronological updates, the audience ladder's first rung, moderation.  
**Third — institutional:** cohort administration, aggregate dashboard, facilitator tools.

Native mobile, app blocking, live coworking, employer matching, recommenders, and public discovery are later.

## 14. Open questions

1. Which project category ships fastest and still feels like the user's own?
2. Is the primary payer the individual, school, university, or employer?
3. Do crews form at onboarding or after a first ship?
4. How much facilitation does an acceptable ship rate require?
5. How large must the first external response be to change how someone sees themselves? A crew member being kind may not count.
6. Does reclaimed time sell, or does the finished thing sell? (§6 of the demand doc leaves this open on purpose.)
7. First market: local, English-speaking global, or institution-specific?
