# Decision Log

> Keep one log per project, e.g. `DECISIONS.md` in the repo root. Record decisions that future work depends on, not every step. Feed relevant entries into the AI's context when returning to the project.

**Instruction for the AI (paste with the log):**
> These are the project's recorded decisions. Follow them. If anything you propose contradicts a decision, say so explicitly and name its ID instead of silently deviating.

---

## Template

```markdown
### D-000 · YYYY-MM-DD · <short title>
- **Decision:** <one sentence>
- **Reason:** <why, 1–2 sentences>
- **Rejected alternatives:** <option — why it lost>
- **Revisit if:** <condition that would reopen this>
- **Status:** active / superseded by D-___
```

---

## Example

### D-001 · 2026-10-08 · Single database
- **Decision:** Use one PostgreSQL instance for all services at MVP stage.
- **Reason:** Team of two; operational simplicity matters more than isolation now.
- **Rejected alternatives:** Database per service — too much ops overhead for current load.
- **Revisit if:** More than 3 services or a service needs independent scaling.
- **Status:** active

### D-002 · 2026-10-08 · No invented data in reports
- **Decision:** AI-generated reports must cite a source for every number; unknown values are shown as "n/a".
- **Reason:** A fabricated figure in an earlier draft was caught only by the client.
- **Rejected alternatives:** Manual spot-checks only — missed errors.
- **Revisit if:** Never, unless reporting moves to a fully automated, tested pipeline.
- **Status:** active
