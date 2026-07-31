# Product and Technical Design

**Working title:** ForgePath  
**Document status:** MVP design specification  
**Research snapshot:** 31 July 2026

## 1. Design objective

Build a mobile-first web product that converts an idle moment into one small, meaningful production action and accumulates those actions into a completed proof-of-work project.

The product should feel simpler than a task manager, more active than a course, safer than a public social network, and more outcome-oriented than a generic AI coach.

## 2. Core design principles

### 2.1 One next action

The default screen should not display a large backlog. It should display the user’s project, progress, and one clear next mission.

### 2.2 Production before consumption

Avoid long lessons. Give only the minimum context required to act. Advice should end in an observable action.

### 2.3 Purpose through evidence

Do not ask users to declare a grand purpose. Help them notice what they repeatedly choose, improve, contribute, and finish.

### 2.4 Confidence through graded mastery

Increase challenge gradually. Record predictions and actual outcomes. Reward attempts, revisions, and exposure to feedback—not only polished results.

### 2.5 Small, recurring social units

Crews are stable enough to create familiarity but small enough to prevent a feed economy.

### 2.6 Transparent measurement

Show raw behavior and clear calculations. Avoid a mysterious confidence score or psychological diagnosis.

### 2.7 AI as scaffolding

AI may decompose, adapt, question, critique, and summarize. It should not become the creator of record.

## 3. Information architecture

Primary navigation:

1. **Today**
2. **Project**
3. **Crew**
4. **Evidence**
5. **Profile**

Admin users receive a separate **Cohort** area.

### Today

- available-time selector;
- current mission;
- mission controls;
- short project progress;
- optional crew pulse;
- no scrolling feed.

### Project

- project outcome and definition of done;
- stages and milestones;
- artifact links;
- scope adjustment;
- final proof-of-work builder.

### Crew

- bounded chronological updates;
- structured feedback requests;
- scheduled work session information;
- crew norms and reporting.

### Evidence

- mission history;
- attachments;
- predicted versus actual outcomes;
- skills demonstrated;
- weekly summaries.

### Profile

- schedule;
- interests;
- skills;
- privacy;
- notification settings;
- data export and deletion.

## 4. Key screens

### 4.1 Welcome

Headline:

> Turn unused time into proof of what you can do.

Primary action:

> Start a 30-day project

Secondary explanation:

- one real project;
- one small mission at a time;
- one crew;
- a shareable result.

### 4.2 Outcome selection

Ask:

> What would make the next 30 days valuable?

Options:

- a project for my portfolio;
- something creative I publish;
- evidence of a new skill;
- momentum after a stuck period;
- exploration of a possible career.

### 4.3 Project selection

Display a small curated library. Initial templates should be bounded and artifact-based.

Recommended first templates:

1. Publish a researched explainer.
2. Build and test a simple web tool.
3. Design a small product concept.
4. Create a local problem-and-solution report.
5. Produce a short visual or audio story.
6. Run a tiny service experiment for a real person or organization.

Each template contains:

- target artifact;
- examples;
- required stages;
- expected weekly time;
- skills demonstrated;
- difficulty;
- suitability constraints.

### 4.4 Baseline

Keep under three minutes.

Capture:

- project experience;
- available days and minutes;
- current confidence finishing this type of project;
- recent unfinished projects;
- main blocker;
- comfort showing unfinished work;
- desired visibility of final artifact.

### 4.5 Today screen

Layout order:

1. Project title and day number
2. “How much time do you have?” selector
3. Mission card
4. Accept / easier / different / blocker
5. Progress strip
6. Crew pulse

Mission card example:

**Create a rough problem statement**

Write 100–150 words describing who experiences the problem, when it happens, and what they currently do instead.

**Done when:** A draft is saved to your project, even if the wording is poor.  
**Time:** 15 minutes  
**Difficulty:** 2/5

### 4.6 Mission completion

Ask only what is useful:

1. Did you attempt it?
2. Is the definition of done satisfied?
3. Attach or link the evidence.
4. What happened?
5. Optional: predicted and actual discomfort.
6. What should happen next?

Provide immediate output:

- mission marked complete;
- artifact progress changed;
- evidence added;
- next recommended action previewed.

### 4.7 Crew update

A crew update has a fixed format:

```text
Today I made:
[artifact or sentence]

I am stuck on:
[optional blocker]

Feedback I need:
[none / clarity / usefulness / technical / visual]
```

Feedback options should guide quality:

- “I understood…”
- “I was confused by…”
- “The most useful part is…”
- “One small next test could be…”

### 4.8 Weekly review

Use a concise, evidence-based summary:

```text
You planned 5 production days and produced on 4.
You completed 7 missions and revised 3 artifacts.
Your average predicted discomfort was 7.1; actual was 4.8.
You avoided publishing twice.
Your crew responded to 4 of your updates.
```

Then ask for one decision:

- increase challenge;
- keep challenge stable;
- reduce scope.

### 4.9 Completion and portfolio

The final page includes:

- title;
- one-sentence outcome;
- problem or purpose;
- final artifact;
- user’s contribution;
- process timeline;
- tests or feedback;
- revisions;
- skills demonstrated;
- tools used, including AI tools;
- reflection;
- public, unlisted, or private visibility.

## 5. Recommended implementation stack

This is a pragmatic MVP recommendation, not a fixed requirement.

### Frontend

- Next.js with App Router
- TypeScript
- React
- Tailwind CSS
- Accessible component primitives such as Radix UI or shadcn/ui
- React Hook Form plus Zod for validated forms

### Backend

Option A, fastest managed path:

- Next.js server actions and route handlers
- Supabase Postgres
- Supabase Auth
- Supabase Storage
- Row-Level Security

Option B, more portable:

- Next.js
- PostgreSQL
- Prisma or Drizzle ORM
- Auth.js
- S3-compatible object storage

### AI layer

- provider-agnostic interface;
- structured JSON output;
- schema validation;
- prompt and model version logging;
- rate and cost limits;
- non-AI template fallback.

### Infrastructure

- Vercel or equivalent web deployment;
- managed PostgreSQL;
- error monitoring such as Sentry;
- privacy-conscious product analytics;
- transactional email provider;
- optional queue for weekly summaries and matching.

## 6. Suggested repository structure

```text
/
├── app/
│   ├── (auth)/
│   ├── onboarding/
│   ├── today/
│   ├── projects/
│   ├── crews/
│   ├── evidence/
│   ├── portfolio/
│   ├── admin/
│   └── api/
├── components/
│   ├── missions/
│   ├── projects/
│   ├── crews/
│   ├── evidence/
│   └── ui/
├── lib/
│   ├── ai/
│   ├── analytics/
│   ├── auth/
│   ├── db/
│   ├── matching/
│   ├── moderation/
│   ├── scoring/
│   └── validation/
├── prompts/
├── public/
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
├── REQUIREMENTS.md
├── DEMAND.md
└── DESIGN.md
```

## 7. Domain model

### User

```ts
type User = {
  id: string;
  email: string;
  createdAt: Date;
  timezone: string;
  locale: string;
  ageConfirmed: boolean;
  status: "active" | "suspended" | "deleted";
};
```

### Profile

```ts
type Profile = {
  userId: string;
  displayName: string;
  bio?: string;
  interests: string[];
  selfReportedSkills: string[];
  preferredSessionMinutes: number[];
  availableWeekdays: number[];
  privacyDefault: "private" | "unlisted" | "public";
};
```

### Project

```ts
type Project = {
  id: string;
  ownerId: string;
  templateId?: string;
  title: string;
  outcome: string;
  audience?: string;
  artifactType: string;
  definitionOfDone: string;
  status: "draft" | "active" | "paused" | "completed" | "archived";
  currentStage: ProjectStage;
  startDate: Date;
  targetDate: Date;
  visibility: "private" | "unlisted" | "public";
};
```

### Project stage

```ts
type ProjectStage =
  | "define"
  | "explore"
  | "build"
  | "test"
  | "revise"
  | "publish"
  | "reflect";
```

### Mission

```ts
type Mission = {
  id: string;
  projectId: string;
  source: "template" | "ai" | "facilitator" | "user";
  title: string;
  instruction: string;
  definitionOfDone: string;
  estimatedMinutes: 5 | 15 | 30 | 60;
  difficulty: 1 | 2 | 3 | 4 | 5;
  stage: ProjectStage;
  evidenceType: "text" | "url" | "image" | "file" | "external_action";
  status: "proposed" | "accepted" | "completed" | "skipped" | "expired";
  generatedAt: Date;
  acceptedAt?: Date;
  completedAt?: Date;
};
```

### Mission attempt

```ts
type MissionAttempt = {
  id: string;
  missionId: string;
  userId: string;
  attemptNumber: number;
  predictedDifficulty?: number;
  predictedDiscomfort?: number;
  predictedOutcome?: string;
  completionConfidence?: number;
  attempted: boolean;
  completed: boolean;
  actualDiscomfort?: number;
  actualOutcome?: string;
  recoveryMinutes?: number;
  blockerCode?: string;
  reflection?: string;
  createdAt: Date;
};
```

### Evidence

```ts
type Evidence = {
  id: string;
  projectId: string;
  missionId?: string;
  ownerId: string;
  type: "text" | "url" | "image" | "file";
  title: string;
  textContent?: string;
  url?: string;
  storagePath?: string;
  isPortfolioEligible: boolean;
  visibility: "private" | "crew" | "portfolio";
  createdAt: Date;
};
```

### Crew

```ts
type Crew = {
  id: string;
  cohortId?: string;
  name: string;
  language: string;
  timezoneBand: string;
  status: "forming" | "active" | "completed" | "archived";
  capacity: number;
};
```

### Crew membership

```ts
type CrewMember = {
  crewId: string;
  userId: string;
  role: "member" | "facilitator";
  joinedAt: Date;
  leftAt?: Date;
  notificationLevel: "all" | "digest" | "off";
};
```

### Crew post and feedback

```ts
type CrewPost = {
  id: string;
  crewId: string;
  authorId: string;
  projectId: string;
  evidenceId?: string;
  madeText: string;
  blockerText?: string;
  feedbackType?: "clarity" | "usefulness" | "technical" | "visual";
  status: "visible" | "reported" | "removed";
  createdAt: Date;
};
```

### Cohort

```ts
type Cohort = {
  id: string;
  organizationId?: string;
  name: string;
  inviteCode: string;
  startDate: Date;
  endDate: Date;
  status: "draft" | "active" | "completed";
};
```

## 8. Database relationships

```text
User 1---1 Profile
User 1---N Project
Project 1---N Mission
Mission 1---N MissionAttempt
Project 1---N Evidence
User N---N Crew through CrewMember
Crew 1---N CrewPost
Cohort 1---N Crew
Organization 1---N Cohort
```

Private reflections should be stored separately or protected by stricter row-level policies than crew-visible evidence.

## 9. Mission generation engine

### 9.1 Inputs

- project template and definition of done;
- current project stage;
- completed and skipped missions;
- required remaining milestones;
- selected available time;
- self-reported energy;
- experience level;
- recent blockers;
- crew dependencies;
- evidence already available;
- safety and content category.

### 9.2 Mission quality rules

A generated mission must:

1. start with one observable verb;
2. produce an artifact or external action;
3. fit the requested duration;
4. include a binary or clearly testable definition of done;
5. advance the current project;
6. avoid combining several independent tasks;
7. avoid unnecessary research;
8. avoid producing the user’s final work without user contribution;
9. use difficulty mostly between 2 and 4;
10. be safe and lawful.

Bad:

> Think about your target customer and improve your concept.

Better:

> Write three sentences describing one target customer, the moment the problem occurs, and what they currently do instead.

### 9.3 Structured AI response

```json
{
  "title": "Write a one-person problem statement",
  "instruction": "Write 100–150 words describing one person, the moment the problem occurs, and their current workaround.",
  "definitionOfDone": "A draft is saved to the project, even if it is incomplete.",
  "estimatedMinutes": 15,
  "difficulty": 2,
  "stage": "define",
  "evidenceType": "text",
  "reason": "This creates the first testable project assumption.",
  "safetyFlags": []
}
```

Validate all output with a strict schema. If validation fails twice, return a template mission.

### 9.4 Difficulty adaptation

Initial rules:

```text
if completion_rate_7d >= 0.8
and average_actual_discomfort <= 6
and no repeated blocker:
    consider difficulty +1

if two consecutive missions are skipped
or completion_rate_7d < 0.4:
    reduce mission size or project scope

if predicted_discomfort - actual_discomfort >= 3
for three relevant attempts:
    show calibration insight

if actual_discomfort >= 8
or user reports overwhelm:
    do not increase difficulty
```

Difficulty adaptation should change one variable at a time: duration, visibility, ambiguity, social exposure, or technical complexity.

## 10. Project template design

Each template should be stored as structured data:

```ts
type ProjectTemplate = {
  id: string;
  title: string;
  promise: string;
  artifactType: string;
  expectedHours: number;
  prerequisites: string[];
  stages: TemplateStage[];
  skills: string[];
  exampleOutputs: string[];
  riskFlags: string[];
};
```

Each stage contains:

- objective;
- required evidence;
- mission patterns by duration;
- completion rule;
- common blockers;
- simplification options.

Templates should be developed manually before relying on AI. The AI adapts a tested path; it does not invent the product pedagogy from scratch.

## 11. Progress and scoring design

Do not create one universal confidence score.

Show five transparent dimensions:

1. **Consistency:** active production days divided by planned days.
2. **Execution:** completed missions divided by accepted missions.
3. **Challenge:** total and average completed difficulty.
4. **Artifact progress:** required stages completed.
5. **Contribution:** feedback and useful crew actions.

Optional calibration insight:

```text
median prediction gap =
median(predicted discomfort - actual discomfort)
```

Example dashboard:

```text
Production days: 8 of 10 planned
Missions completed: 14 of 17 accepted
Current challenge level: 3 of 5
Project stages complete: 4 of 7
Useful crew contributions: 6
Predicted discomfort: 7.0
Actual discomfort: 4.5
```

The design should emphasize trend and evidence rather than comparison with other users.

## 12. Crew matching

Initial matching score:

```text
score =
0.35 * timezone_overlap
+ 0.25 * schedule_overlap
+ 0.20 * project_category_compatibility
+ 0.10 * language_match
+ 0.10 * preferred_feedback_style_match
```

Constraints:

- do not place blocked users together;
- preserve institution-specific cohorts;
- avoid crews below three active members;
- replace inactive members during the first week;
- allow a facilitator to override matching.

Do not match on sensitive traits unless explicitly chosen and necessary for a protected affinity group.

## 13. Notification design

Good notification:

> Your next step takes 15 minutes: write the rough opening paragraph.

Bad notification:

> You are losing your streak. Do not fail today.

Rules:

- concrete and actionable;
- user-scheduled;
- no shame;
- no false urgency;
- no public exposure;
- batch crew activity;
- automatically reduce frequency after repeated dismissal.

## 14. Moderation and safety architecture

### Content controls

- text moderation before crew publication;
- file-type and size restrictions;
- malware scanning for uploads;
- URL safety checks where practical;
- reporting and blocking;
- moderator audit trail;
- rate limits for posting and messaging.

### AI controls

- prohibited mission categories;
- project risk classification;
- structured output validation;
- prompt-injection resistance for user-supplied project text;
- no generation of targeted harassment, dangerous instructions, illegal access, self-harm encouragement, or exploitative activity;
- escalation to human moderation for ambiguous flags.

### Community rules

- critique work, not personal worth;
- obtain consent before sharing another person’s work;
- disclose substantial AI assistance;
- do not solicit money, sexual contact, or private sensitive information;
- no employment guarantees or deceptive portfolio claims.

## 15. Privacy model

Data classes:

### Private

- email;
- baseline responses;
- predicted and actual discomfort;
- private reflections;
- moderation reports;
- account and billing data.

### Crew-visible

- display name;
- project title;
- selected progress updates;
- evidence deliberately shared;
- feedback requests.

### Portfolio-visible

- only fields explicitly selected by the user;
- AI tools and collaborators should be attributed where relevant;
- private behavioral ratings are excluded by default.

Institutional administrators receive aggregate program metrics and user-level project status only where contractually justified and clearly disclosed.

## 16. Analytics event model

Core events:

```text
account_created
onboarding_started
onboarding_completed
project_selected
project_created
mission_proposed
mission_accepted
mission_replaced
mission_simplified
mission_skipped
mission_completed
evidence_added
crew_joined
crew_post_created
feedback_given
weekly_review_viewed
scope_reduced
project_completed
portfolio_published
subscription_started
subscription_cancelled
account_deleted
```

Useful properties:

- anonymous user or internal ID;
- project template;
- cohort;
- mission duration;
- mission difficulty;
- project stage;
- source: template/AI/facilitator;
- time from onboarding;
- no raw private reflection text.

## 17. API outline

```text
POST   /api/projects
GET    /api/projects/:id
PATCH  /api/projects/:id
POST   /api/projects/:id/scope-review

POST   /api/missions/generate
POST   /api/missions/:id/accept
POST   /api/missions/:id/replace
POST   /api/missions/:id/attempts
POST   /api/missions/:id/complete

POST   /api/evidence
GET    /api/projects/:id/evidence

POST   /api/crews/join
GET    /api/crews/:id
POST   /api/crews/:id/posts
POST   /api/crew-posts/:id/report

GET    /api/reviews/weekly
POST   /api/reviews/weekly

POST   /api/portfolio/publish
PATCH  /api/portfolio/:id/visibility

GET    /api/admin/cohorts/:id/metrics
```

Use server-side authorization on every resource. Never rely on hidden UI controls for access control.

## 18. Testing strategy

### Unit tests

- mission schema validation;
- progress calculations;
- matching score;
- permission rules;
- notification selection;
- scope adjustment;
- project-stage transition.

### Integration tests

- onboarding to first mission;
- mission attempt with file evidence;
- private versus crew evidence;
- weekly review generation;
- portfolio publication;
- account deletion;
- AI failure fallback.

### End-to-end tests

1. New user completes onboarding and first mission.
2. User joins a crew and posts evidence.
3. User reports another post.
4. User reduces project scope and still completes.
5. User publishes an unlisted portfolio page.
6. Admin views aggregate cohort metrics without private reflections.

### AI evaluation set

Create a fixed set of at least 100 project states covering:

- vague projects;
- overambitious projects;
- low energy;
- short time windows;
- repeated avoidance;
- different project categories;
- unsafe or illegal requests;
- prompt injection;
- AI-dependent projects;
- interpersonal missions.

Score outputs for specificity, feasibility, duration fit, artifact production, safety, and preservation of user agency.

## 19. Delivery phases

### Phase 0: Concierge test

No full product. Use forms, a database, messaging, and manually generated missions.

Deliverables:

- paid cohort;
- tested templates;
- facilitator playbook;
- completion data;
- qualitative evidence;
- pricing signal.

### Phase 1: Solo MVP

- authentication;
- onboarding;
- project template;
- daily mission;
- evidence;
- progress;
- final portfolio.

Goal: prove activation and project completion without community complexity.

### Phase 2: Crew MVP

- matching;
- crew updates;
- structured feedback;
- moderation;
- weekly review.

Goal: test whether crews improve completion and retention.

### Phase 3: Institutional pilot

- cohort codes;
- aggregate dashboard;
- facilitator tools;
- data-processing terms;
- program export.

Goal: validate distribution and willingness to pay.

### Phase 4: Personalization

- adaptive difficulty;
- mission recommendations;
- blocker detection;
- project-template expansion;
- optional blocker integrations.

Goal: improve completion while controlling AI cost and preserving user agency.

## 20. Implementation priorities

Build in this order:

1. Manual project templates and mission library.
2. Project, mission, attempt, and evidence data model.
3. Onboarding to first mission.
4. Completion and progress loop.
5. Proof-of-work output.
6. Analytics.
7. Crew system.
8. AI adaptation.
9. Institutional administration.
10. Optional integration with screen-time tools.

The product should prove that users finish valuable work before investing heavily in AI, mobile blocking, or social discovery.
