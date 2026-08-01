# Freathe

### You didn't waste four hours last night. You spent them. You just don't have anything to show for it.

That's the whole difference, and it's the only one this product cares about.

Time in flow disappears. Time spent scrolling drags *and* leaves a residue — the specific feeling, at midnight, that the evening went somewhere and you can't say where. Same clock. Opposite relationship to it.

**Generic apps took the control. This gives it back.**

## How it works

You open it. There's one thing to do, already on the screen.

No sign-up. No questionnaire. Nothing asking what your goals are or how much time you've got — because you don't know, and being asked is where people stall. Just something small and specific, with a clear finish.

You do it. It's saved. If you want another, it's right there.

Within three days you'll have made something and put it in front of a real person, and a real person will have responded — that part is guaranteed, not hoped for. At the end of the week it shows you what you made. Not what you missed.

## What it won't do

It won't make you happy, and it won't make you money. Anything promising either is selling something.

It won't make boredom go away, either. When the scrolling stops, boredom shows up undiluted — that's not a bug in the product, it's the point. Boredom is a signal to go and do something else. The apps have just been intercepting the signal before it reaches you.

And it won't set you a deadline, count your streak, hand you a curriculum, or write anything for you. Everything it shows you, you made.

## Why not the alternatives

**Blockers** close the app and hand you back an empty fifteen minutes. They cut the loop where cutting is easiest — but removing something propagates nowhere, so you get the boredom back with nothing to fill it, and you'll bypass them by Thursday.

**Courses** hand you someone else's plan, which is exactly what makes them inert.

**Task managers** hand you back the backlog you already had.

**AI assistants** hand you a finished thing you can't defend when someone asks about it.

This cuts at the one link where cutting propagates: *not making anything*. Make something, and confidence follows; confidence follows, and the fear loses its footing; and *"I'm just lazy"* — the verdict at the end of the chain that explains away every future evening — runs out of evidence.

That's the wager. It's falsifiable, and the plan to falsify it is written down.

---

## Current state — planning, pre-code

**There is no software yet. This repository is a product thesis.**

Written: the market case, the requirements, an initial design, and the build method. Next: a cohort run entirely by hand, with predictions committed to git *before* it starts. Then a first release, then reach, then institutional pilots.

Nobody has used this. Every number here is a hypothesis with a threshold attached, and [demand](docs/product/demand.md) §8 states what evidence would kill it.

Four things aren't known:

- whether reclaimed time is something people will pay for, or only something they feel;
- whether a first ship gets a response or silence — silence being the internet's default;
- how big that response has to be before it changes how someone sees themselves;
- whether this reaches the genuinely stuck, or only the already-motivated.

And one that can't be known yet: the first cohort runs unpaid, so nothing it produces will be evidence that anyone will buy this ([D-018](docs/log/decision-log.md)).

## The documents

**[demand.md](docs/product/demand.md) — should this exist?** The market case. Why boredom is the entry point and fear is downstream of it; the four layers being sold and which two are ever spoken aloud; why everyone else fights for *less* screen time while nobody sells it back. Competitive gaps, the beachhead, and a four-phase validation plan with numeric stop/continue thresholds.

**[requirements.md](docs/product/requirements.md) — what does it do?** Eight principles, the mechanics, and the numbered `FR-`/`NFR-` requirements. Plus the measurement model, pilot thresholds, safeguarding obligations for the 16–18 segment, and the open questions left to real users rather than argument.

**[initial-design.md](docs/product/initial-design.md) — how would it be built?** Screens down to actual copy, the domain model in prose, mission generation, the audience ladder, privacy, failure modes, and eight rejected alternatives with the reasons. Named "initial" on purpose — the principles should survive, the rest is a starting position to be challenged.

**Also:** [the BMAD path](docs/method/bmad-path.md) for how this gets built · [the decision log](docs/log/decision-log.md) for why it looks like this, including what was tried and thrown out · [future plans](docs/roadmap/future-plans.md) for what's deferred and what's refused outright.

## Licence

[MIT](LICENSE).
