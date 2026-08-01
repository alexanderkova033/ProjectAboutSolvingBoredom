# Product Requirements

**Product:** Freathe · **Status:** MVP specification · **Superseded by:** `prd.md` once the BMAD PM run produces it · **Snapshot:** 1 August 2026

> **Related:** [Demand](demand.md) · [Initial design](initial-design.md) · [BMAD path](../method/bmad-path.md) · [Decision log](../log/decision-log.md)

> `FR-`/`NFR-` identifiers are stable handles. PRD stories cite them rather than renumbering. Retired IDs are never reused.

## 1. Summary

> **Time is control. Generic apps took the control. This gives it back.**

The product turns an idle moment into one small act of making, and accumulates those acts into hours the user can see they authored. The promise is a week that left something behind; the proof is something real that exists outside their head.

Not a confidence app, therapy product, social network, course, or blocker.

## 2. Problem

The chain runs **boredom → consumption → not creating → no confidence → fear → "I'm just lazy"**, and the last link feeds the first. The argument is [demand](demand.md) §2; two things here depend on it. Boredom is upstream, so the intervention is *making* rather than fear-management. And the last link is a **verdict, not a cause** — what users report while fear is what happens, and the only link phrased as an identity, which is what makes the loop stable. The product disputes it with a record and never uses the word ([D-027](../log/decision-log.md)).

## 3. Principles

Eight, and they bind the design document too — this is the only list ([initial design](initial-design.md) §1 refers here rather than restating).

1. **Show, don't tell.** Describe only what they did, never what they are — no copy, empty state, or low-activity week may imply they are lazy, behind, or failing. Where the product could narrate a gap, it shows both sides and says nothing. Agency has to be real before it's legible: manufacturing a feeling of control the user doesn't have is a dark pattern.

2. **Nothing is asked that they can't answer.** Not what they want to improve — they don't know, and being asked is where people stall. Not how big, not by when, not how long they've got. Show real options and record which they take; the pick is the signal. Questions before work are friction; only questions *after* work are allowed, and only as reflection.

3. **Present tense.** Anything living in *will* — countdowns, deadlines, goal ceremonies — or *have* — badges, streaks, trophies, portfolio-as-achievement — does not ship. A filter to run against every screen, not a sentiment.

4. **One next action, and it must be good to do.** One mission on screen, never a backlog, and enjoyable *while it happens* rather than merely rewarding afterwards — creating can't beat consuming on ease, so the work itself has to be pleasant or the product loses every evening to a feed. Every cheap route is banned, which leaves the real ones ([D-045](../log/decision-log.md)).

5. **Ship early, and never into a void.** Work nobody sees isn't progress. Every rung has a guaranteed responder before the next unlocks.

6. **You are free to do whatever you want. You are not free of the consequences.** Discipline is force applied against wanting, and force runs out — so nothing is scheduled, owed, or required, any mission can be dropped, and stopping is a decision rather than a failure. What replaces it is a visible consequence, and only ever **the one they cannot already see**: the lost evening was felt in full by the person who lost it, so repeating it is scolding, while the seven days they came back is the only new fact available ([D-042](../log/decision-log.md)).

7. **Boredom is faced, not removed.** When the scrolling stops it arrives undiluted. Say so.

8. **AI is scaffolding, never the creator of record.** It decomposes, adapts, and critiques. It never makes the user's thing and never writes the user's words.

## 4. Goals and non-goals

Goals are things the product **does**, not states the user should reach.

**The product must:** get someone from opening it to making something in under ten minutes without an account · put one appropriately sized thing to do in front of them whenever they have a spare five minutes · get the first made thing in front of a real person within 72 hours · guarantee that thing receives a response · show, weekly, what was made and never what was missed · keep working with the language model switched off.

**Non-goals.** Diagnose or treat anything. Promise happiness, purpose, or income. Ask what the user wants to become. Set deadlines or scope. General social network or public feed. Job placement. Users under 16. App blocking. Generate the user's work. Creator monetisation, tokens, prizes. Streaks or any punitive mechanic.

## 5. Users

**A — Directionless graduate (21–26):** evenings that vanish, nothing that's hers. **B — Creator who never publishes (18–30):** ideas and drafts, nothing shipped. **C — Student with unstructured time (18–24):** boredom, no peers who make things. **D — Sixth-former (16–18):** nothing to point at that isn't coursework — second segment, currently **blocked** (§11).

**Secondary buyer:** schools, universities, workforce programmes, bootcamps, employers.

## 6. Core experience

The mechanics, as an index. Principles are §3; screens, copy and reasoning are [initial design](initial-design.md) §3.2, which is not restated here.

1. **The loop.** One mission is already there → do it → it's saved → the next is available immediately. Small by default; duration **observed, not declared**.
2. **Reset missions exist** — conditions for making, never wellbeing. Excluded from every production total, one per session, never a swap for a mission being avoided.
3. **Something ships within 72 hours** and repeatedly after. Getting it in front of a person is a mission kind, not an end-state.
4. **The audience ladder guarantees a response**: one responder → several → a small public. Ordered by count, not familiarity; the user picks who, and a stranger is the default ([D-043](../log/decision-log.md)).
5. **Session feeling, optional, one tap each side.** The only internal state recorded anywhere: private, never scored, never averaged. The user rates a session; the product never rates the user ([D-031](../log/decision-log.md)).
6. **They say what they did, then the record says what they did, and nothing comments** ([D-038](../log/decision-log.md)). In words, not numbers, never against an empty record.
7. **The record is plain facts, never a composed sentence** ([D-041](../log/decision-log.md)). No paste-ready line — phrasing is the user's, and it's the part that survives being asked about.
8. **The weekly view shows what was made**, never what was missed. Its job is to make *"I'm just lazy"* untenable against a record.

A project ends when the user stops, and stopping is not failure. The proof-of-work page is a **by-product** — the receipt that the hours were real, not the reason for the work.

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
| **FR-018** | After two stalled weeks, ask once whether this is still what they want to make. Stopping is valid, unpenalised, and recorded as a completed decision rather than an abandonment |
| **FR-019** | Weekly time mirror: hours that produced something, things made, things shipped, responses received. No projection, no target, no comparison |
| **FR-020** | Generate or select missions from stage, available time, energy, skill, and recent behaviour |
| **FR-021** | Every mission has title, instruction, definition of done, estimated duration, difficulty, and stage. The **first move is mechanical** — the opening step requires execution, not invention ([D-045](../log/decision-log.md)) |
| **FR-022** | Accept, replace, simplify, skip, or report a blocker |
| **FR-023** | Repeated replacement triggers a scope or blocker review |
| **FR-024** | Non-AI fallback missions exist for every stage |
| **FR-025** | Never generate dangerous, illegal, exploitative, or clinically framed missions |
| **FR-026** | Distribution missions exist for every project type — getting the thing in front of someone is a mission, not an afterthought |
| **FR-027** | Audience ladder: each rung has a guaranteed responder before the next is offered. Rungs are ordered by **number of recipients, never familiarity** — the user chooses the responder, and a fitting stranger is the default ([D-043](../log/decision-log.md)) |
| **FR-028** | Ask, in free text, what the user thinks they have got done — first at 72 hours, occasionally after. Never numeric, never before a work session, never fired when the record is empty |
| **FR-029** | Display the self-report beside the record without narrating the difference: no delta, no arrow, no percentage, no evaluative language, in **either** direction |
| **FR-030** | Submit text, URL, image, or file evidence |
| **FR-031** | Attempts preserve planned, attempted, completed, skipped |
| **FR-032** | Optionally record predicted and actual discomfort, stored separately. Minor by design — fear is downstream |
| **FR-033** | Transparent progress metrics |
| **FR-034** | No universal "confidence score" is displayed, and no internal state is ever scored |
| **FR-035** | Browse the evidence timeline |
| **FR-036** | Record external responses against the thing that caused them |
| **FR-037** | Optionally record how the user feels before and after a session, one tap each. Private, never scored, never averaged, never surfaced ([D-031](../log/decision-log.md)) |
| **FR-045** | Moderators can remove content and suspend accounts |
| **FR-046** | Cohort codes for institution-led pilots |
| **FR-047** | Support a **reset** mission kind — go outside, clear the table, stop for today. Framed as conditions for making, never wellbeing |
| **FR-048** | Reset missions are excluded from authored hours, things made, and things shipped. No production total may include one |
| **FR-049** | Reset missions are capped at one per session, never accumulate, and are never offered as a swap for a mission being avoided |
| **FR-050** | Schedule one daily production reminder |
| **FR-051** | Notifications reference a concrete next mission — never guilt, streak loss, or time-remaining |
| **FR-052** | Disable all non-essential notifications |
| **FR-060** | Generate a proof-of-work page as a by-product of completion |
| **FR-062** | Public, unlisted, or private visibility, user-controlled |
| **FR-063** | Public pages never expose discomfort or reflection data |
| **FR-064** | State what the user did as a loose list of plain facts drawn **only** from the record — days returned to, what the thing does, who saw it, what changed after. Ordinary words, no polish |
| **FR-065** | Never compose a sentence for an application, statement, or interview answer. No paste-ready output, no copy button, no application formatting ([D-041](../log/decision-log.md)) |
| **FR-066** | Never assert or imply the work's value, quality, or how a reader will receive it. No named outcomes, companies, or courses. Never inflate a small result |
| **FR-067** | Surface an external response that arrives after a project has ended. It is news, not a prompt: no call to action, no suggestion to start something else ([D-042](../log/decision-log.md)) |
| **FR-068** | Record whether the user starts a further mission unprompted within the same session. The proxy for whether the work was pleasant — aggregate only, never shown, never scored ([D-045](../log/decision-log.md)) |
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

Observable only: things made · things shipped · external responses received · hours that produced something · sessions per week · stage progression · continued production afterwards.

```text
authored hours   = time in production sessions
ship rate        = things shipped / things made
response rate    = things receiving an external response / things shipped
continuation     = sessions with a further unprompted mission / sessions
return           = users who start something else / users whose thing got a response
```

**Retired:** *consistency = active days / planned days.* There are no planned days ([D-042](../log/decision-log.md)), so the denominator never existed — a discipline metric that outlived the discipline.

`continuation` proxies whether the work was pleasant (`FR-068`); `return` tests the retention hypothesis directly, that the **response** brings people back rather than the product. Compare it against users whose thing received nothing.

Never measure how the user feels. The internal outcome is the product; the external numbers are the only honest evidence of it.

## 9. Success criteria

Pilot thresholds, not benchmarks.

- **Activation:** 60% ship something within 72 hours · median open→first mission under 10 minutes · 50% reach a first mission **before** registering.
- **Engagement:** 50% produce in three separate sessions in week one · 40% active in week three · **40% of sessions contain a further unprompted mission** — the only observable evidence the work is pleasant rather than merely virtuous.
- **Outcome:** 30% receive at least one unsolicited external response · 25% start something else within 14 days, **and at a higher rate among those who got a response** — if not, the retention hypothesis is wrong and nothing here gives anyone a reason to come back.
- **The gap** ([D-038](../log/decision-log.md)): direction and size of the difference between what users say they did and what the record shows. Predicted to skew toward under-reporting; if it doesn't, the central premise is wrong and worth knowing early. Aggregate only.
- **Weak by construction:** median session mood delta positive across a cohort. Badly confounded by selection, demand characteristics, and the mere fact of finishing. **Never quoted without that sentence attached.**
- **Commercial:** *deferred* ([D-018](../log/decision-log.md)). The first cohort is unpaid, so nothing here is evidence of willingness to pay.

## 10. Monetisation

All deferred until payments are possible. Hypotheses only: bounded outcome purchase (one project to completion, USD 29–79) · membership after a first completed project · per-seat institutional · facilitated premium. Bounded by outcome, never by calendar.

## 11. Safety and trust

Not therapy, and it says so. No shame, no status withdrawal, no punitive streaks. No encouragement of overwork, dangerous challenges, harassment, or exposure without consent. Reporting, blocking, moderation throughout. Minimal sensitive data. Discomfort ratings never shown to crews or administrators. AI output passes content and schema validation. The core loop is completable without ever sharing publicly. Acute distress stops productivity coaching and presents location-appropriate crisis guidance — it does not attempt counselling.

**Minors.** Persona D adds guardian consent, data minimisation, no mixed-age crews, no direct messaging, private-by-default publishing, and a named responsible adult (`FR-080`–`FR-086`). A UK deployment engages the ICO Age Appropriate Design Code and UK GDPR; a school pilot engages that school's safeguarding policy. **These are not self-certifiable.**

**Persona D is blocked, not scheduled** ([D-046](../log/decision-log.md)), for two structural reasons. The founder is under 18 and so **cannot be the named responsible adult `FR-085` requires** — the segment needs an adult before it needs a feature. And these are *product* obligations, while the concierge phase collects personal data on forms with no product to gate: minors in Phase 0 would engage UK GDPR and a school's safeguarding policy with none of `FR-080`–`FR-086` attached to anything. **Phase 0 recruits 18+ only.** The unlock is a named adult who will hold safeguarding, plus the DSL of any school involved.

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
| **NFR-012** | **Nothing interrupts an open mission.** No notification, badge, animation, or moving chrome while the user is working. Leaving is free — no confirmation, no cost to stopping ([D-042](../log/decision-log.md)) |

## 13. Release boundary

Phased per [initial design](initial-design.md) §7 ([D-013](../log/decision-log.md)).

**First — solo:** auth, onboarding, templates plus custom project, mission generation with fallback, evidence, ship missions, time mirror, proof-of-work by-product, analytics.
**Second — reach:** upper ladder rungs, moderation. Crews only if a cohort asks ([D-033](../log/decision-log.md)).
**Third — institutional:** cohort administration, aggregate dashboard, facilitator tools.

Native mobile, app blocking, live coworking, employer matching, recommenders, and public discovery are later.

## 14. Open questions

1. **Where does anyone encounter this?** No channel is validated and there is no search demand ([D-044](../log/decision-log.md)). First, because a product nobody encounters fails identically to one nobody wants.
2. **Does a response bring people back?** The only retention mechanism left once discipline mechanics are banned, and a hypothesis ([D-042](../log/decision-log.md)).
3. Which project category ships fastest and still feels like the user's own?
4. Is the primary payer the individual, school, university, or employer?
5. Does anyone actually want a crew, or is it a barrier dressed as a feature?
6. How much facilitation does an acceptable ship rate require?
7. How large must the first external response be to change how someone sees themselves?
8. Does reclaimed time sell, or does the finished thing sell?
9. First market: local, English-speaking global, or institution-specific?
