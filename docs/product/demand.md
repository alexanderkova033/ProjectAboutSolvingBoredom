# Demand and Market Thesis

**Product:** Freathe · **Status:** Market hypothesis and validation plan · **Feeds:** the BMAD Analyst brief · **Snapshot:** 2 August 2026

> **Related:** [Requirements](requirements.md) · [Initial design](initial-design.md) · [BMAD path](../method/bmad-path.md) · [Decision log](../log/decision-log.md)

> Every number is either a cited source (§10) or a labelled hypothesis. §6 scores are assumptions, and §7's channels are bets with tests attached rather than a plan. Nothing is validated until §8 has run.

## 1. Thesis

> **Time is control. Generic apps took the control. This gives it back.**

Not more content, not less screen time, not a course. The product returns authorship of your own hours, and the proof it worked is that the week left something behind.

Boredom is time you can feel passing. Time in flow disappears; time spent consuming drags *and* leaves a residue. Same clock, opposite relationship to it. That residue is what the product removes, and it can do it in the first week rather than the sixth.

## 2. The problem

The chain runs one way, and the order decides where to intervene:

```text
boredom → consumption (easier) → not creating → no confidence → fear → "I'm just lazy"
        ↑                                                                      │
        └──────────────────────────────────────────────────────────────────────┘
```

**Boredom is upstream** ([D-023](../log/decision-log.md)) — so the intervention is *creating*, not fear-management. Confidence is a by-product of having made things; treating the fear directly treats a symptom.

**The last link is a verdict, not a cause** ([D-027](../log/decision-log.md)). Laziness is the socially acceptable name for avoidance, so it's what people say while fear is what's happening. It's also the only link phrased as an identity — *I am someone who doesn't do things* — which explains away every future instance and makes this a stable loop rather than a bad week. Expect it in every interview and hear past it.

**Research supports the entry point.** Boredom is failed engagement, a signal to pursue a *different* goal — and rapidly switching between videos to escape it makes people **more** bored, not less. The signal is real; the apps intercept it before it reaches you. More stimulation can't resolve disengagement, and blocking removes the stimulation without returning anything.

**And the exit.** Self-efficacy is built primarily through **mastery experience** — having done the thing — and only weakly through persuasion or reassurance. That's the mechanism behind *make something and confidence follows*, and why a product that tells the user they're capable does nothing while one that leaves them holding evidence does. It's borrowed rather than proven here: the literature is about efficacy at a task, not a person's verdict on themselves, and the jump between them is ours to test.

Two pressures make the audience reachable rather than merely sympathetic: the ILO put youth unemployment near 12% against 4.9% overall in 2024, with ~262 million 15–24s not in employment, education, or training; and the WEF's *Future of Jobs 2025* found 39% of skill sets expected to change by 2030, with the durable ones being exactly what AI doesn't supply — choosing problems, persisting, judging, finishing.

## 3. What is actually being sold

Four layers. Only the middle two ever appear in the product.

| Layer | Content | Rule |
|---|---|---|
| **Why** | Happiness, and a life that feels like the user's own | Never say it. Every product claims happiness; the claim carries no information |
| **Promise** | Reclaimed time — a week that left something behind instead of nothing | This is the pitch. **Time is spoken and happiness is not**, and the difference is that one is observable: an evening either produced something or it didn't, while a claim about how someone feels can't be checked by the person hearing it |
| **Proof** | One real external event — someone used it, responded to it, paid for it | The only honest source of the internal change |
| **Measure** | Shipped, responded to, hours that produced something | External and falsifiable only. Never score how anyone feels |

The internal outcome is the product; the external event is what makes it real. Confidence is belief calibrated to evidence — remove the evidence and it's a mood, and moods don't change what someone does on a Tuesday.

**Boredom is not promised away.** When the scrolling stops, boredom arrives undiluted. That is the point, and saying so is the only honest position available — every competitor promises the removal of discomfort ([D-022](../log/decision-log.md)).

## 4. Competitive landscape

| Category | Examples | Gap |
|---|---|---|
| Screen-time blockers | Opal, ScreenZen, Brick, OS controls | Remove the app and return nothing. Success measured as reduced use, not reclaimed time. Bypassed the moment motivation dips |
| Accountability and coworking | Focusmate | You must already know what to do. No decomposition, task-agnostic partners |
| Courses, bootcamps, cohorts | Many | Completion means content consumed. Someone else's plan — the thing that makes them inert |
| Project communities | Buildspace (closed) | Validated the interest; its closure warns that enthusiasm isn't a business |
| AI coaches | Many | RevenueCat's 2026 analysis of 115,000+ subscription apps: AI apps monetise better early (41% median year-one revenue-per-payer premium) and retain materially worse at 12 months. Not durable positioning |

Everyone in the first row is fighting for *less*. Nobody is selling *back*.

**Everyone cuts the loop where cutting is easiest. This cuts it where cutting propagates.** Blockers attack *consumption*, the cheapest link, because removal is just subtraction — and subtraction propagates nowhere: the user gets the boredom back with nothing to put in the gap, which is why blockers get bypassed the moment motivation dips. Cutting at *not-creating* is the only intervention that moves forward through the rest of the chain unassisted. Fear and laziness are never treated directly; they're downstream, and they starve.

Say the mechanism, never the depth. *"Everyone else treats symptoms, we treat the cause"* is a genre convention, unfalsifiable, and precisely the pattern the red-team in [D-021](../log/decision-log.md) exists to catch.

## 5. Beachhead

**Primary — 18–26, English-speaking:** recent graduates, unemployed or underemployed, students near the transition to work, self-taught creators. Able to work alone, unable to finish, aware the evenings are going somewhere.

**Second segment — 16–18 in school:** added because school access makes it reachable in a way the primary market isn't ([D-019](../log/decision-log.md)). Adjacent pain — not "I need a portfolio" but "I have nothing that's mine." **Blocked, not scheduled** ([D-046](../log/decision-log.md)): it needs a named responsible adult and the founder is under 18. Phase 0 is adults only, which closes the one channel with real access.

**Excluded:** under 16 · "everyone who is bored", too broad to write copy for · clinical framing of any kind.

**Payers.** Not the user, and not a parent ([D-060](../log/decision-log.md)) — a funder, and secondarily a school, a university career centre, a workforce programme, or an employer. All of them have budget, long cycles, and the same demand for evidence.

## 6. Demand scoring

Founder hypotheses, not measurements.

| Opportunity | Frequency | Urgency | Willingness to pay | Measurability | Competition | Overall |
|---|---:|---:|---:|---:|---:|---:|
| Generic confidence app | 4 | 2 | 2 | 2 | 5 | 2.4/5 |
| Generic boredom app | 5 | 1 | 1 | 2 | 3 | 2.4/5 |
| Screen-time blocker | 5 | 3 | 3 | 5 | 5 | 3.4/5 |
| Project completion system | 4 | 4 | 4 | 5 | 3 | 4.0/5 |
| Reclaimed-time system | 5 | 4 | 3 | 4 | 2 | 4.0/5 |
| Youth portfolio sprint | 4 | 5 | 4 | 5 | 3 | 4.2/5 |

The portfolio sprint scores highest on paper — and it's the version that assumes an artifact people want, six weeks out. The reclaimed-time framing scores lower on willingness to pay and higher on frequency and competitive space. **This tension is unresolved and §8 exists to resolve it.**

The willingness-to-pay column is weaker than it looks now ([D-060](../log/decision-log.md)): the user never pays, so what the column has to predict is whether a funder or an institution finds the outcome legible — a different question, and one nobody in this table was scored against.

## 7. Distribution and market model

```text
Reach:  reachable qualified audience × people who start something × people who ship
Funded: funders and partner institutions × places supported × cost per place
```

Neither line has a paid-conversion term any more ([D-060](../log/decision-log.md)) — the user is not the payer. Distribution still dominates both, and the missing input isn't a rate: it's a channel.

**There is no search demand** ([D-044](../log/decision-log.md)). Nobody types this into a search box, and the reason is in our own risk register: the people furthest into the loop recognise it least as a problem. Intent-based acquisition has nothing to bid on, which rules out search independently of budget.

**They do complain, and the complaint is the channel.** This loop gets described in public constantly, in the chain's own last-link language — *wasted the whole evening again*, *I have no hobbies*, *I'm just lazy*. A complaint is the only reliable signal that someone is in the market, so where it gets posted is where the market is reachable.

Four hypotheses, none validated, and one of them closed for the duration of Phase 0:

| Channel | The bet | The test |
|---|---|---|
| **Where the complaint is posted** — procrastination and quarter-life communities, self-taught-creator and study servers, "I have no hobbies" threads | Someone describing the residue of a lost evening is qualified in a way no ad targeting reproduces. Costs time, not money | Reply to real posts with the real thing, two weeks. Count **qualified replies and first missions started**, not impressions. Kill it if the response reads as spam to the community it's in |
| **In person, through the founder's own segment** | The only channel with genuine access, zero cost, and a warm room — and the actual reason the 16–18 segment exists | **Closed for the concierge phase** ([D-046](../log/decision-log.md)). Reopens with a named responsible adult, not before |
| **The artifact carries the trace** — things shipped point back at where they were made | Costs nothing per unit and keeps working with nobody doing anything — a property of shipping rather than an activity, which no other channel here has | Untestable until things are shipping to strangers at all. Not a first channel |
| **Publish what the cohort made** ([D-057](../log/decision-log.md)) — video, where this problem is *consumed* even though nobody searches for it | The only compounding channel that can be **started now** — the artifact trace above compounds too and cannot be run until things are already shipping. **Not an advertisement:** the self-improvement genre runs on the promises §3 forbids, so the winning format there is the one we banned. What needs no forbidden claim is someone who had made nothing, three weeks later holding a small thing a stranger used | Consent per participant, never assumed. Count **missions started, not views**. Follows Phase 1 rather than replacing it — one good video is a week not spent interviewing. Kill it if it can't be made without a claim §3 forbids |
| ~~**A store listing for the card**~~ | Withdrawn with [D-059](../log/decision-log.md). Both stores need an adult-held account, and there is no native artifact to list — the phone surface is a web page you install. **An app store was a channel; a URL is not one** | Nothing to test. Losing it puts the weight back on the complaint threads, which is the one channel that can be run this week |

**Refused.** Paid acquisition — there is no lifetime value to weigh a cost against, and under [D-060](../log/decision-log.md) there will not be one in the usual sense, so no acquisition cost can be justified; buying traffic against an unvalidated message burns the message and the money together. Productivity-influencer content — the genre runs on exactly the promises §3 forbids, and arriving through it sets expectations the product then breaks on purpose. **This is not the same as [D-057](../log/decision-log.md):** the refusal is on *making the claims the genre runs on*, whoever makes them, and publishing a record of what somebody actually built makes none of them. The line is the claim, not the platform.

Institutional distribution is a sales motion rather than a channel, and downstream of all of the above: schools want evidence, evidence requires users, users require a channel.

## 8. Validation plan

**Phase 1 — Problem interviews.** 30+ in the beachhead. Never "would you use this?" Ask: what did you do last night, and how did you feel at the end of it · when did you last make something · what stopped you · who notices whether you do anything. **The script is [interview-script.md](../method/interview-script.md)**, and five to eight conversations already teach most of it — thirty is what these thresholds need, not what learning something costs.

**One question decides whether the ladder is the right mechanism** ([D-054](../log/decision-log.md)): *describe a time something changed for you — what happened?* Then code each answer as **someone reacted to what I made** or **someone was there when I started**. The product is built entirely on the first; the only three first-hand accounts available to us are the second. Ask it late in the interview and never explain why.

Record two facts alongside the answers, because they cost nothing to collect and each decides a build: **what phone they carry** — the surface is web on both platforms now ([D-059](../log/decision-log.md)), but an Android-carrying beachhead is the one finding that would bring the widget back ([D-052](../log/decision-log.md)) — and **whether they own a laptop at all** ([D-051](../log/decision-log.md) assumes one). Neither is a question about the product, so neither is subject to the demand characteristics that make everything else here soft.

**Most will answer "I'm lazy" or "I couldn't be bothered."** That's the beginning of the answer, never the end — follow it with *what did you imagine would happen if you tried?* The gap between the two responses is the most valuable data in the interview ([D-027](../log/decision-log.md)).

*Threshold:* 15+ describe the evening-residue feeling unprompted · 10+ have a workaround · 10+ move off a laziness self-description when asked once more · language converges on one concrete outcome.

**Phase 2 — Concierge cohort, unpaid, 18+ only.** 20–30 users, run by hand. Forms, a spreadsheet, hand-written missions, a guaranteed responder.

*Adults only* ([D-046](../log/decision-log.md)). The forms collect real personal data with no product to gate it, so recruiting minors would engage UK GDPR and a school's safeguarding policy with none of `FR-080`–`FR-086` in existence — and the founder, being under 18, cannot be the responsible adult that requires.

*Split the roles* ([D-047](../log/decision-log.md)). One person writing missions, guaranteeing the response, and running exit interviews stacks three demand characteristics on a cohort already unpaid. **Minimum: the exit interviewer is never the operator.** Report the separation that actually ran alongside the numbers it produced.

*Unpaid weakens the evidence* ([D-018](../log/decision-log.md)) — free cohorts overstate commitment, and this limitation travels with every number produced here. A good result must never be re-read later as commercial validation.

*Lock predictions first.* Write the expected value for every threshold below, commit the file, then run it ([D-020](../log/decision-log.md)).

*Proceed if:* 60% ship something within 72 hours · 50% produce in three separate sessions in week one · 40% of sessions contain a further unprompted mission ([D-045](../log/decision-log.md)) · **40% report the week felt different** · users describe the *time*, not the motivation, as what changed.

*Read the self-reports with the confound attached.* "The week felt different" comes by hand, from a free cohort, from people who chose to be there — the softest number in the plan and the easiest to over-read. The hard ones are ships, responses, and unprompted continuations.

*Interview everyone who stopped.* They are the product risk, and a free cohort makes them easy to ignore.

**Phase 3 — Message test.** Three landing pages, design and traffic held constant: reclaimed time · finished thing · productive belonging. Measure qualified visitor→application, application→first ship, week-one production. Not email signups. *A message test needs traffic* — so §7's first channel is tested **before** this phase, and the winning message is only meaningful for the channel that carried it.

**Phase 4 — Funder and institutional discovery.** Grant funders and youth foundations ([D-060](../log/decision-log.md)), then schools, career centres, workforce organisations, employer graduate programmes. Ask for a budget, a grant round, or a letter of intent. A positive interview without a buyer and a procurement path is not validation, and enthusiasm from a funder is worth exactly what enthusiasm from a user is.

## 9. Risks

| Risk | Mitigation |
|---|---|
| **Nobody encounters it** | The largest and newest. No channel is validated and there's no search demand. §7 names three hypotheses and one cheap test; run it before the message test ([D-044](../log/decision-log.md)) |
| **Nothing brings anyone back** | Every conventional retention lever is banned on purpose ([D-042](../log/decision-log.md)). Two unproven mechanisms remain — the work being pleasant ([D-045](../log/decision-log.md)) and a response arriving — plus one surface, an icon on the first home screen ([D-049](../log/decision-log.md), [D-061](../log/decision-log.md)), which is seen at unlock, removes the excuse of having forgotten, and supplies no motive of its own. §8 measures return against responses received |
| Reclaimed time is felt but not funded | The user was never the payer ([D-060](../log/decision-log.md)), so the question is whether a funder finds reclaimed hours legible or wants a countable outcome instead. Keep the artifact as proof; test all three messages in Phase 3 rather than assuming |
| The first ship lands in silence | Engineer the audience ladder ([D-025](../log/decision-log.md)), ordered by audience size rather than familiarity so the first rung isn't also the most exposing ([D-043](../log/decision-log.md)). **Never by a self-response** ([D-055](../log/decision-log.md)) |
| **The change moment isn't a response at all** | The ladder assumes a reaction to finished work is what changes someone. The only first-hand accounts we have describe *someone competent present at the start* instead ([D-054](../log/decision-log.md)). One interview question settles it, and it is asked in Phase 1 — before the ladder is built |
| Users need heavy facilitation | Measure facilitator minutes per active user; standardise before automating |
| AI does the work instead of the user | Require decisions, process evidence, attribution |
| Time mirror reads as judgment | Count what was made; never scold the rest. If it feels like a screen-time dashboard it has become the enemy |
| Drift into mental-health claims | Behavioural language only; refer out when appropriate |

Load-bearing untested assumptions are tracked in the [decision log](../log/decision-log.md).

## 10. Sources

1. WHO, *Commission on Social Connection* / 2025 report — https://www.who.int/groups/commission-on-social-connection · https://www.who.int/publications/i/item/978240112360
2. WHO, *Social connection: Q&A* — https://www.who.int/news-room/questions-and-answers/item/social-connection
3. ILO, *WESO Trends 2025 in figures* — https://www.ilo.org/resource/other/world-employment-and-social-outlook-trends-2025-figures
4. ILO, *NEET vs youth unemployment* — https://www.ilo.org/resource/article/measuring-what-matters-neet-vs-youth-unemployment
5. ILO, *Global Employment Trends for Youth 2024* — https://www.ilo.org/resource/article/global-employment-trends-youth-2024-figures
6. WEF, *Future of Jobs Report 2025* — https://www.weforum.org/publications/the-future-of-jobs-report-2025/digest/
7. APA, *Swiping through online videos increases boredom* (2024) — https://www.apa.org/news/press/releases/2024/08/online-videos-boredom
8. *In search of boredom: beyond a functional account* (2023) — https://pubmed.ncbi.nlm.nih.gov/36922277/
9. *The motivational consequences of boredom* (2025) — https://pubmed.ncbi.nlm.nih.gov/41071937/
10. Focusmate — https://www.focusmate.com/about/ · ScreenZen — https://screenzen.co/ · Opal — https://www.opal.so/ · Buildspace — https://buildspace.so/
11. RevenueCat, *State of Subscription Apps 2026* — https://www.revenuecat.com/blog/growth/subscription-app-trends-benchmarks-2026
12. Bandura, A., *Self-efficacy: toward a unifying theory of behavioral change*, Psychological Review 84(2), 191–215 (1977); developed in *Self-Efficacy: The Exercise of Control* (1997) — mastery experience as the primary source of self-efficacy. Cited by reference; verify the link before publication
