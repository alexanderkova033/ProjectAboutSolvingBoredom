# Freathe

### You didn't waste four hours last night. You spent them. You just don't have anything to show for it.

That's the whole difference, and it's the only one this product cares about.

Time in flow disappears. Time spent scrolling drags *and* leaves a residue — the specific feeling, at midnight, that the evening went somewhere and you can't say where. Same clock. Opposite relationship to it.

**Generic apps took the control. This gives it back.**

## How it works

There's one thing to do, and it's on the first screen your phone unlocks to. Not an app you go and find — something you put there yourself, on the page the evening was about to go to anyway. One tap, and the thing to do is in front of you, already chosen.

No sign-up. No questionnaire. Nothing asking what your goals are or how much time you've got — because you don't know, and being asked is where people stall. Just something small and specific, with a clear finish.

You do it. It's saved. If you want another, it's right there.

Three days in, something you made is in front of a real person and a real person has answered — that part is guaranteed, not hoped for. At the end of the week it shows you what you made. Not what you missed.

The thing on your phone catches the moment; the laptop is where it actually gets made. It only asks you to sign in once you've finished something and there's work worth keeping.

## Discipline isn't the mechanism

You're free to do whatever you want. You're just not free of the consequences.

Discipline is force applied against what you actually want, and force runs out — usually on a Tuesday. So nothing here is scheduled, owed, or required. You can drop any task, stop mid-sentence, and close it without a dialog box asking whether you're sure. That's the point, not politeness: knowing you can leave at any second is what makes starting cheap.

What's left when you take the obligation out is the consequence — and only the half you can't already see. You don't need telling that last night went nowhere; you were there. You do need telling that you came back to this on seven different days, because nobody has ever counted.

## What it won't do

It won't make you happy, and it won't make you money. Anything promising either is selling something.

It won't make boredom go away, either. When the scrolling stops, boredom shows up undiluted — that's not a bug, it's the point. Boredom is a signal to go and do something else. The apps have just been intercepting the signal before it reaches you.

And it won't count your streak, hand you a curriculum, or write anything for you. Everything it shows you, you made.

## Why not the alternatives

**Blockers** close the app and hand you back an empty fifteen minutes. They cut the loop where cutting is easiest — but removing something propagates nowhere, so you get the boredom back with nothing to fill it, and you'll bypass them by Thursday.

**Courses** hand you someone else's plan, which is exactly what makes them inert. **Task managers** hand you back the backlog you already had. **AI assistants** hand you a finished thing you can't defend when someone asks about it.

This cuts at the one link where cutting propagates: *not making anything*. Make something, and confidence follows; confidence follows, and the fear loses its footing; and *"I'm just lazy"* — the verdict that explains away every future evening — runs out of evidence.

That's the wager. It's falsifiable, and the plan to falsify it is written down.

---

## Current state — stopped

**This will not be built** ([D-062](docs/log/decision-log.md)). Everything above describes a product that does not exist and now won't. No software was ever written.

It wasn't the market case that killed it — [demand](docs/product/demand.md) §8 was never run, so nothing here gets to be read as its result. It stopped on noticing what it was *for*. The project started after watching a video essay, from a real urge to make some contribution, and that urge was then handed to a personal statement to carry. A thing that has to be impressive before it's allowed to be real gets planned instead of made, and 62 decisions with nothing built is what that looks like from the inside. The documents ban exactly this mechanic four screens deep in the product ([D-024](docs/log/decision-log.md)) while it operated on the project from the outside the whole time.

**What survives is the writing** ([D-063](docs/log/decision-log.md)). The strongest idea here never needed software to be true: *"I'm just lazy"* is the last link in the chain, and it's a **verdict rather than a cause** — the only link phrased as an identity, which is what makes it a stable loop rather than a bad week ([D-027](docs/log/decision-log.md)). That, the argument against blockers, and the rule that only the consequence you *can't already see* is worth showing anyone, are an essay. They were always an essay.

Nobody ever used this. Every number in these files is a hypothesis with a threshold attached, and not one threshold was tested.

Five things were never found out, in order of how much damage each would have done:

- **where anyone encounters this at all.** Nobody searches for it, so there's no channel to buy — only the places people describe the problem in their own words ([D-044](docs/log/decision-log.md));
- whether anything brings a person back once the first thing is finished. Every conventional retention trick is banned here on purpose, which leaves one candidate: the response ([D-042](docs/log/decision-log.md)). what sits on the home screen is a *surface*, not a reason — put it on the first page and it's seen every unlock, which removes the excuse of having forgotten and supplies no motive whatsoever ([D-049](docs/log/decision-log.md), [D-061](docs/log/decision-log.md));
- whether a first ship gets a response or silence — silence being the internet's default;
- how big that response has to be before it changes how someone sees themselves;
- whether anyone funds it. That the user is not the payer is settled ([D-060](docs/log/decision-log.md)), which moves the question rather than answering it: a funder wants the same evidence a school does, on the same slow cycles, and there is still no fundable unit — completion was deliberately deleted and can't be the thing anyone buys ([D-050](docs/log/decision-log.md)).

And three that couldn't have been, all downstream of the founder being 15: the first cohort runs unpaid, so nothing it produces is evidence anyone will fund this ([D-018](docs/log/decision-log.md)); it runs adults-only, because a minor can't be the responsible adult a minor cohort requires — which closes the one channel that came with real access ([D-046](docs/log/decision-log.md)); and every account that could receive money opens in 2029, including a charity's, since trustees are adults too ([D-058](docs/log/decision-log.md), [D-060](docs/log/decision-log.md)).

There was also nobody to dogfood it. The founder is below the product's own minimum age, so every claim here about how a session *feels* is reasoned rather than felt — which, in the end, was true of the whole thing.

## The documents

**[demand.md](docs/product/demand.md) — should this exist?** The market case. Why boredom is the entry point and fear is downstream of it; the four layers being sold and which two are ever spoken aloud; why everyone else fights for *less* screen time while nobody sells it back. Competitive gaps, the beachhead, the distribution problem and its three channel bets, and a four-phase validation plan with numeric stop/continue thresholds.

**[requirements.md](docs/product/requirements.md) — what does it do?** Eight principles, the mechanics, and the numbered `FR-`/`NFR-` requirements. Plus the measurement model, pilot thresholds, safeguarding obligations, and the open questions left to real users rather than argument.

**[initial-design.md](docs/product/initial-design.md) — how would it be built?** Screens down to actual copy, the domain model in prose, mission generation, the audience ladder, privacy, and failure modes. Named "initial" on purpose — the principles should survive, the rest is a starting position to be challenged.

**Also:** [the BMAD path](docs/method/bmad-path.md) for how this gets built · [the decision log](docs/log/decision-log.md) for why it looks like this, including what was tried and thrown out · [future plans](docs/roadmap/future-plans.md) for what's deferred and what's refused outright.

## Licence

[MIT](LICENSE).
