# Decision Log and Work Log

**Product:** ForgePath (working title) · **Living document — append only**

> **Related:** [Demand](../product/demand.md) · [Requirements](../product/requirements.md) · [Initial design](../product/initial-design.md) · [BMAD path](../method/bmad-path.md) · [Future plans](../roadmap/future-plans.md)

A decision belongs here if someone joining the project would otherwise ask "why is it like this?" Reversed decisions get marked `Superseded`, never deleted — the entries that turn out wrong are the ones worth keeping. `Provisional` means deliberately revisitable, usually pending evidence.

## Decisions

| # | Decision | Why | Status |
|---|---|---|---|
| **D-001** | Sell project completion, not boredom relief | Boredom is high-frequency but scores 2.4/5 on willingness to pay; portfolio completion scores 4.2/5 because a job market forces the issue. Boredom stays the hook, never the purchase reason. | Accepted |
| **D-002** | Beachhead is 18–26 in transition to work | Narrow enough to write copy for, large enough to matter, reachable through institutions that already budget for this outcome. Removes under-18 safeguarding from MVP scope. | Accepted |
| **D-003** | Bounded 30-day purchase before any subscription | The buyer must know exactly what they bought. Subscription apps churn on trial day one, and AI-branded ones retain worst of all. | Provisional — membership pricing is live once completion data exists |
| **D-004** | No clinical claims, no shame mechanics | Ethical and regulatory, but mostly product integrity: a completion product leaning on guilt produces compliance, not the mastery it sells. | Accepted |
| **D-005** | AI decomposes and critiques; never authors the artifact | The artifact's whole value is being defensible in an interview. An AI-written portfolio piece fails exactly when examined. | Accepted |
| **D-006** | Every AI path ships a non-AI fallback | A daily loop can't break on a provider outage at day 9 of 30. Makes manual template authoring implementation priority #1. | Accepted |
| **D-007** | Web-first responsive; no native apps, no app blocking in MVP | Blocking is crowded and isn't the differentiator — what appears *after* the block is. Native adds store review and platform cost before the hypothesis is tested. | Accepted |
| **D-008** | No public feed or follower counts; crews of 4–6 | A feed creates the comparison pressure that stops the target user publishing in the first place. Costs us conventional social growth loops; accepted. | Accepted |
| **D-009** | Five transparent progress dimensions, never one score | A composite score is unfalsifiable, invites comparison, and drifts toward measuring the person. Raw counts can be argued with, which makes them trustworthy. | Accepted |
| **D-010** | Concierge test before installing BMAD | Planning-phase efficiency works against us on unvalidated assumptions — it produces a well-organised spec that's harder to abandon. Repo stays docs-only meanwhile; that's the intended state. | Accepted |
| **D-011** | Docs-only repo, domain-named folders; `DESIGN.md` → `initial-design.md` | The rename is the substantive part: "design" implied a settled architecture, "initial design" states its real status. | Accepted |
| **D-012** | MIT licence | Permissive and frictionless while the asset is a market thesis rather than code. | Provisional — revisit **before** the first outside contribution if the commercial model comes to rest on the platform code |

## Work log

**31 July 2026 — Repository structured for BMAD.** Reorganised into `docs/{product,method,roadmap,log}`, renamed the design document, marked in each product doc which BMAD artifact supersedes it. Fixed a stale section: initial design §6 described a repo structure listing root-level files that no longer exist there.

Three of the seven open questions in requirements §15 block the concierge design: which project category to start with, whether crews form at onboarding or after the first mission, and how much facilitation completion actually requires.

**31 July 2026 — Initial documentation committed.** Demand thesis, requirements, design spec. Beachhead selected over five alternatives. Not built, not tested, not sold.
