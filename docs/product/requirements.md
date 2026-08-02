# Product Requirements

**Product:** Freathe · **Status:** MVP specification · **Superseded by:** `prd.md` once the BMAD PM run produces it · **Snapshot:** 2 August 2026

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

6. **You are free to do whatever you want. You are not free of the consequences.** Stated the other way round: you don't endure a path in order to arrive at a success — you take the success, and the path is its consequence, which is exactly why the consequence has to be one you'd choose. Discipline is force applied against wanting, and force runs out — so nothing is scheduled, owed, or required, any mission can be dropped, and stopping is a decision rather than a failure. What replaces it is a visible consequence, and only ever **the one they cannot already see**: the lost evening was felt in full by the person who lost it, so repeating it is scolding, while the seven days they came back is the only new fact available ([D-042](../log/decision-log.md)).

7. **Boredom is faced, not removed.** When the scrolling stops it arrives undiluted. Say so.

8. **AI is scaffolding, never the creator of record.** It decomposes, adapts, and critiques. It never makes the user's thing and never writes the user's words.

## 4. Goals and non-goals

Goals are things the product **does**, not states the user should reach.

**The product must:** get someone from opening it to making something in under ten minutes without an account · be **already on the screen boredom arrives on**, holding one appropriately sized thing to do, without having been opened · get the first made thing in front of a real person within 72 hours · guarantee that thing receives a response · show, weekly, what was made and never what was missed · keep working with the language model switched off.

**Non-goals.** Diagnose or treat anything. Promise happiness, purpose, or income. Ask what the user wants to become. Set deadlines or scope. General social network or public feed. Job placement. Users under 16. App blocking. Generate the user's work. Creator monetisation, tokens, prizes. Streaks or any punitive mechanic.

## 5. Users

**A — Directionless graduate (21–26):** evenings that vanish, nothing that's hers. **B — Creator who never publishes (18–30):** ideas and drafts, nothing shipped. **C — Student with unstructured time (18–24):** boredom, no peers who make things. **D — Sixth-former (16–18):** nothing to point at that isn't coursework — second segment, currently **blocked** (§11).

**Who pays:** not the user ([D-060](../log/decision-log.md)) — funders, and secondarily schools, universities, workforce programmes, bootcamps, employers.

## 6. Core experience

The mechanics, as an index. Principles are §3; screens, copy and reasoning are [initial design](initial-design.md) §3.2, which is not restated here.

1. **The loop.** One mission is already there → do it → it's saved → the next is available immediately. Small by default; duration **observed, not declared**, and never shown ([D-048](../log/decision-log.md)).
2. **Two surfaces, one loop** ([D-051](../log/decision-log.md)). The mission sits on the phone's home screen because that is where boredom arrives; the work happens on a laptop because that is where things get made. The account is the seam between them and is asked for after the introduction, never before it.
3. **Reset missions exist** — conditions for making, never wellbeing. Excluded from every production total, one per session, never a swap for a mission being avoided.
4. **Something ships within 72 hours** and repeatedly after. Getting it in front of a person is a mission kind, not an end-state.
5. **The audience ladder guarantees a response**: one responder → several → a small public. Ordered by count, not familiarity; the user picks who, and a stranger is the default ([D-043](../log/decision-log.md)).
6. **Session feeling, optional, one tap each side.** The only internal state recorded anywhere: private, never scored, never averaged. The user rates a session; the product never rates the user ([D-031](../log/decision-log.md)).
7. **They say what they did, then the record says what they did, and nothing comments** ([D-038](../log/decision-log.md)). In words, not numbers, never against an empty record.
8. **The record is plain facts, never a composed sentence** ([D-041](../log/decision-log.md)). No paste-ready line — phrasing is the user's, and it's the part that survives being asked about.
9. **The weekly view shows what was made**, never what was missed. Its job is to make *"I'm just lazy"* untenable against a record.

A project ends when the user stops, and stopping is not failure. The proof-of-work page is a **by-product** — the receipt that the hours were real, not the reason for the work.

## 7. Functional requirements

| ID | Requirement |
|---|---|
| **FR-001** | Start and complete a first mission with **no account**. Work is held locally until there is something worth keeping |
| **FR-002** | Offer registration only **after the introduction** — the first finished mission — and only when it buys the user something: work that would otherwise be lost, or a second device to carry it to ([D-051](../log/decision-log.md)). Never a gate before the work |
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
| **FR-021** | Every mission has title, instruction, definition of done, estimated duration, difficulty, and stage. Duration is **recorded and never displayed** to the user, on any surface, including notifications ([D-048](../log/decision-log.md)) — the engine sizes the next mission from it, and telling someone a task takes twenty minutes hands them a reason to postpone it. The **first move is mechanical** — the opening step requires execution, not invention ([D-045](../log/decision-log.md)) |
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
| **FR-038** | Ask the user to **respond to their own work**, as a responder would — what they'd change, what they'd keep — and show that beside the thing itself. The gap between their judgement and the work is the point, and nothing narrates it, exactly as in `FR-029`. Also offered cold, on something made weeks earlier, and optionally before a ship as *what would you want someone to notice* ([D-055](../log/decision-log.md)) |
| **FR-039** | A self-response is **never** counted as an external response, never satisfies a rung's guarantee, and never enters `response rate`. When nothing came back, the product says nothing ([D-055](../log/decision-log.md)) |
| **FR-045** | Moderators can remove content and suspend accounts |
| **FR-046** | Cohort codes for institution-led pilots |
| **FR-047** | Support a **reset** mission kind — go outside, clear the table, stop for today. Framed as conditions for making, never wellbeing |
| **FR-048** | Reset missions are excluded from authored hours, things made, and things shipped. No production total may include one |
| **FR-049** | Reset missions are capped at one per session, never accumulate, and are never offered as a swap for a mission being avoided |
| **FR-051** | **Nothing is scheduled.** The only notification the product sends unbidden is an external response arriving (`FR-067`); it names what came back and carries no call to action. Never guilt, streak loss, time-remaining, or a mission ([D-049](../log/decision-log.md)) |
| **FR-052** | Disable all non-essential notifications |
| **FR-054** | A **home-screen surface the user installs themselves**, opening straight onto the current mission — title and definition of done — with **nothing cumulative**: no count, total, streak, elapsed time, or record of any kind ([D-049](../log/decision-log.md)). The record is deliberate and weekly (`FR-019`); anything seen fifty times a day without being chosen is where a count turns into a demand. **On web this is an icon, not a live card** ([D-059](../log/decision-log.md)) — the mission is one tap away rather than already visible, and that gap is the cost of reaching iPhone at all. What replaces *already visible* is *placed where it is seen* (`FR-057`, [D-061](../log/decision-log.md)) |
| **FR-057** | Ask **once**, at install, for the surface to be placed on the **first** home screen, and say why in plain words. Never repeated, never a condition of anything, and nothing is said if it isn't done ([D-061](../log/decision-log.md)). Placement is the only property this surface has left, and it is the user's to give |
| **FR-055** | The home-screen surface renders with **no network and no account**, from the local template library (`FR-024`). It is never empty and never shows an error |
| **FR-056** | **Starting is the primary gesture**; swapping is a smaller, secondary target. Rapid swapping on this surface counts toward `FR-023`'s blocker review like any other — the card must not make replacement the cheapest thing to do with it |
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

**Retired:** `FR-017` (deadline projection — a *will* mechanic, replaced by `FR-019`) · `FR-050` (daily production reminder — a scheduled re-entry prompt, which `FR-051`'s wording rules disguised rather than fixed, [D-049](../log/decision-log.md)) · `FR-053`, `FR-061`, `FR-073` (folded into neighbours).

**Deferred with crews** ([D-033](../log/decision-log.md)) — specified, not scheduled: `FR-040` join a crew · `FR-041` matching · `FR-042` leave, mute, report · `FR-043` chronological bounded posts · `FR-044` crew as guaranteed first audience.

## 8. Measurement

Observable only: things made · things shipped · external responses received · hours that produced something · sessions per week · stage progression · continued production afterwards.

```text
authored hours   = time in production sessions
ship rate        = things shipped / things made
response rate    = things receiving an external response / things shipped
continuation     = sessions with a further unprompted mission / sessions
return           = users who start something else / users who shipped something
```

**Retired:** *consistency = active days / planned days.* There are no planned days ([D-042](../log/decision-log.md)), so the denominator never existed — a discipline metric that outlived the discipline.

`continuation` proxies whether the work was pleasant (`FR-068`) and is the **primary** retention measure ([D-056](../log/decision-log.md)). `return` tests the second hypothesis, that a **response** brings people back rather than the product — so it is **computed twice**, once over users whose thing got a response and once over users whose thing got nothing. Either figure alone says nothing; the difference between them is the whole test, which is why the denominator is everyone who shipped rather than everyone who was answered. Self-responses are excluded from `response rate` by `FR-039` — a metric that can be satisfied by the user talking to themselves measures nothing.

Never measure how the user feels. The internal outcome is the product; the external numbers are the only honest evidence of it.

## 9. Success criteria

Pilot thresholds, not benchmarks.

- **Activation:** 60% ship something within 72 hours · median open→first mission under 10 minutes · 50% reach a first mission **before** registering.
- **Engagement:** **40% of sessions contain a further unprompted mission** — promoted to the *leading* indicator ([D-056](../log/decision-log.md)), because enjoyment is now the primary retention hypothesis and this is its only observable form. Then: 50% produce in three separate sessions in week one · 40% active in week three.
- **Outcome:** 30% receive at least one unsolicited external response · 25% start something else within 14 days. Read return against **both** hypotheses — continuation rate and whether a response arrived. If neither predicts it, nothing here gives anyone a reason to come back.
- **The gap** ([D-038](../log/decision-log.md)): direction and size of the difference between what users say they did and what the record shows. Predicted to skew toward under-reporting; if it doesn't, the central premise is wrong and worth knowing early. Aggregate only.
- **Weak by construction:** median session mood delta positive across a cohort. Badly confounded by selection, demand characteristics, and the mere fact of finishing. **Never quoted without that sentence attached.**
- **Commercial:** *deferred, and reframed* ([D-018](../log/decision-log.md), [D-060](../log/decision-log.md)). The first cohort is unpaid, so nothing here is evidence of willingness to pay — and the user was never going to be the one paying. What replaces the question is whether a funder or an institution finds the record legible, which is a different test, on different people, and not one this cohort can run.

## 10. Funding

**Not-for-profit, and the user is not the payer** ([D-060](../log/decision-log.md)). The legal form is open and deliberately unresearched until the interviews are in. Everything below is parked in [future plans](../roadmap/future-plans.md), with one seam held open ([D-050](../log/decision-log.md), [D-053](../log/decision-log.md)).

No price is stated here, and the previous range was furniture — a number invented to fill a heading. Two things still block any money arriving, and [D-060](../log/decision-log.md) removes neither: nobody here can hold an account that receives it ([D-018](../log/decision-log.md), [D-058](../log/decision-log.md)) — trustees are adults too, so the date is **2029** either way — and **there is no unit**, because *one project to completion* was written nine decisions after [D-028](../log/decision-log.md) deleted completion and accepted *no completion metric* as its cost. A grant application asks what a pound buys in the same words a customer would, so the second problem survived the change of form intact. The first expires with a birthday; the second is a design question (§14).

**What is kept ready is a seam, not a feature** ([D-053](../log/decision-log.md)). Every capability check goes through one gate that today answers *yes* to everything. Payments later then mean changing one implementation rather than finding every place a check should have been — which is the part that is actually expensive to retrofit. Nothing else is built in anticipation.

**One product constraint travels with any future answer:** a subscription is a recurring obligation, and this product's central claim is that nothing is owed ([D-042](../log/decision-log.md)). Whatever is eventually funded has to survive that — bounded things sit inside the principles and rent does not, and a funded place should be bounded for the same reason a purchase would have been.

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
| **NFR-004** | Two surfaces, **one codebase** ([D-051](../log/decision-log.md), [D-059](../log/decision-log.md)). Responsive web from **360 px** upward: installable to a phone home screen, offline-capable for the mission loop, and sized for the laptop where the work actually happens. No native client on either platform |
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

**First — solo:** auth, onboarding, templates plus custom project, mission generation with fallback, evidence, ship missions, time mirror, proof-of-work by-product, analytics — plus the **installed home-screen surface** ([D-059](../log/decision-log.md)), which ships here rather than later because it is the surface the trigger lives on, and shipping the laptop half alone tests a product nobody is reminded to open.
**Second — reach:** upper ladder rungs, moderation. Crews only if a cohort asks ([D-033](../log/decision-log.md)).
**Third — institutional:** cohort administration, aggregate dashboard, facilitator tools.

App blocking, live coworking, employer matching, recommenders, public discovery, and any iOS surface are later.

## 14. Open questions

1. **Where does anyone encounter this?** No channel is validated and there is no search demand ([D-044](../log/decision-log.md)). First, because a product nobody encounters fails identically to one nobody wants.
2. **Does a response bring people back?** The only retention mechanism left once discipline mechanics are banned, and a hypothesis ([D-042](../log/decision-log.md)).
3. Which project category ships fastest and still feels like the user's own?
4. Which funder or institution pays — grant funder, school, university, workforce programme, employer — and **what is the fundable unit**, given that completion no longer exists to be sold ([D-050](../log/decision-log.md))? The individual is no longer a candidate ([D-060](../log/decision-log.md)).
5. Does anyone actually want a crew, or is it a barrier dressed as a feature?
6. How much facilitation does an acceptable ship rate require?
7. How large must the first external response be to change how someone sees themselves?
8. Does reclaimed time sell, or does the finished thing sell?
9. First market: local, English-speaking global, or institution-specific?
