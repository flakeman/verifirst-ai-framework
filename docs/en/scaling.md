# Scaling: from one team to the whole company

[Русская версия](../ru/scaling.md) · [← Back to the framework](../../README.md)

The logic mirrors SAFe: team → team of teams → portfolio. Each level uses the same six components with different content.

| Component | Team | Several teams (ART equivalent) | Portfolio / company |
|---|---|---|---|
| **Trust Map** | Quadrant per task | Shared catalogue of common task types with pre-assigned quadrants | Risk appetite: which quadrants are allowed in which domains |
| **Intent Contract** | Per task | At interfaces between teams | Per AI initiative: goal, success criteria, what is unacceptable |
| **Make–Break** | Separate pass | Cross-team review: one team's 🔴 output is checked by another | Independent audit of critical AI systems |
| **Decision Log** | Per project | Shared log of cross-team decisions | AI decision register for leadership and regulators |
| **Reversibility** | Team agreement | Shared R0–R3 classification of systems | Company-wide AI autonomy policy |
| **Metrics** | TTV, rework | Escape rate per team and at interfaces; verification capacity per increment | Escape-rate trend, verification cost share, incidents |

---

## Team-of-teams level

### New elements

- **Verifiability owner** (similar to the System Architect in SAFe). Maintains the shared Trust Map catalogue and the R0–R3 classification, and keeps verification from becoming the bottleneck of the whole flow.
- **Verification debt** (similar to technical debt). AI results accepted without the required Break pass to save time. Track it explicitly and pay it down, or it turns into escaped errors.

### Example: three teams at a bank

*Illustrative example.* Mobile, backend and data teams build one product — a credit card.

**Shared Trust Map catalogue** (one page for all teams):

| Task type | Quadrant | Verified by |
|---|---|---|
| SQL report for internal analytics | 🟡 | Control totals + analyst |
| Push-notification text to customers | 🟡 | Editor + legal for promotions |
| API code | 🟡 | Contract tests + review |
| Credit-scoring logic | 🔴 | AI advises only; risk management decides |

Without the catalogue, the mobile team treated notification texts as 🟢, and legal learned about them from customer complaints.

**Contract at the interface.** The backend uses AI to generate a new credit-limit API. The cross-team Intent Contract: "response matches `limits-api.yaml`, the limit is never negative, errors return 503, not 500". The Break pass is run by the mobile team — the API's consumer, not its author.

**Verification debt.** Before a release the backend accepted 12 AI results without a Break pass to hit the date. This is logged as debt: 12 backlog cards tagged `verification-debt`. Next increment planning reserves 3 days to pay it down. Two of the twelve turned out to contain errors.

**Increment planning (PI planning equivalent).** Each team states not only scope but verification capacity: reviewer hours per week. If the teams together plan more 🟡 and 🔴 work than they can verify, the excess is deferred during planning instead of surfacing at the end.

---

## Portfolio / company level

At this level the framework effectively becomes an AI risk-management system.

### Example: a company policy

*Illustrative* one-page policy:

1. **Risk appetite by domain.**
   - Marketing, internal documents: all quadrants allowed.
   - Customer-facing work: 🟢 not allowed, 🟡 minimum.
   - Finance, legal, HR: AI in 🔴 "Advise" mode only.
2. **R3 actions that always require a human:** sending to external recipients, payments, changing customer data, signing, deploying to production, deleting data.
3. **AI decision register:** every AI system that affects customers has an owner, a quadrant, a verification method and a decision log.
4. **Quarterly board report:** escaped errors by domain, verification cost share, incidents and their reviews.

### Mapping to external requirements

The portfolio level maps naturally onto ISO/IEC 42001 (AI management systems) and the EU AI Act. Such a mapping must be checked against the primary sources and is prepared as a separate document.
