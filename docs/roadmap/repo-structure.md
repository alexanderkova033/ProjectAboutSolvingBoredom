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
│   ├── moderation/
│   ├── record/                # authored hours, ships, responses
│   └── validation/
├── prompts/
├── public/
└── tests/
    ├── unit/
    ├── integration/
    └── e2e/
```

`crews/` and `matching/` are absent deliberately — crews are a later release ([D-013](../log/decision-log.md)) and matching is deferred past that ([D-014](../log/decision-log.md)). Add those folders when the work is real, not in anticipation.

## The one load-bearing decision

`record`, `moderation`, and `ai` are where this product's actual rules live. They must stay testable without a browser or a database — the AI evaluation set in [initial design](../product/initial-design.md) §4.5 depends on running hundreds of project states through mission generation as plain function calls.

`record` was called `scoring` until this pass, which was wrong in a way worth keeping visible: nothing in this product is scored ([D-009](../log/decision-log.md), `FR-034`), and a folder named for the banned thing is where the banned thing eventually gets written.
