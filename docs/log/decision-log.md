# Decision Log and Work Log

**Product:** ForgePath *(placeholder name — to be replaced)* · **Living document — append only**

> **Related:** [Demand](../product/demand.md) · [Requirements](../product/requirements.md) · [Initial design](../product/initial-design.md) · [BMAD path](../method/bmad-path.md) · [Future plans](../roadmap/future-plans.md)

A decision belongs here if someone joining would otherwise ask "why is it like this?" Reversed decisions get marked `Superseded`, never deleted — the entries that turn out wrong are the ones worth keeping. `Provisional` means deliberately revisitable, pending evidence.

## Decisions

| # | Decision | Why | Status |
|---|---|---|---|
| **D-001** | Sell project completion, not boredom relief | Boredom is frequent but scores 2.4/5 on willingness to pay; portfolio completion scores 4.2/5 because a job market forces the issue. Boredom stays the hook, never the purchase reason. | Accepted |
| **D-002** | Beachhead is 18–26 in transition to work | Narrow enough to write copy for, large enough to matter, reachable through institutions that already budget for this outcome. Removes under-18 safeguarding from scope. | Accepted |
| **D-003** | Bounded 30-day purchase before any subscription | The buyer must know exactly what they bought. Subscription apps churn on trial day one; AI-branded ones retain worst. | Provisional — membership pricing revisits once completion data exists |
| **D-004** | No clinical claims, no shame mechanics | Ethical and regulatory, but mostly integrity: a completion product leaning on guilt produces compliance, not the mastery it sells. | Accepted |
| **D-005** | AI decomposes and critiques; never authors the artifact | The artifact's whole value is being defensible in an interview. Every competitor will offer to just make the thing — refusing is a deliberate conversion cost, not an obvious call, and will be re-proposed. | Accepted as a cost |
| **D-006** | Every AI path ships a non-AI fallback | A daily loop can't break on a provider outage at day 9 of 30. Makes manual template authoring implementation priority #1. | Accepted |
| **D-007** | Web-first responsive; no native apps, no app blocking | Blocking is crowded and isn't the differentiator — what appears *after* the block is. Native adds store review and platform cost pre-validation. | Accepted |
| **D-008** | No public feed or follower counts; crews of 4–6 | A feed creates the comparison pressure that stops the target user publishing at all. Costs us conventional social growth loops. | Accepted |
| **D-009** | Five transparent progress dimensions, never one score | A composite score is unfalsifiable, invites comparison, and drifts toward measuring the person. Raw counts can be argued with, which makes them trustworthy. | Accepted |
| **D-010** | Concierge test before installing BMAD | Planning-phase efficiency works against us on unvalidated assumptions — it yields a well-organised spec that's harder to abandon. Repo stays docs-only meanwhile; intended, not stalled. | Accepted |
| **D-011** | Docs-only repo, domain-named folders; `DESIGN.md` → `initial-design.md` | The rename is the substantive part: "design" implied a settled architecture, "initial design" states its real status. | Accepted |
| **D-012** | MIT licence | Permissive and frictionless while the asset is a market thesis rather than code. | Provisional — revisit **before** the first outside contribution if the commercial model comes to rest on platform code |
| **D-013** | Solo MVP ships alone; crews are a later release | Crews are the largest source of scope, risk and cold-start difficulty. Shipping them with the core loop makes it impossible to tell which one failed. Resolves a contradiction between requirements §14 and design §19 in favour of §19. | Accepted |
| **D-014** | Hand-pick the first crews; don't build matching | Matching solves a liquidity problem we don't have. The replacement-of-inactives rule assumes a bench of spare users that only exists at scale. | Accepted |
| **D-015** | Name deferred — "ForgePath" is a placeholder nobody is happy with | Naming ahead of validation locks a name to positioning that may still move; the concierge cohort will also supply the vocabulary users actually use for this. Renaming costs ~12 string replacements today, so deferring is close to free — but that cost rises the moment a domain, logo, or payment account exists. | Open — decide before the first paid cohort |

## Open risks

Not decisions — the assumptions everything rests on, none tested. Each needs an owner and an answer before Step 1.

| Risk | Why it's load-bearing |
|---|---|
| **Completion rate** | The 30% target carries the entire pitch. Self-directed programs typically complete far lower; Buildspace had huge energy, was free, and closed. Someone who doesn't finish has paid to be reminded they don't finish — worse than never buying. |
| **Artifact credibility** | The whole value chain terminates in employers valuing proof of work. Asserted throughout, verified nowhere. If false, this is a motivation product with better marketing. |
| **Who it's actually for** | The idle moment is a low-executive-function state. The sprint may serve the moderately motivated — already served by Focusmate and a to-do list — and fail the genuinely stuck, who are the stated market. *Who fails without this and succeeds with it?* |
| **Payer mismatch** | Users have time and no money; institutions have money and 6–18 month sales cycles needing evidence that requires users first. B2C may be a loss-leader that exists to generate the B2B case study. If so, say it, because it changes how much B2C unit economics matter. |

## Work log

**31 July 2026 — Repository structured for BMAD.** Reorganised into `docs/{product,method,roadmap,log}`, renamed the design document, marked which BMAD artifact supersedes each product doc. Fixed two stale sections: initial design §6 described a repo structure listing root-level files that no longer exist, and requirements §14 bundled crews and cohort admin into a "first release" that contradicted design §19.

Three of the seven open questions in requirements §15 block the concierge design: which project category to start with, whether crews form at onboarding or after the first mission, and how much facilitation completion actually requires.

**31 July 2026 — Initial documentation committed.** Demand thesis, requirements, design spec. Beachhead selected over five alternatives. Not built, not tested, not sold.
