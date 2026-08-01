# Decision Log and Work Log

**Product:** ForgePath *(placeholder name — to be replaced)* · **Append only**

> **Related:** [Demand](../product/demand.md) · [Requirements](../product/requirements.md) · [Initial design](../product/initial-design.md) · [BMAD path](../method/bmad-path.md) · [Future plans](../roadmap/future-plans.md)

Reversed decisions are marked `Superseded`, never deleted — the wrong ones are the ones worth keeping. IDs are never reused.

## Decisions

| # | Decision | Why | Status |
|---|---|---|---|
| **D-001** | Sell completion, not boredom relief | Boredom scores 2.4/5 on willingness to pay; completion 4.2/5. | Amended by **D-022** — the thing sold is reclaimed time; completion is how it's proved |
| **D-002** | Beachhead 18–26 in transition to work | Narrow enough to write copy for, reachable through institutions. | Amended by **D-019** |
| **D-003** | Bounded purchase before any subscription | The buyer must know what they bought; subscriptions churn on day one. | Superseded in part by **D-016** — bounded by outcome, not calendar |
| **D-004** | No clinical claims, no shame mechanics | A completion product leaning on guilt produces compliance, not mastery. | Accepted |
| **D-005** | AI never authors the artifact | Its whole value is being defensible. Every competitor will offer to just make the thing; refusing is a real conversion cost. | Accepted as a cost |
| **D-006** | Every AI path ships a non-AI fallback | The loop can't break because a provider is down. Makes manual templates priority #1. | Accepted |
| **D-007** | Web-first; no native apps, no blocking | Blocking is crowded and isn't the differentiator — what appears *after* is. | Accepted |
| **D-008** | No feed, no follower counts; crews of 4–6 | A feed creates the comparison pressure that stops people publishing at all. | Accepted |
| **D-009** | Transparent quantities, never one score | A composite score is unfalsifiable and drifts toward measuring the person. | Accepted |
| **D-010** | Concierge test before installing BMAD | Planning efficiency works against us on unvalidated assumptions. | Accepted |
| **D-011** | Docs-only repo; `DESIGN.md` → `initial-design.md` | "Design" implied a settled architecture. | Accepted |
| **D-012** | MIT licence | Frictionless while the asset is a thesis rather than code. | Provisional — revisit before the first outside contribution |
| **D-013** | Solo release ships alone; crews later | Crews are the largest source of scope and cold-start risk; shipping together hides which one failed. | Accepted |
| **D-014** | Hand-pick crews; don't build matching | Matching solves a liquidity problem we don't have. | Accepted |
| **D-015** | Name deferred | Naming ahead of validation locks a name to positioning that's still moving. Cheap now, expensive once a domain exists. | Open — before the first cohort |
| **D-016** | No fixed programme length; user sets scope and finish line | A prescribed container removes the independence of choice that resolving boredom depends on. **Cost:** "in 30 days" was concrete marketing and a real deadline effect; both given up. | Accepted |
| **D-017** | Consequence visibility replaces discipline | Discipline is consequence-blindness plus force. Something must do the job motivation is bad at, and that job goes to arithmetic, not obligation. | Accepted — mechanic changed by **D-024** from forward projection to backward mirror |
| **D-018** | First cohort unpaid | Founder is under 18 and can't hold a processor account. **A real loss of evidence** — free cohorts overstate commitment, and that limitation travels with every number produced. Never re-read as commercial validation. | Accepted under constraint |
| **D-019** | Add 16–18 as a second segment | School access makes it reachable and testable in a way the primary market isn't. **Cost:** guardian consent, no mixed-age crews, no DMs, Children's Code (`FR-080`–`FR-086`). | Accepted |
| **D-020** | Pre-register predictions before any cohort | Adopted from the sibling manipulation-recognition rubric. Completion rate is the load-bearing unknown; writing the expected number down first is what stops us rationalising whatever arrives. | Accepted |
| **D-021** | Red-team against the manipulation taxonomy; agency real before legible | The sibling project catalogues exactly the techniques this one could reach for. Manufacturing a feeling of control the user lacks is the dark pattern that project exists to detect. | Accepted |
| **D-022** | **The spine: time is control, generic apps took it, this returns it** | Money and being valued are both instrumental; time is closer to terminal. Boredom is time you can feel passing — the residue after an evening spent on nothing. Everyone else is fighting for *less* screen time; nobody is selling it *back*. **Boredom is not promised away:** when scrolling stops it arrives undiluted, and saying so is the only honest position and the only differentiated one. | Accepted |
| **D-023** | Fear is downstream of boredom; intervene at making | The chain runs boredom → consumption → not creating → no confidence → fear. Because boredom is *first* and fear is late, treating the fear directly treats a symptom. Mission one is *make something*, not *survive being seen*, and the predicted-vs-actual discomfort machinery is demoted to optional (`FR-032`). | Accepted — chain extended by **D-027**, which puts laziness after fear |
| **D-024** | Present tense: cut every *will* and *have* mechanic | *Will* (countdowns, goal ceremonies, deadline projections) and *have* (badges, streaks, trophies, portfolio-as-achievement) both pull the user out of now, which is where the product works. Retires `FR-017`'s deadline projection in favour of the backward-looking time mirror (`FR-019`). | Accepted |
| **D-025** | Audience ladder — no first ship goes into a void | The internet's default response is silence, and a promise of external proof fails hardest at the moment the user is most exposed. Every rung has a guaranteed responder before the next unlocks. This is the part nobody else builds and the reason the proof is deliverable rather than hoped for. | Accepted — rung one changed by **D-033** from a crew to one known person, or the operator in hand-run cohorts |
| **D-026** | The artifact is a by-product, not the promise | Things you *have* devalue — a portfolio page is worth little in five years. Time spent authoring doesn't devalue. The proof-of-work page stays as the receipt that the hours were real; it stops being the reason for the work. | Accepted |
| **D-027** | Laziness is the last link in the chain, and it is a verdict rather than a cause | Nobody says "I'm afraid to make a website"; they say "I couldn't be bothered". So laziness is what users **report** while fear is what **happens** — and it is the only link phrased as an identity rather than a state. Fear says *this might go badly*; laziness says *I am someone who doesn't do things*, which pre-explains every future instance and is what makes this a stable loop rather than a bad week. Three consequences: the time mirror's job is to make the verdict untenable against a record, not to inform or motivate; interviews must treat a laziness self-description as the first answer and ask once more; and no copy, mission, notification, or empty state may ever describe the user, only what they did. | Accepted |
| **D-028** | No scope, no finish line — the product never asks how big or by when | D-016 removed the *imposed* 30 days but kept a user-set target date, which was inconsistent: D-024 had already killed the deadline projection as a *will* mechanic while leaving the date that fed it. The deeper objection is that when someone is doing what they actually want, size and deadline are irrelevant — and the pressure they add is itself a reason people stop. *Done* is defined per mission; the project has no finish line. The 72-hour first ship keeps work small without anyone declaring a size. **Cost:** no completion metric, so success is measured in ships and responses instead. | Accepted — supersedes the finish-line half of **D-016** |
| **D-029** | Show, don't tell | Show what the user can do; never tell them what to feel, what to achieve, or what they already know about themselves. Goals are now written as things the product *does*, not states the user should reach — a goal phrased as a feeling can't be built and can't be falsified. | Accepted |
| **D-030** | Choice reveals preference; the recall questionnaire is retired | *"When did you last lose track of time?"* is a self-help cliché, and worse, it's redundant — people already know what absorbs them and what they're avoiding. Knowing was never the missing piece. Replaced by putting real options in front of them and recording what they pick and pass over. A choice is evidence; a self-report is a performance. | Accepted — retires the recall step added 1 Aug |
| **D-031** | Session mood, before and after, is the one internal state recorded | Everything else in this product measures behaviour, and D-009 forbids scoring internal states. This is a deliberate, narrow exception, and the distinction that makes it safe is **who is the subject**: D-009 forbids the *product rating the user*; this is the *user rating a session*. One tap each side, optional, private, never scored, never averaged into a profile, never shown to anyone. It earns the exception because the delta is the only direct measure of the actual promise — that the time felt different afterwards. Aggregate cohort median is a success criterion; per-user values are never surfaced. | Accepted |
| **D-032** | No account until there is something worth keeping | Registration before value is a gate in front of the only thing that matters — getting someone making within ten minutes. Work is held locally and registration is offered when it would otherwise be lost. **Cost:** anonymous sessions complicate storage, analytics, and the age gate, and the under-16 check has to happen before any crew or public surface rather than at first touch. | Accepted |
| **D-033** | Crews deferred to *maybe* | A social component at signup is a barrier for exactly the person this targets — someone avoiding being seen. Crews are specified but unscheduled. **This breaks a dependency:** D-025's ladder used the crew as the guaranteed first responder. Rung one becomes *one person the user already knows*, and during hand-run cohorts the operator is the guaranteed responder — which is more honest anyway, since a hand-run cohort has one. | Accepted |

## Open risks

Untested assumptions everything rests on.

| Risk | Why it's load-bearing |
|---|---|
| **Reclaimed time is felt but not bought** | The demand doc scores the time framing lower on willingness to pay than the portfolio framing, and higher on frequency and open competitive space. Both are guesses. Phase 3 tests all three messages rather than assuming. |
| **The first ship lands in silence** | The audience ladder is the mitigation, and it is unproven. If guaranteed responses feel manufactured, they won't update anyone's self-concept. |
| **How big must the first response be** | A crew member being kind is dismissible as politeness; a stranger paying isn't. There's a threshold below which evidence doesn't change how someone sees themselves, and nobody knows where it sits. |
| **Who it's actually for** | The idle moment is a low-executive-function state. The sibling project's field notes found heavier low-value-content consumption tracks with *less* self-recognition of a problem — so the people who most need this may be least likely to seek it. |
| **Payer mismatch** | Users have time and no money; institutions have money and long cycles needing evidence that requires users first. |

## Work log

**1 August 2026 — Onboarding stripped; crews deferred.** D-028 through D-033. The finish line went, and with it an inconsistency: D-024 had already cut the deadline projection as a *will* mechanic while leaving the user-set date that fed it. The recall questionnaire went too — people already know what absorbs them, so asking was a cliché that changed nothing; replaced by showing real options and recording the pick. Registration moved behind the first mission. Crews deferred to *maybe*, which broke D-025's first ladder rung — now one person the user knows, or the operator during hand-run cohorts.

One thing added rather than removed: an optional before/after session mood tap (D-031). It is the only internal state recorded anywhere, and it earns the exception to D-009 because the subject is different — the product never rates the user; the user rates a session. The cohort median is now a success criterion, replacing "reach their own definition of done", which no longer exists.

**1 August 2026 — Laziness added as the chain's last link.** D-027. It is what users report while fear is what happens, and the only link phrased as an identity — which is what makes the loop stable. Gives the time mirror a narrower job than it had: dispute the verdict, rather than inform or motivate. Adds a copy constraint (never describe the user, only what they did) as a principle in both product docs and a BMAD guardrail, and a follow-up question to the Phase 1 interview script with its own threshold.

**1 August 2026 — Rebuilt around time and control.** The docs previously sold process with the payoff six weeks out, which is the version nobody would use. New spine in D-022; fear placed downstream of boredom in D-023, moving the intervention to making; present-tense filter in D-024; audience ladder in D-025; artifact demoted in D-026.

Model gains `Artifact`, `Ship`, `Response`, and `ProductionSession` — the old one could record that work happened but not that it landed, which is the only thing the new thesis cares about. Distribution becomes a first-class mission kind rather than a later phase. `FR-017` retired; `FR-019`, `FR-026`, `FR-027`, `FR-036` added. Product docs cut a further ~30%.

**1 August 2026 — Autonomy work.** D-017 through D-021: consequence visibility, unpaid cohort, 16–18 segment with safeguarding requirements, pre-registration, manipulation red-team.

**31 July 2026 — Structure and first cuts.** Reorganised into `docs/{product,method,roadmap,log}`, renamed the design document, removed the fixed 30-day programme (D-016), cut the product docs by 65%, resolved a contradiction between the requirements release boundary and the phased delivery plan.
