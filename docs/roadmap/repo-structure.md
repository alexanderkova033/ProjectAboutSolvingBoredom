# Repository Structure

**Product:** Freathe · **Status:** Plan for code that does not exist yet

> **Related:** [Initial design](../product/initial-design.md) · [BMAD path](../method/bmad-path.md) · [Future plans](future-plans.md) · [Decision log](../log/decision-log.md)

No application code exists. The repository holds documentation only. This file records how the tree should look when code arrives, so the decision isn't re-litigated during the first sprint.

## Principle

The top level should scream the domain. A reader should see what the product *does* before they see which framework it uses. Route and component folders take their names from the product surfaces in [initial design](../product/initial-design.md) §3.1; `lib/` splits by domain capability, not by technical layer.

```text
/
├── README.md
├── LICENSE
├── docs/                      # exists today
│   ├── product/               # demand, requirements, initial design
│   ├── method/                # bmad-path
│   ├── roadmap/               # future-plans, repo-structure
│   └── log/                   # decision-log
│
├── app/                       # arrives with the solo MVP
│   ├── (auth)/
│   ├── onboarding/
│   ├── now/                   # the mission surface
│   ├── projects/
│   ├── evidence/
│   ├── receipt/               # proof-of-work by-product
│   └── api/
├── components/
│   ├── missions/
│   ├── projects/
│   ├── evidence/
│   └── ui/
├── lib/
│   ├── ai/                    # generation + schema validation
│   ├── analytics/
│   ├── auth/
│   ├── db/
│   ├── entitlement/           # the payments seam — answers yes to everything
│   ├── moderation/
│   ├── record/                # authored hours, ships, responses
│   └── validation/
├── prompts/
├── public/
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
│
└── missions/                  # the template library, as data
```

`crews/` and `matching/` are absent deliberately — crews are a later release ([D-013](../log/decision-log.md)) and matching is deferred past that ([D-014](../log/decision-log.md)). Add those folders when the work is real, not in anticipation.

`entitlement/` is the one exception, and it earns it by being the opposite of a feature ([D-053](../log/decision-log.md)). Money is parked, not cancelled ([future plans](future-plans.md)), and what makes payments expensive to retrofit is never the provider — it is the fifty call sites that should have asked *is this allowed* and simply did. So the rule is: **no surface ever decides for itself what a user may do.** It asks here, and here says yes to everything. A paid tier later is one implementation change instead of an audit. There is no billing table, no plan model, and no provider integration until there is something to sell — the folder holds a question, not a product.

## One client, two shapes

There is no `android/`, and there was nearly ([D-052](../log/decision-log.md), withdrawn by [D-059](../log/decision-log.md)). The phone and the laptop are the same web application at two widths, installed to a home screen at the narrow end.

**`missions/` is a top-level data directory anyway**, and the reason survived the reversal. The template library is what the mission loop degrades to when the model is unavailable (`FR-024`) *and* what the phone renders from when the network is (`FR-055`), so it is read by the server, the client, and the offline cache. Templates were already first in the build order because everything degrades to them ([initial design](../product/initial-design.md) §7); keeping them as data rather than as an implementation detail of one layer is what makes that structural instead of intentional.

## The one load-bearing decision

`record`, `moderation`, and `ai` are where this product's actual rules live. They must stay testable without a browser or a database — the AI evaluation set in [initial design](../product/initial-design.md) §4.5 depends on running hundreds of project states through mission generation as plain function calls.

The sibling SapGlance repo reached the identical constraint from the other direction: its selection engine sits in a module with zero Android imports so it runs on a plain JVM, and that split turned out to be exactly the seam a platform port needs. Two products, two justifications, one rule — **the domain logic never imports the surface.** Worth keeping in view here, because the surface just changed once already ([D-059](../log/decision-log.md)) and code that had imported it would have gone with it.

`record` was called `scoring` until this pass, which was wrong in a way worth keeping visible: nothing in this product is scored ([D-009](../log/decision-log.md), `FR-034`), and a folder named for the banned thing is where the banned thing eventually gets written.
