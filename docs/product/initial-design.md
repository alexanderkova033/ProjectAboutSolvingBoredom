# Initial Product and Technical Design

**Product:** ForgePath *(placeholder name — to be replaced)*  
**Document status:** Initial design — a starting position, not a ratified architecture  
**BMAD stage:** Pre-BMAD input, feeds the UX Expert spec and the Architect run  
**Superseded by:** `docs/product/architecture.md` once the BMAD Architect run produces it  
**Research snapshot:** 31 July 2026

> **Related:** [Demand](demand.md) · [Requirements](requirements.md) · [BMAD path](../method/bmad-path.md) · [Repo structure](../roadmap/repo-structure.md) · [Decision log](../log/decision-log.md)

> **Why "initial":** written before any code, user test, or BMAD run. §1–4 (principles, architecture, screens) are the durable part. §5–15 (stack, schema, engine, API) are a defensible first draft the Architect is expected to challenge and replace — evidence the domain has been thought through, not a migration target.

## 1. Design objective

A mobile-first web product that converts an idle moment into one small production action, and accumulates those actions into a completed proof-of-work project.

It should feel simpler than a task manager, more active than a course, safer than a public social network, and more outcome-oriented than a generic AI coach.

## 2. Core principles

1. **One next action.** The default screen shows the project, progress, and one clear next mission — never a backlog.
2. **Production before consumption.** Minimum context required to act. Advice ends in an observable action.
3. **The user decides; the product proposes.** The user picks the project, the scope, and the finish line. Every system suggestion is a default with a visible override. Boredom is failed engagement — handing the user someone else's plan reproduces what makes courses inert.
4. **Purpose through evidence.** Don't ask for a declared purpose. Help users notice what they repeatedly choose, improve, and finish.
5. **Confidence through graded mastery.** Increase challenge gradually. Record predictions against outcomes. Reward attempts and revisions, not only polish.
6. **Small recurring social units.** Crews stable enough for familiarity, small enough to prevent a feed economy.
7. **Transparent measurement.** Raw behaviour and clear calculations. No mysterious score, no diagnosis.
8. **AI as scaffolding.** AI may decompose, adapt, question, critique, summarise. It never becomes the creator of record.

## 3. Information architecture

**Today** — time-available selector, current mission, mission controls, brief progress, optional crew pulse, no scrolling feed.  
**Project** — outcome and definition of done, stages and milestones, artifact links, scope adjustment, proof-of-work builder.  
**Crew** — bounded chronological updates, structured feedback requests, session info, norms and reporting.  
**Evidence** — mission history, attachments, predicted versus actual outcomes, skills demonstrated, weekly summaries.  
**Profile** — schedule, interests, skills, privacy, notifications, data export and deletion.

Administrators get a separate **Cohort** area.

## 4. Key screens

**Welcome.** Headline: *Turn unused time into proof of what you can do.* Primary action: *Start a project.* Supporting: one real project · one small mission at a time · one crew · a shareable result.

**Outcome selection.** *What would you like to have finished?* — a portfolio project · something creative I publish · evidence of a new skill · momentum after a stuck period · exploration of a possible career.

**Project selection.** A small curated library, bounded and artifact-based. First templates: publish a researched explainer · build and test a simple web tool · design a small product concept · create a local problem-and-solution report · produce a short visual or audio story · run a tiny service experiment for a real person or organisation. Each carries target artifact, examples, required stages, expected weekly time, skills, difficulty, and suitability constraints.

**Scope and finish line.** The user names their own definition of done and target date. The system shows what that implies — *that's about 4 hours a week for 6 weeks* — and flags an inconsistency with stated availability without blocking it. Users who want a suggestion get one; it is a default, not a container.

**Baseline.** Under three minutes: project experience, available days and minutes, confidence finishing this kind of project, recent unfinished projects, main blocker, comfort showing unfinished work, desired final visibility.

**Today.** In order: project title and day number · *how much time do you have?* · mission card · accept / easier / different / blocker · progress strip · crew pulse.

> **Create a rough problem statement**  
> Write 100–150 words describing who experiences the problem, when it happens, and what they currently do instead.  
> **Done when:** a draft is saved to your project, even if the wording is poor. **Time:** 15 min. **Difficulty:** 2/5

**Mission completion.** Did you attempt it? Is the definition of done satisfied? Attach evidence. What happened? Optionally predicted versus actual discomfort. What next? Immediately show: mission complete, artifact progress changed, evidence added, next action previewed.

**Crew update.** Fixed format — *Today I made: … / I am stuck on: … / Feedback I need: [none, clarity, usefulness, technical, visual]*. Feedback prompts guide quality: "I understood…", "I was confused by…", "The most useful part is…", "One small next test could be…".

**Weekly review.** Evidence-based summary — *You planned 5 production days and produced on 4. You completed 7 missions and revised 3 artifacts. Your average predicted discomfort was 7.1; actual was 4.8. You avoided publishing twice. Your crew responded to 4 of your updates.* Then one decision: increase challenge, hold, or reduce scope.

**Completion page.** Title, one-sentence outcome, problem or purpose, final artifact, the user's contribution, process timeline, tests or feedback, revisions, skills demonstrated, tools used including AI, reflection, and visibility control.

## 5. Implementation stack

A pragmatic recommendation, not a requirement.

**Frontend:** Next.js (App Router), TypeScript, React, Tailwind, accessible primitives (Radix or shadcn/ui), React Hook Form with Zod.

**Backend, option A (fastest):** Next.js server actions and route handlers, Supabase Postgres, Auth, and Storage, with Row-Level Security. **Option B (more portable):** Next.js, PostgreSQL, Prisma or Drizzle, Auth.js, S3-compatible storage.

**AI layer:** provider-agnostic interface, structured JSON output, schema validation, prompt and model version logging, rate and cost limits, non-AI template fallback.

**Infrastructure:** Vercel or equivalent, managed PostgreSQL, error monitoring, privacy-conscious analytics, transactional email, optional queue for summaries and matching.

Code layout is in [repo-structure.md](../roadmap/repo-structure.md).

## 6. Domain model

```ts
type User = {
  id: string; email: string; createdAt: Date; timezone: string;
  locale: string; ageConfirmed: boolean;
  status: "active" | "suspended" | "deleted";
};

type Profile = {
  userId: string; displayName: string; bio?: string;
  interests: string[]; selfReportedSkills: string[];
  preferredSessionMinutes: number[]; availableWeekdays: number[];
  privacyDefault: "private" | "unlisted" | "public";
};

type ProjectStage =
  | "define" | "explore" | "build" | "test" | "revise" | "publish" | "reflect";

type Project = {
  id: string; ownerId: string; templateId?: string;
  title: string; outcome: string; audience?: string;
  artifactType: string; definitionOfDone: string;
  status: "draft" | "active" | "paused" | "completed" | "archived";
  currentStage: ProjectStage;
  startDate: Date;
  targetDate: Date;          // set by the user, revisable without penalty
  visibility: "private" | "unlisted" | "public";
};

type Mission = {
  id: string; projectId: string;
  source: "template" | "ai" | "facilitator" | "user";
  title: string; instruction: string; definitionOfDone: string;
  estimatedMinutes: 5 | 15 | 30 | 60;
  difficulty: 1 | 2 | 3 | 4 | 5;
  stage: ProjectStage;
  evidenceType: "text" | "url" | "image" | "file" | "external_action";
  status: "proposed" | "accepted" | "completed" | "skipped" | "expired";
  generatedAt: Date; acceptedAt?: Date; completedAt?: Date;
};

type MissionAttempt = {
  id: string; missionId: string; userId: string; attemptNumber: number;
  predictedDifficulty?: number; predictedDiscomfort?: number;
  predictedOutcome?: string; completionConfidence?: number;
  attempted: boolean; completed: boolean;
  actualDiscomfort?: number; actualOutcome?: string;
  recoveryMinutes?: number; blockerCode?: string;
  reflection?: string; createdAt: Date;
};

type Evidence = {
  id: string; projectId: string; missionId?: string; ownerId: string;
  type: "text" | "url" | "image" | "file";
  title: string; textContent?: string; url?: string; storagePath?: string;
  isPortfolioEligible: boolean;
  visibility: "private" | "crew" | "portfolio";
  createdAt: Date;
};

type Crew = {
  id: string; cohortId?: string; name: string; language: string;
  timezoneBand: string;
  status: "forming" | "active" | "completed" | "archived";
  capacity: number;
};

type CrewMember = {
  crewId: string; userId: string; role: "member" | "facilitator";
  joinedAt: Date; leftAt?: Date;
  notificationLevel: "all" | "digest" | "off";
};

type CrewPost = {
  id: string; crewId: string; authorId: string; projectId: string;
  evidenceId?: string; madeText: string; blockerText?: string;
  feedbackType?: "clarity" | "usefulness" | "technical" | "visual";
  status: "visible" | "reported" | "removed"; createdAt: Date;
};

type Cohort = {
  id: string; organizationId?: string; name: string; inviteCode: string;
  startDate: Date; endDate: Date;
  status: "draft" | "active" | "completed";
};
```

```text
User 1—1 Profile     Project 1—N Mission        Mission 1—N MissionAttempt
User 1—N Project     Project 1—N Evidence       Crew 1—N CrewPost
User N—N Crew (via CrewMember)                  Cohort 1—N Crew
```

Private reflections are stored separately or under stricter row-level policies than crew-visible evidence.

## 7. Mission generation

**Inputs:** template and definition of done, current stage, completed and skipped missions, remaining milestones, selected available time, self-reported energy, experience level, recent blockers, crew dependencies, existing evidence, safety category.

**Quality rules.** A mission must start with one observable verb, produce an artifact or external action, fit the requested duration, have a testable definition of done, advance the project, avoid combining independent tasks, avoid unnecessary research, avoid producing the user's final work for them, sit mostly at difficulty 2–4, and be safe and lawful.

> Bad: *Think about your target customer and improve your concept.*  
> Better: *Write three sentences describing one target customer, the moment the problem occurs, and what they currently do instead.*

**Structured output**, validated against a strict schema — two failures fall back to a template mission:

```json
{
  "title": "Write a one-person problem statement",
  "instruction": "Write 100–150 words describing one person, the moment the problem occurs, and their current workaround.",
  "definitionOfDone": "A draft is saved to the project, even if incomplete.",
  "estimatedMinutes": 15, "difficulty": 2,
  "stage": "define", "evidenceType": "text",
  "reason": "This creates the first testable project assumption.",
  "safetyFlags": []
}
```

**Difficulty adaptation** — change one variable at a time (duration, visibility, ambiguity, social exposure, technical complexity):

```text
completion_rate_7d >= 0.8 and avg_actual_discomfort <= 6 and no repeated blocker
    → consider difficulty +1
two consecutive skips, or completion_rate_7d < 0.4
    → reduce mission size or project scope
predicted - actual discomfort >= 3 across three attempts
    → show calibration insight
actual_discomfort >= 8, or user reports overwhelm
    → do not increase difficulty
```

## 8. Project templates

```ts
type ProjectTemplate = {
  id: string; title: string; promise: string; artifactType: string;
  expectedHours: number; prerequisites: string[];
  stages: TemplateStage[]; skills: string[];
  exampleOutputs: string[]; riskFlags: string[];
};
```

Each stage carries an objective, required evidence, mission patterns by duration, a completion rule, common blockers, and simplification options. **Templates are authored manually before any AI involvement** — the AI adapts a tested path, it does not invent the pedagogy.

## 9. Progress and scoring

No universal confidence score. Five transparent dimensions: **consistency** (active ÷ planned production days), **execution** (completed ÷ accepted missions), **challenge** (total and average completed difficulty), **artifact progress** (required stages completed), **contribution** (feedback and useful crew actions). Optional calibration insight: `median(predicted discomfort − actual discomfort)`.

```text
Production days: 8 of 10 planned      Project stages complete: 4 of 7
Missions completed: 14 of 17          Useful crew contributions: 6
Current challenge level: 3 of 5       Predicted 7.0 / actual 4.5 discomfort
```

Emphasise trend and evidence, never comparison with other users.

## 10. Crew matching

Deferred — hand-pick crews until manual assembly is the obvious bottleneck ([D-014](../log/decision-log.md)). When built:

```text
score = 0.35·timezone_overlap + 0.25·schedule_overlap
      + 0.20·project_category_compatibility + 0.10·language_match
      + 0.10·preferred_feedback_style_match
```

Never place blocked users together. Preserve institution-specific cohorts. Avoid crews below three active members. Replace inactive members early. Allow facilitator override. Do not match on sensitive traits unless explicitly chosen for a protected affinity group.

## 11. Notifications

> Good: *Your next step takes 15 minutes: write the rough opening paragraph.*  
> Bad: *You are losing your streak. Do not fail today.*

Concrete and actionable, user-scheduled, no shame, no false urgency, no public exposure, crew activity batched, frequency automatically reduced after repeated dismissal.

## 12. Moderation and safety

**Content:** text moderation before crew publication, file type and size restrictions, malware scanning, URL safety checks where practical, reporting and blocking, moderator audit trail, posting rate limits.

**AI:** prohibited mission categories, project risk classification, structured output validation, prompt-injection resistance for user-supplied project text, no generation of harassment, dangerous instructions, illegal access, self-harm encouragement, or exploitation, and escalation to human moderation for ambiguous flags.

**Community rules:** critique work, not personal worth · get consent before sharing another person's work · disclose substantial AI assistance · never solicit money, sexual contact, or private sensitive information · no employment guarantees or deceptive portfolio claims.

## 13. Privacy model

**Private:** email, baseline responses, predicted and actual discomfort, private reflections, moderation reports, account and billing data.  
**Crew-visible:** display name, project title, selected progress updates, deliberately shared evidence, feedback requests.  
**Portfolio-visible:** only fields the user explicitly selects, with AI tools and collaborators attributed. Private behavioural ratings excluded by default.

Institutional administrators receive aggregate metrics, and user-level project status only where contractually justified and clearly disclosed.

## 14. Analytics events

```text
account_created · onboarding_started · onboarding_completed
project_selected · project_created · scope_reduced
mission_proposed · mission_accepted · mission_replaced · mission_simplified
mission_skipped · mission_completed · evidence_added
crew_joined · crew_post_created · feedback_given · weekly_review_viewed
project_completed · portfolio_published
subscription_started · subscription_cancelled · account_deleted
```

Properties: anonymous or internal ID, template, cohort, mission duration and difficulty, project stage, source (template/AI/facilitator), time from onboarding. Never raw reflection text.

## 15. API outline

```text
POST   /api/projects                      POST  /api/evidence
GET    /api/projects/:id                  GET   /api/projects/:id/evidence
PATCH  /api/projects/:id
POST   /api/projects/:id/scope-review     POST  /api/crews/join
                                          GET   /api/crews/:id
POST   /api/missions/generate             POST  /api/crews/:id/posts
POST   /api/missions/:id/accept           POST  /api/crew-posts/:id/report
POST   /api/missions/:id/replace
POST   /api/missions/:id/attempts         GET   /api/reviews/weekly
POST   /api/missions/:id/complete         POST  /api/reviews/weekly

POST   /api/portfolio/publish             GET   /api/admin/cohorts/:id/metrics
PATCH  /api/portfolio/:id/visibility
```

Server-side authorisation on every resource. Never rely on hidden UI controls for access control.

## 16. Testing strategy

**Unit:** mission schema validation, progress calculations, matching score, permission rules, notification selection, scope adjustment, stage transitions.

**Integration:** onboarding to first mission, mission attempt with file evidence, private versus crew evidence, weekly review generation, portfolio publication, account deletion, AI failure fallback.

**End-to-end:** new user completes onboarding and first mission · user joins a crew and posts evidence · user reports a post · user reduces scope and still completes · user publishes an unlisted portfolio page · admin views aggregate metrics without private reflections.

**AI evaluation set.** At least 100 fixed project states covering vague projects, overambitious projects, low energy, short time windows, repeated avoidance, different categories, unsafe or illegal requests, prompt injection, AI-dependent projects, and interpersonal missions. Score for specificity, feasibility, duration fit, artifact production, safety, and preservation of user agency.

## 17. Delivery phases

**Phase 0 — Concierge.** No product. Forms, a database, messaging, manually written missions. Delivers a paid cohort, tested templates, a facilitator playbook, completion data, qualitative evidence, and a pricing signal.

**Phase 1 — Solo MVP.** Authentication, onboarding, templates, daily mission, evidence, progress, portfolio. *Goal: prove activation and completion without community complexity.*

**Phase 2 — Crew MVP.** Crew updates, structured feedback, moderation, weekly review. *Goal: test whether crews improve completion and retention.*

**Phase 3 — Institutional pilot.** Cohort codes, aggregate dashboard, facilitator tools, data-processing terms, programme export. *Goal: validate distribution and willingness to pay.*

**Phase 4 — Personalisation.** Adaptive difficulty, mission recommendations, blocker detection, template expansion, optional blocker integrations. *Goal: improve completion while controlling AI cost and preserving user agency.*

## 18. Implementation priorities

1. Manual project templates and mission library
2. Project, mission, attempt, and evidence data model
3. Onboarding through first mission
4. Completion and progress loop
5. Proof-of-work output
6. Analytics
7. Crew system
8. AI adaptation
9. Institutional administration
10. Optional screen-time tool integration

Prove that users finish valuable work before investing heavily in AI, mobile blocking, or social discovery.
