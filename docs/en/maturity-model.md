# VeriFirst maturity model

[Русская версия](../ru/maturity-model.md) · [← Back to the framework](../../README.md)

The model helps a team or a company see in 10 minutes where it stands and which next step brings the most value. Levels build on each other.

| Level | Name | In short |
|---|---|---|
| **0** | Ad hoc | AI is used however people like; results are not checked systematically |
| **1** | Aware | People tell tasks apart by risk and check what matters |
| **2** | Team practice | Verification is part of the team process: contracts, Break pass, tracker templates |
| **3** | Cross-team | Shared rules across teams: catalogue, R0–R3, verification debt |
| **4** | Governed | Company policy, AI system register, reporting to leadership |

---

## Self-assessment

Answer "yes" only if it holds for most people or tasks, not for a few enthusiasts. Your level is **the last one with "yes" to at least 4 of 5 questions**, provided every level below it also passes.

### Level 1 · Aware

1. Before a non-trivial AI task, people consider what an error would cost.
2. AI output for important work (production code, customer texts, figures for management) is checked by a person.
3. There is shared awareness that AI can confidently invent facts, sources and names.
4. AI does not perform irreversible actions (sending, paying, deleting, publishing) without a human.
5. People can give an example of an AI error they caught.

### Level 2 · Team practice

1. AI tasks are set with checkable done criteria (an Intent Contract or equivalent).
2. 🟡 and 🔴 work is verified by a separate session, another model or another person.
3. The tracker has a template or field for quadrant and criteria (issue form, PR template, Jira field).
4. The team keeps a decision log and feeds it to the AI when working on the project.
5. Verification time is planned (sprint, iteration), not squeezed in "if time allows".

### Level 3 · Cross-team

1. There is a shared catalogue of common task types with assigned quadrants.
2. Systems and environments are classified R0–R3 the same way for all teams.
3. Contracts apply at team interfaces: what one team guarantees another about AI-made output.
4. Verification debt is tracked explicitly (label, counter) and paid down on a plan.
5. Escaped errors are counted per team and reviewed.

### Level 4 · Governed

1. An approved policy states which quadrants are allowed in which domains.
2. There is a list of R3 actions that always require a human across the company.
3. A register of AI systems affecting customers or money exists: owner, quadrant, verification method.
4. Leadership regularly receives a report: escaped errors, incidents, verification cost share.
5. External standards or regulatory requirements are mapped to internal rules ([mapping](standards-mapping.md)).

---

## Moving up a level

### 0 → 1: "Start noticing"

- Run a one-hour session: 3–4 real AI errors from the team's own work, plus the Trust Map.
- Hand out the [cheat sheet](../../CHEATSHEET.md).
- Install the [AI instructions](../../ai-instructions/README.md) in the tools people already use.
- Agree on one rule: "irreversible actions are done by a human only".

**Sign of success:** a month later, people name the quadrant of a task on their own.

### 1 → 2: "Build it into the process"

- Add the [issue form and PR template](../../integrations/README.md) to the tracker.
- Add "Break pass done" to the Definition of Done for 🟡 and 🔴 work.
- Create `DECISIONS.md` in every active project.
- Start tracking TTV and escaped errors, even manually, once per sprint.

**Sign of success:** escaped errors are a standing topic at retrospectives.

### 2 → 3: "Agree across teams"

- Appoint a verifiability owner.
- Build a shared catalogue of common tasks (15–30 rows is usually enough to start).
- Classify shared systems R0–R3.
- Introduce the `verification-debt` label and review it at every planning session.

**Sign of success:** teams verify each other's output at interfaces, not only their own.

### 3 → 4: "Make it governed"

- Approve a one-page policy ([example](scaling.md#portfolio--company-level)).
- Start an AI system register.
- Introduce a quarterly report to leadership.
- Map the rules to the external requirements relevant to your industry.

**Sign of success:** "can we use AI here?" is answered by policy in minutes, not debated for weeks.

---

## Common rollout mistakes

- **Skipping a level.** A company policy (4) without team practice (2) stays on paper.
- **Measuring volume.** "How many people use AI" is not maturity. Count verified results and escaped errors.
- **Self-review as verification.** AI instructions raise quality but do not replace an independent Break pass.
- **Bans instead of verifiability.** Banning AI in 🔴 work is easier than making it verifiable, but less useful. First look for a way to move the task to 🟡.
