# ForgePath

**Turn unused time into proof of what you can do.**

Most people who feel stuck do not need more content, more motivation, or a better app blocker. They need one small next action, someone who notices whether they did it, and something to show at the end.

ForgePath is a 30-day project sprint. You pick one real project. Each day it gives you a single mission sized to the time you actually have — five minutes or an hour — with one clear definition of done. You do the work, record the evidence, and post it to a crew of four to six people doing the same thing. At the end you have a finished, shareable proof-of-work page: the artifact, how you made it, what broke, and what you learned.

No feed. No follower counts. No streak guilt. No AI writing your project for you.

## Why this and not the alternatives

| | What it gives you | What it leaves you with |
|---|---|---|
| Screen-time blockers | The app is closed | An empty fifteen minutes |
| Courses and bootcamps | Knowledge and a certificate | Someone else's project |
| Task managers | A place to put tasks | A backlog you already had |
| AI assistants | A finished draft | Work you cannot defend in an interview |
| **ForgePath** | **One mission at a time, and a crew that notices** | **A project you made, and can talk about** |

The wager is simple: confidence comes from evidence of mastery, and purpose emerges from work you chose and finished. Neither can be delivered directly — but the conditions for both can be designed.

## Current state — planning, pre-code

**There is no software yet. This repository is a product thesis, not a product.**

That is deliberate, and here is the honest version of where things stand:

- ✅ **Market thesis** — researched and written, with sources and explicitly labelled hypotheses
- ✅ **MVP requirements** — specified down to numbered functional and non-functional requirements
- ✅ **Initial design** — screens, domain model, mission-generation rules, safety architecture
- ✅ **Build method chosen** — this project runs on [BMAD](docs/method/bmad-path.md)
- ⬜ **Concierge test** — a manual, paid, 30-day cohort. **This is the next step.**
- ⬜ **Solo MVP** — built via BMAD, only after the concierge test produces real data
- ⬜ **Crews, institutional pilots, personalisation** — later phases

Nobody has paid for this yet. No user has completed a project. Every completion and conversion number in these documents is a hypothesis with a threshold attached, and the [demand document](docs/product/demand.md) §9 says exactly what evidence would kill the idea.

The next step is not writing code. It is running a paid cohort by hand — forms, a spreadsheet, and hand-written missions — because a well-structured specification built on untested assumptions is harder to abandon than a messy one.

## The documents

### [demand.md](docs/product/demand.md) — should this exist?

The market case. Argues that boredom is a high-frequency pain nobody pays to fix, while portfolio completion is a lower-frequency pain people pay for urgently — so boredom becomes the hook and completion becomes the product. Scores six adjacent opportunities against each other and picks the youth portfolio sprint, maps the gaps left by blockers, coworking, bootcamps and AI coaches, sizes the market bottom-up rather than top-down, and sets a four-phase validation plan with explicit numeric thresholds for continuing or stopping. Ends with seven risks and their mitigations.

### [requirements.md](docs/product/requirements.md) — what does it do?

The MVP specification. Three personas plus the institutional buyer, the seven-step product loop, and a hard list of non-goals. Walks every user flow — onboarding, the daily five/fifteen/thirty/sixty-minute mission, evidence capture with predicted-versus-actual discomfort, crew posts, weekly review, completion. Then roughly forty numbered `FR-` requirements and ten `NFR-`s, the behavioural measurement model, activation and completion thresholds the pilot must hit, monetisation hypotheses, the safety and ethics rules, and seven open questions to be settled by paid pilots rather than argument.

### [initial-design.md](docs/product/initial-design.md) — how would it be built?

The first design position. Seven principles, a five-surface information architecture, and the key screens written down to actual copy. Then the engineering draft: recommended stack, the TypeScript domain model, the mission-generation engine with its quality rules and difficulty-adaptation logic, the five transparent progress dimensions, the crew matching formula, moderation and privacy architecture, analytics events, API outline, testing strategy, and five delivery phases.

Named "initial" deliberately. The principles and screen model should survive; the stack and schema are a starting position the BMAD Architect is expected to challenge.

## Licence

[MIT](LICENSE).
