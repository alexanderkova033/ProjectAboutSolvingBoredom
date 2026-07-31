# ForgePath

*Placeholder name. A real one gets chosen before the first paid cohort — see [D-015](docs/log/decision-log.md).*

**Turn unused time into proof of what you can do.**

A 30-day project sprint. You pick one real project. Each day it gives you a single mission sized to the time you actually have — five minutes or an hour — with one clear definition of done. You do the work, record the evidence, show it to a crew of four to six people doing the same. At the end you have a finished, shareable proof-of-work page: the artifact, how you made it, what broke, what you learned.

No feed. No follower counts. No streak guilt. No AI writing your project for you.

## Why this and not the alternatives

Blockers close the app and leave you with an empty fifteen minutes. Courses hand you someone else's project. Task managers hand you back the backlog you already had. AI assistants hand you a finished draft you can't defend in an interview.

The wager: confidence comes from evidence of mastery, and purpose emerges from work you chose and finished. Neither can be sold directly — but the conditions for both can be designed.

## Current state — planning, pre-code

**There is no software yet. This repository is a product thesis.**

Written: the market case, the MVP requirements, an initial design, and the build method. Next: a paid cohort run entirely by hand — forms, a spreadsheet, hand-written missions. Only then a solo MVP, then crews, then institutional pilots.

Nobody has paid for this. No user has completed a project. Every number in these documents is a hypothesis with a threshold attached, and [demand](docs/product/demand.md) §9 states what evidence would kill the idea.

Three assumptions carry the whole thesis, and none is tested:

- that people defined by not finishing things will finish this one;
- that the artifact is credible to someone doing the hiring;
- that a sprint helps the genuinely stuck, not just the already-motivated.

The next step is deliberately not code. A well-structured specification built on untested assumptions is harder to abandon than a messy one.

## The documents

**[demand.md](docs/product/demand.md) — should this exist?** The market case. Argues that boredom is a frequent pain nobody pays to fix while portfolio completion is an urgent one people do, so boredom becomes the hook and completion the product. Scores six adjacent opportunities, maps the gaps left by blockers, coworking, bootcamps and AI coaches, sizes the market bottom-up, and sets a four-phase validation plan with numeric stop/continue thresholds.

**[requirements.md](docs/product/requirements.md) — what does it do?** The MVP spec. Personas, the seven-step loop, hard non-goals, and every user flow from onboarding through the daily mission to completion. Then ~40 numbered `FR-` requirements and 10 `NFR-`s, the measurement model, pilot thresholds, monetisation hypotheses, safety rules, and seven open questions left to paid pilots rather than argument.

**[initial-design.md](docs/product/initial-design.md) — how would it be built?** The first design position: seven principles, five product surfaces, key screens down to actual copy. Then the engineering draft — stack, domain model, mission-generation engine with its difficulty logic, progress dimensions, crew matching, moderation and privacy architecture, API outline, delivery phases. Named "initial" deliberately: the principles should survive, the schema is a starting position to be challenged.

**Also:** [the BMAD path](docs/method/bmad-path.md) for how this gets built, [the decision log](docs/log/decision-log.md) for why it looks like this, [future plans](docs/roadmap/future-plans.md) for what's deferred and what's refused.

## Licence

[MIT](LICENSE).
