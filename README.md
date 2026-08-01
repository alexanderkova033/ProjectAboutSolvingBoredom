# ForgePath

*Placeholder name. A real one gets chosen before the first cohort — see [D-015](docs/log/decision-log.md).*

**Your evenings are going somewhere. This is how you get them back.**

Time is control, and generic apps took the control. You already have the hours — four of them went somewhere last night. What you don't have is any evidence they were yours.

So: it shows you things you could make and you pick one. No sign-up, no questionnaire, no goal-setting — the first screen is something to do. It asks how long you've got, five minutes or an hour, and gives you one thing with a clear definition of done. You make something small, you get it in front of a real person, and someone responds. At the end of the week it shows you the hours that left something behind.

Nothing asks how big it is or when it'll be done. No countdown, no streak, no curriculum, no AI writing it for you.

## What it isn't

It won't make you happy and it won't make you money, and anything claiming otherwise is selling something. It also won't make boredom go away — when the scrolling stops, boredom arrives undiluted. That's the point. Boredom is a signal to go do something else, and the apps have been intercepting the signal before it reaches you.

Blockers close the app and hand back nothing. Courses hand you someone else's plan. Task managers hand you back the backlog you already had. AI assistants hand you a finished thing you can't take credit for.

## Current state — planning, pre-code

**There is no software yet. This repository is a product thesis.**

Written: the market case, the requirements, an initial design, and the build method. Next: a cohort run entirely by hand, with predictions written down and committed before it starts. Then a solo release, then crews, then institutional pilots.

Nobody has used this. Every number in these documents is a hypothesis with a threshold attached, and [demand](docs/product/demand.md) §8 says what evidence would kill it.

What isn't known:

- whether reclaimed time is something people will pay for, or only something they feel;
- whether a first ship gets a response, or silence — the default outcome online;
- how big that first response has to be before it changes how someone sees themselves;
- whether this reaches the genuinely stuck, or only the already-motivated.

And one thing that can't be known yet: the first cohort runs unpaid, so nothing here will be evidence that anyone will buy it ([D-018](docs/log/decision-log.md)).

## The documents

**[demand.md](docs/product/demand.md) — should this exist?** The market case. Why boredom is the entry point and fear is downstream of it, what the four layers being sold actually are, why everyone else is fighting for *less* screen time while nobody sells it back. Competitive gaps, the beachhead, and a four-phase validation plan with numeric stop/continue thresholds.

**[requirements.md](docs/product/requirements.md) — what does it do?** The spec. Principles, personas, and the core loop from recall through shipping to the weekly time mirror. Then the numbered `FR-`/`NFR-` requirements, the measurement model, pilot thresholds, safeguarding obligations for the 16–18 segment, and seven open questions.

**[initial-design.md](docs/product/initial-design.md) — how would it be built?** Screens down to actual copy, the domain model, mission generation with distribution as a first-class mission kind, the audience ladder, privacy, testing, and the build order. Named "initial" deliberately — the principles should survive, the schema is a starting position to be challenged.

**Also:** [the BMAD path](docs/method/bmad-path.md) for how this gets built · [the decision log](docs/log/decision-log.md) for why it looks like this, including what was tried and dropped · [future plans](docs/roadmap/future-plans.md) for what's deferred and what's refused.

## Licence

[MIT](LICENSE).
