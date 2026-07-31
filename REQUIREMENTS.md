# Product Requirements

**Working title:** ForgePath  
**Document status:** MVP specification  
**Research snapshot:** 31 July 2026  
**Primary audience:** Product, engineering, design, research, and pilot partners

## 1. Product summary

ForgePath helps young adults convert idle, low-purpose screen time into small acts of production that accumulate into a finished, shareable project.

The product is not positioned as a generic confidence app, therapy product, social network, course platform, or screen blocker. Its first promise is concrete:

> Complete a real project in 30 days, build proof of skill, and work alongside a small crew.

Confidence is treated as an outcome of repeated action and recorded evidence. Purpose is treated as something that can emerge from chosen work, growing competence, contribution, and relationships.

## 2. Problem statement

The initial target user often has unstructured time, wants to become more capable, and knows that passive consumption is not helping. However, the user:

- does not know what to make;
- cannot reduce a project to a manageable next action;
- fears producing something bad or being judged;
- has weak external accountability;
- does not see objective evidence of progress;
- may feel isolated from productive peers;
- struggles to translate learning into portfolio evidence.

Existing tools usually solve only one part of this problem:

- screen blockers remove a distraction but do not supply a meaningful alternative;
- task managers assume the user already knows what to do;
- courses supply more content to consume;
- public social platforms optimize comparison and attention;
- generic AI assistants generate ideas or outputs without ensuring that the user acts, learns, or finishes.

## 3. Product thesis

When a person receives one appropriately sized production mission, completes it, records evidence, and is seen by a consistent small group, the person is more likely to continue producing and to build confidence through mastery.

The product loop is:

1. Choose a meaningful project.
2. Receive one small next mission.
3. Produce something observable.
4. Record evidence and compare feared versus actual outcomes.
5. Share progress with a small crew.
6. Increase difficulty gradually.
7. Finish and publish a proof-of-work artifact.

## 4. Goals

### 4.1 MVP goals

1. Help users begin a first production mission within ten minutes of onboarding.
2. Help users complete a bounded project within 30 days.
3. Generate visible evidence of skill, persistence, and contribution.
4. Reduce the friction between an idle moment and a meaningful next action.
5. Create recurring, low-pressure interaction within a crew of four to six users.
6. Measure behavior rather than relying on a single subjective confidence score.
7. Test whether users or institutions will pay for the outcome.

### 4.2 Non-goals for MVP

The MVP will not:

- diagnose or treat depression, anxiety, ADHD, addiction, or other conditions;
- promise to give users a life purpose;
- operate as a general-purpose social network;
- include an infinite public feed;
- provide job placement or guarantee employment;
- support users under 18;
- automatically block third-party mobile applications;
- generate an entire finished project on behalf of the user;
- include creator monetization, token rewards, or cash prizes;
- support complex organization administration beyond a basic pilot dashboard.

## 5. Target users

### Persona A: Directionless graduate

- Age: 21–26
- Situation: Recently graduated or between jobs
- Pain: Has time but lacks structure, portfolio evidence, and confidence
- Desired outcome: Finish a credible project that can be shown in applications or interviews

### Persona B: Aspiring creator who never publishes

- Age: 18–30
- Situation: Has many ideas and unfinished drafts
- Pain: Perfectionism, fear of judgment, inconsistent execution
- Desired outcome: Publish one imperfect but complete project and develop a repeatable production habit

### Persona C: Student with unstructured time

- Age: 18–24
- Situation: Studies but spends substantial free time consuming short-form content
- Pain: Boredom, weak direction, few peers who make things
- Desired outcome: Use spare time to develop a demonstrable skill and meet productive peers

### Secondary buyer: Institution

Universities, workforce programs, bootcamps, community organizations, and employers may purchase a cohort-based version to improve engagement, portfolio production, belonging, and transition-to-work outcomes.

## 6. Jobs to be done

### Primary job

> When I feel bored, directionless, or tempted to scroll, help me start one meaningful action that contributes to a finished project.

### Supporting jobs

- Help me choose a project that is challenging but achievable.
- Tell me exactly what to do next.
- Make it safe to show unfinished work.
- Help me see that feared outcomes are often worse than actual outcomes.
- Let a small group notice whether I showed up.
- Turn completed work into proof I can show other people.
- Help me identify what type of work I want to continue.

## 7. Core user experience

### 7.1 Onboarding

The user must be able to:

1. Create an account.
2. Confirm that they are at least 18.
3. Select a primary desired outcome:
   - build a portfolio;
   - publish a creative project;
   - learn by making;
   - regain productive momentum;
   - explore a career direction.
4. Select or define a 30-day project.
5. Set available days, preferred session length, and current experience.
6. Complete a short baseline assessment.
7. Join or be assigned to a crew.
8. Receive the first mission immediately.

The onboarding must avoid abstract questions such as “What is your life purpose?” It should ask for concrete interests, constraints, and desired outputs.

### 7.2 Daily production flow

The home screen must foreground a single action:

> I have 5 / 15 / 30 / 60 minutes.

After selecting a duration, the system presents one mission that:

- begins with a clear verb;
- has one definition of done;
- fits the available time;
- creates or improves an artifact;
- is appropriate to the user’s project stage;
- is not merely “research,” “think,” or “plan” without a tangible output.

The user can accept, request an easier mission, request a different mission, or report a blocker.

### 7.3 Evidence flow

Before a difficult mission, the user may record:

- expected difficulty, 1–5;
- expected discomfort, 0–10;
- feared outcome in one sentence;
- confidence that the mission will be completed, 0–100%.

After the attempt, the user records:

- attempted: yes/no;
- completed: yes/no;
- actual discomfort, 0–10;
- actual outcome;
- evidence attachment or link;
- what was learned;
- whether the mission should be repeated, increased, or reduced in difficulty.

### 7.4 Crew flow

Each crew contains four to six active users when possible. Members can:

- see each member’s current project and recent completed mission;
- post a short daily proof or progress note;
- react with bounded signals such as “seen,” “useful,” or “keep going”;
- request or provide specific feedback;
- attend an optional scheduled co-working session;
- report inappropriate content or behavior.

The crew experience must not contain follower counts, popularity rankings, public like counts, or an infinite feed.

### 7.5 Weekly review

Every seven days, the product summarizes:

- missions planned and completed;
- production minutes;
- artifacts created or changed;
- average predicted versus actual discomfort;
- repeated avoidance points;
- crew contributions;
- project progress;
- recommended adjustment for the next week.

The review asks the user to choose one of three paths:

- continue at the current level;
- increase challenge;
- reduce scope to protect completion.

### 7.6 Completion flow

A project is complete when the user has:

- met the predefined definition of done;
- uploaded or linked the final artifact;
- written a short project summary;
- identified skills demonstrated;
- recorded at least one obstacle and response;
- optionally requested peer feedback;
- generated a shareable proof-of-work page.

The completion page should be exportable as a public link and printable PDF in a later release. The MVP requires a public or private web page.

## 8. Functional requirements

### Account and profile

- **FR-001:** Users can register with email or supported OAuth.
- **FR-002:** Users must confirm age eligibility and accept terms.
- **FR-003:** Users can set timezone, availability, interests, skills, and privacy preferences.
- **FR-004:** Users can export or delete their account data.

### Projects

- **FR-010:** Users can select from project templates.
- **FR-011:** Users can create a custom project with a title, outcome, audience, artifact type, deadline, and definition of done.
- **FR-012:** The system validates that a project can reasonably be completed in 30 days.
- **FR-013:** Users can reduce project scope without losing historical evidence.
- **FR-014:** Projects have stages: define, explore, build, test, revise, publish, reflect.
- **FR-015:** A user may have one active MVP project at a time.

### Missions

- **FR-020:** The system generates or selects missions based on project stage, available time, energy, skill level, dependencies, and recent behavior.
- **FR-021:** Every mission has a title, instruction, definition of done, estimated duration, difficulty, artifact type, and project-stage mapping.
- **FR-022:** Users can accept, replace, simplify, skip, or report a blocker.
- **FR-023:** Repeated mission replacement triggers a scope or blocker review.
- **FR-024:** The system must have non-AI fallback missions for every project stage.
- **FR-025:** The system must not generate dangerous, illegal, exploitative, or clinically framed missions.

### Evidence and progress

- **FR-030:** Users can submit text, URL, image, or file evidence.
- **FR-031:** Mission attempts preserve planned, attempted, completed, and skipped states.
- **FR-032:** The system stores predicted and actual discomfort separately.
- **FR-033:** Users can view transparent progress metrics.
- **FR-034:** The system does not display a universal “confidence score.”
- **FR-035:** Users can browse their evidence timeline and filter by project stage or skill.
- **FR-036:** Completed evidence can be added to the final proof-of-work page.

### Crews

- **FR-040:** Users can join a crew by invitation or matching.
- **FR-041:** Matching considers timezone, project category, session preference, and language.
- **FR-042:** Users can leave, mute, or report a crew.
- **FR-043:** Crew posts are chronological and bounded.
- **FR-044:** Crew members can request structured feedback.
- **FR-045:** Moderators can remove content and suspend accounts.
- **FR-046:** The system supports a crew code for institution-led pilots.

### Notifications

- **FR-050:** Users can schedule one daily production reminder.
- **FR-051:** Notifications must reference a concrete next mission, not generic guilt or streak loss.
- **FR-052:** Users can disable all non-essential notifications.
- **FR-053:** Crew notifications are batched by default.

### Portfolio output

- **FR-060:** Users can generate a proof-of-work page.
- **FR-061:** Pages show the final artifact, contribution, skills, process evidence, and reflection.
- **FR-062:** Users control public, unlisted, or private visibility.
- **FR-063:** Public pages must not expose anxiety or discomfort data by default.

### Administration and pilots

- **FR-070:** Administrators can create a cohort and invite users.
- **FR-071:** Administrators can view aggregate activation, participation, and completion data.
- **FR-072:** Administrators cannot read private reflections unless the user explicitly shares them.
- **FR-073:** Aggregate reporting must suppress personally identifiable data where practical.

## 9. Measurement model

The product must emphasize observable metrics:

- missions attempted;
- missions completed;
- completion rate;
- production minutes;
- number of artifacts created or revised;
- number of drafts shared before feeling ready;
- project-stage progression;
- crew feedback given and received;
- predicted versus actual discomfort;
- recovery time where recorded;
- project completion;
- proof-of-work page published;
- continued production after the 30-day program.

Suggested derived metrics:

```text
7-day completion rate =
completed missions / accepted missions

difficulty-adjusted output =
sum(completed mission difficulty)

prediction gap =
predicted discomfort - actual discomfort

production consistency =
active production days / planned production days

artifact progression =
completed required project stages / total required stages
```

No derived metric should be presented as a clinical measure or objective measure of a person’s worth.

## 10. MVP success criteria

These are product hypotheses and pilot decision thresholds, not industry benchmarks.

### Activation

- At least 70% of registered pilot users accept a project.
- At least 60% complete a first mission within 24 hours.
- Median time from registration to first accepted mission is under 10 minutes.

### Engagement

- At least 50% of activated users complete three missions during week one.
- At least 40% remain active in week three.
- At least 50% post or respond in their crew during the first week.

### Outcome

- At least 30% of activated users complete the defined project.
- At least 40% produce a shareable proof-of-work artifact.
- At least 50% report that the final project is useful for a portfolio, application, conversation, or continued personal work.
- At least 25% begin another project or continue producing within 14 days of completion.

### Commercial

- At least 15 individuals pay for a concierge pilot at a tested price.
- At least three institutional buyers agree to a discovery meeting after seeing pilot outcomes.
- At least one institution signs a paid or deposit-backed pilot before major platform expansion.

## 11. Monetization hypotheses

Test, do not assume:

1. **B2C outcome purchase:** USD 29–79 for a 30-day project sprint.
2. **B2C membership:** USD 8–15 monthly after users complete one project and understand recurring value.
3. **Institutional cohort:** Per-seat pricing for universities, workforce organizations, bootcamps, or employers.
4. **Facilitated cohort:** Higher-priced version including human project review and scheduled group sessions.

The first commercial test should favor a bounded paid program rather than an indefinite subscription. The user should understand exactly what they are buying.

## 12. Safety, ethics, and trust

- The product must state that it is not therapy or medical treatment.
- It must not use shame, withdrawal of social status, or punitive streak mechanics.
- It must not encourage sleep deprivation, overwork, dangerous challenges, harassment, unauthorized access, or public exposure without consent.
- It must provide reporting, blocking, and moderation controls.
- It must minimize collection of sensitive mental-health information.
- It must not reveal private discomfort ratings to crews or institutional administrators.
- AI-generated missions and feedback must pass content and schema validation.
- Users must be able to complete the core program without sharing publicly.
- Moderation policies must address abuse, sexual content, hate, self-harm content, exploitation, and intellectual-property violations.
- If a user expresses acute distress, the product should stop productivity coaching and present appropriate crisis-support guidance based on location. It should not attempt counselling.

## 13. Non-functional requirements

- **NFR-001 Performance:** Core authenticated pages should reach usable state within three seconds on typical mobile connections.
- **NFR-002 Reliability:** Mission submission must be idempotent and recoverable after network interruption.
- **NFR-003 Accessibility:** Target WCAG 2.2 AA for core flows.
- **NFR-004 Responsive design:** All MVP flows must work at 360 px width.
- **NFR-005 Security:** Encrypt data in transit and at rest through managed infrastructure.
- **NFR-006 Privacy:** Separate private reflections from public portfolio data.
- **NFR-007 Observability:** Log structured errors and key product events without storing reflection text in analytics.
- **NFR-008 Portability:** Users can export project and evidence data in JSON or CSV.
- **NFR-009 AI resilience:** Core flows remain usable when the language-model provider is unavailable.
- **NFR-010 Cost control:** Cache reusable templates and impose per-user generation limits.

## 14. MVP release boundary

The first production release includes:

- web authentication;
- onboarding and baseline;
- project templates and one custom project;
- mission generation with template fallback;
- mission attempts and evidence;
- transparent progress dashboard;
- crews with chronological updates and structured feedback;
- weekly review;
- proof-of-work page;
- simple cohort administration;
- analytics and moderation controls.

Native mobile apps, application blocking, live video coworking, employer matching, sophisticated recommender models, and public discovery are later-stage features.

## 15. Open product decisions

1. Which initial project category produces the clearest value: software, design, research, content, community service, or mixed?
2. Is the primary payer the individual, university, workforce program, or employer?
3. Are crews created at onboarding or after users complete a first mission?
4. How much human facilitation is required to achieve acceptable completion rates?
5. Does a 30-day program outperform a shorter 14-day program?
6. Which final artifact is most persuasive to buyers: portfolio page, skills report, completed project, or verified contribution record?
7. Should the first market be geographically local, English-speaking global, or institution-specific?

These questions should be resolved through paid pilots rather than internal debate alone.
