# Product Requirements

**Product:** ForgePath *(placeholder name — to be replaced)*  
**Document status:** MVP specification  
**BMAD stage:** Pre-BMAD input, feeds the PM PRD  
**Superseded by:** `docs/product/prd.md` once the BMAD PM run produces it  
**Research snapshot:** 31 July 2026

> **Related:** [Demand](demand.md) · [Initial design](initial-design.md) · [BMAD path](../method/bmad-path.md) · [Future plans](../roadmap/future-plans.md) · [Decision log](../log/decision-log.md)

> `FR-`/`NFR-` identifiers are the stable handles for this project. PRD epics and stories should trace back to them rather than renumbering.

## 1. Product summary

Helps young adults convert idle screen time into small acts of production that accumulate into a finished, shareable project.

> **The promise:** finish a real project you chose, build proof of skill, and work alongside a small crew.

Not a confidence app, therapy product, social network, course platform, or screen blocker. Confidence is an outcome of repeated action and recorded evidence. Purpose emerges from chosen work, growing competence, contribution, and relationships.

## 2. Problem statement

The target user has unstructured time, wants to become more capable, and knows passive consumption isn't helping — but doesn't know what to make, can't reduce a project to a next action, fears producing something bad, has no external accountability, sees no objective evidence of progress, feels isolated from productive peers, and can't translate learning into portfolio evidence.

Existing tools each solve one part: blockers remove a distraction without supplying an alternative; task managers assume you know what to do; courses supply more content; public platforms optimise comparison; AI assistants generate output without ensuring the user acts, learns, or finishes.

## 3. Product thesis

When a person receives one appropriately sized mission, completes it, records evidence, and is seen by a consistent small group, they are more likely to keep producing and to build confidence through mastery.

**Autonomy is a mechanism, not a courtesy.** Boredom is failed engagement — a signal to pursue a *different* goal. A product that hands the user someone else's plan reproduces exactly the failure that makes courses feel inert. So the user chooses the project, the scope, and the finish line; the product supplies the next action, the evidence trail, and the crew. Where the product must choose for the user, it offers a default and makes overriding it obvious ([D-016](../log/decision-log.md)).

The loop: choose a meaningful project → receive one small next mission → produce something observable → record evidence and compare feared versus actual outcomes → share progress with a crew → increase difficulty gradually → finish and publish a proof-of-work artifact.

## 4. Goals and non-goals

**MVP goals.** Begin a first mission within ten minutes of onboarding. Complete a project the user scoped themselves, by a finish line they set. Generate visible evidence of skill, persistence, and contribution. Reduce friction between an idle moment and a meaningful next action. Create recurring low-pressure crew interaction. Measure behaviour rather than one subjective confidence score. Test whether users or institutions will pay.

**Non-goals.** Diagnose or treat any condition. Promise life purpose. Operate as a general social network or infinite public feed. Provide job placement or employment guarantees. Support users under 18. Block third-party mobile apps. Generate a finished project on the user's behalf. Include creator monetisation, tokens, or cash prizes. Support organisation administration beyond a basic pilot dashboard.

## 5. Users

| Persona | Age | Situation | Pain | Desired outcome |
|---|---|---|---|---|
| **A — Directionless graduate** | 21–26 | Recently graduated or between jobs | Time without structure, portfolio evidence, or confidence | A credible project to show in applications and interviews |
| **B — Creator who never publishes** | 18–30 | Many ideas, many unfinished drafts | Perfectionism, fear of judgment, inconsistent execution | One imperfect but complete published project, and a repeatable habit |
| **C — Student with unstructured time** | 18–24 | Studying, much free time on short-form content | Boredom, weak direction, few peers who make things | A demonstrable skill and productive peers |

**Secondary buyer:** universities, workforce programmes, bootcamps, community organisations, and employers, purchasing a cohort version to improve engagement, portfolio production, belonging, and transition-to-work outcomes.

## 6. Jobs to be done

**Primary:** when I feel bored, directionless, or tempted to scroll, help me start one meaningful action that contributes to a finished project.

**Supporting:** help me choose something challenging but achievable · tell me exactly what to do next · make it safe to show unfinished work · show me that feared outcomes beat actual ones · let a small group notice whether I showed up · turn completed work into proof · help me identify what work I want to continue.

## 7. Core experience

**Onboarding.** Create an account, confirm 18+, choose a desired outcome (portfolio, published creative work, evidence of a skill, momentum, career exploration), select or define a project, **set their own target finish date**, state available days and session length, complete a baseline under three minutes, join a crew, receive the first mission immediately. Never ask abstract questions like "what is your life purpose?" — ask for concrete interests, constraints, and outputs.

**Daily production.** The home screen foregrounds one action: *I have 5 / 15 / 30 / 60 minutes.* The system then presents one mission that begins with a clear verb, has one definition of done, fits the time, creates or improves an artifact, suits the project stage, and is never merely "research" or "think" without tangible output. The user can accept, simplify, replace, or report a blocker.

**Evidence.** Before a difficult mission, optionally record expected difficulty (1–5), expected discomfort (0–10), the feared outcome in one sentence, and completion confidence (0–100%). Afterwards record attempted, completed, actual discomfort, actual outcome, evidence attachment or link, what was learned, and whether to repeat, increase, or reduce difficulty.

**Crew.** Four to six active members. See each member's project and recent completed mission, post a short daily proof, react with bounded signals ("seen", "useful", "keep going"), request or give specific feedback, attend optional co-working, report content. No follower counts, popularity rankings, public like counts, or infinite feed.

**Weekly review.** Summarise missions planned and completed, production minutes, artifacts created or changed, predicted versus actual discomfort, repeated avoidance points, crew contributions, and progress against the user's own finish line. Then ask for one decision: continue at this level, increase challenge, or reduce scope to protect completion.

**Completion.** A project is complete when the user's own definition of done is met, the final artifact is uploaded or linked, a short summary is written, skills demonstrated are identified, at least one obstacle and response is recorded, peer feedback is optionally requested, and a shareable proof-of-work page is generated.

## 8. Functional requirements

| ID | Requirement |
|---|---|
| **FR-001** | Register with email or supported OAuth |
| **FR-002** | Confirm age eligibility and accept terms |
| **FR-003** | Set timezone, availability, interests, skills, privacy preferences |
| **FR-004** | Export or delete account data |
| **FR-010** | Select from project templates |
| **FR-011** | Create a custom project with title, outcome, audience, artifact type, **user-set target date**, and definition of done |
| **FR-012** | The system helps the user set scope and finish line, and flags when stated scope and stated availability are inconsistent. It does **not** impose a fixed programme length |
| **FR-013** | Reduce project scope without losing historical evidence |
| **FR-014** | Projects have stages: define, explore, build, test, revise, publish, reflect |
| **FR-015** | One active project at a time in the MVP |
| **FR-020** | Generate or select missions from project stage, available time, energy, skill level, dependencies, and recent behaviour |
| **FR-021** | Every mission has title, instruction, definition of done, estimated duration, difficulty, artifact type, and stage |
| **FR-022** | Accept, replace, simplify, skip, or report a blocker |
| **FR-023** | Repeated replacement triggers a scope or blocker review |
| **FR-024** | Non-AI fallback missions exist for every project stage |
| **FR-025** | Never generate dangerous, illegal, exploitative, or clinically framed missions |
| **FR-030** | Submit text, URL, image, or file evidence |
| **FR-031** | Attempts preserve planned, attempted, completed, and skipped states |
| **FR-032** | Predicted and actual discomfort stored separately |
| **FR-033** | Transparent progress metrics |
| **FR-034** | No universal "confidence score" is displayed |
| **FR-035** | Browse the evidence timeline, filtered by stage or skill |
| **FR-036** | Completed evidence can be added to the proof-of-work page |
| **FR-040** | Join a crew by invitation or matching |
| **FR-041** | Matching considers timezone, project category, session preference, language |
| **FR-042** | Leave, mute, or report a crew |
| **FR-043** | Crew posts are chronological and bounded |
| **FR-044** | Members can request structured feedback |
| **FR-045** | Moderators can remove content and suspend accounts |
| **FR-046** | Crew codes for institution-led pilots |
| **FR-050** | Schedule one daily production reminder |
| **FR-051** | Notifications reference a concrete next mission, never guilt or streak loss |
| **FR-052** | Disable all non-essential notifications |
| **FR-053** | Crew notifications batched by default |
| **FR-060** | Generate a proof-of-work page |
| **FR-061** | Pages show artifact, contribution, skills, process evidence, reflection |
| **FR-062** | Public, unlisted, or private visibility, user-controlled |
| **FR-063** | Public pages never expose anxiety or discomfort data by default |
| **FR-070** | Administrators create a cohort and invite users |
| **FR-071** | Administrators view aggregate activation, participation, completion |
| **FR-072** | Administrators cannot read private reflections unless explicitly shared |
| **FR-073** | Aggregate reporting suppresses personally identifiable data where practical |

## 9. Measurement

Observable metrics only: missions attempted and completed, completion rate, production minutes, artifacts created or revised, drafts shared before feeling ready, stage progression, crew feedback given and received, predicted versus actual discomfort, project completion, proof-of-work pages published, and continued production after completion.

```text
7-day completion rate      = completed missions / accepted missions
difficulty-adjusted output = sum(completed mission difficulty)
prediction gap             = predicted discomfort - actual discomfort
production consistency     = active production days / planned production days
artifact progression       = completed required stages / total required stages
```

No derived metric may be presented as a clinical measure or a measure of a person's worth.

## 10. Success criteria

Pilot decision thresholds, not industry benchmarks.

- **Activation:** 70% of registered pilot users accept a project · 60% complete a first mission within 24 hours · median registration→first accepted mission under 10 minutes.
- **Engagement:** 50% complete three missions in week one · 40% still active in week three · 50% post or respond in their crew in week one.
- **Outcome:** 30% complete their project · 40% produce a shareable artifact · 50% report the result is useful for a portfolio, application, or continued work · 25% begin another project within 14 days.
- **Commercial:** 15 individuals pay at a tested price · three institutional buyers agree to a discovery meeting · one institution signs a paid or deposit-backed pilot before major platform expansion.

## 11. Monetisation hypotheses

Test, don't assume. **B2C outcome purchase:** USD 29–79 for one project taken to completion — bounded by outcome, not by calendar. **B2C membership:** USD 8–15 monthly *after* a first completed project. **Institutional:** per-seat pricing. **Facilitated:** higher-priced, with human review and group sessions.

The first commercial test favours a bounded outcome over an indefinite subscription. The user must understand exactly what they are buying.

## 12. Safety, ethics, trust

Not therapy or medical treatment, and it says so. No shame, no withdrawal of social status, no punitive streaks. No encouragement of sleep deprivation, overwork, dangerous challenges, harassment, unauthorised access, or public exposure without consent. Reporting, blocking, and moderation controls throughout. Minimal collection of sensitive mental-health information. Private discomfort ratings never revealed to crews or administrators. AI missions and feedback pass content and schema validation. The core programme is completable without ever sharing publicly. Moderation policy covers abuse, sexual content, hate, self-harm content, exploitation, and IP violation.

If a user expresses acute distress, the product stops productivity coaching and presents location-appropriate crisis-support guidance. It does not attempt counselling.

## 13. Non-functional requirements

| ID | Requirement |
|---|---|
| **NFR-001** | Core authenticated pages usable within three seconds on typical mobile connections |
| **NFR-002** | Mission submission is idempotent and recoverable after network interruption |
| **NFR-003** | WCAG 2.2 AA for core flows |
| **NFR-004** | All MVP flows work at 360 px width |
| **NFR-005** | Encryption in transit and at rest via managed infrastructure |
| **NFR-006** | Private reflections stored separately from public portfolio data |
| **NFR-007** | Structured error and event logging, with no reflection text in analytics |
| **NFR-008** | Users export project and evidence data as JSON or CSV |
| **NFR-009** | Core flows remain usable when the language-model provider is unavailable |
| **NFR-010** | Reusable templates cached; per-user generation limits enforced |

## 14. Release boundary

An earlier version of this section bundled crews and cohort administration into the "first production release", contradicting the phased plan in [initial design](initial-design.md) §17. The phased plan governs ([D-013](../log/decision-log.md)).

**First release — solo MVP only:** web authentication, onboarding and baseline, project templates plus one custom project, mission generation with template fallback, mission attempts and evidence, transparent progress dashboard, proof-of-work page, analytics.

The goal is to prove activation and completion *without* community complexity. Crews are the largest source of scope, risk, and cold-start difficulty; shipping them alongside the core loop would make it impossible to tell which one failed.

**Second release — crews:** chronological updates, structured feedback, matching, moderation, weekly review.  
**Third release — institutional:** cohort administration, aggregate dashboard, facilitator tools.

Native mobile, application blocking, live video coworking, employer matching, sophisticated recommenders, and public discovery are later-stage.

## 15. Open questions

To be resolved by paid pilots, not internal debate.

1. Which initial project category produces the clearest value — software, design, research, content, community service, or mixed?
2. Is the primary payer the individual, university, workforce programme, or employer?
3. Are crews created at onboarding or after a first completed mission?
4. How much human facilitation is required for acceptable completion rates?
5. Does a user-set finish line outperform a suggested default — and what default should be offered to users who ask for one?
6. Which final artifact persuades buyers: portfolio page, skills report, completed project, or verified contribution record?
7. Should the first market be geographically local, English-speaking global, or institution-specific?
