# Integrating with Agile and Waterfall

[Русская версия](../ru/integration.md) · [← Back to the framework](../../README.md)

VeriFirst does not replace Scrum, Kanban or Waterfall. Delivery models answer "in what order and when do we do the work". VeriFirst answers "how do we accept an AI-made result without letting an error through". It operates at the level of a single work item, so it fits into any model.

---

## Scrum

| Scrum element | What VeriFirst adds |
|---|---|
| User story + acceptance criteria | Intent Contract: criteria gain Boundaries ("what must not be invented") and a verification method |
| Definition of Ready | A story is not ready without checkable Done criteria |
| Definition of Done | 🟡 and 🔴 work requires a completed Break pass |
| Refinement / planning | Each story gets a Trust Map quadrant; sprint capacity includes time for verification |
| Velocity | Complemented by TTV and escape rate |
| Retrospective | Review escaped errors: at which step should they have been caught |

### Example: online store, discount calculation

A team of five, two-week sprints. Story: "As a shopper, I want to see the final price with my promo code and loyalty discount applied."

**Refinement.** A pricing error costs real money, but the code can be tested → quadrant 🟡. The team writes an Intent Contract:
- *Done criteria:* 15 reference baskets from the analyst's table produce exactly the expected totals; combined discounts never exceed 30%.
- *Boundaries:* do not touch the payment module; do not invent promo API fields — use only `promo-api.yaml`.
- *Verifier:* automated tests + review by another developer.

**Planning.** Previously this would have been estimated at 3 days of development. Now: 0.5 day generating code with AI + 1 day for tests, the Break pass and review. Verification is what gets planned.

**Make–Break.** The AI writes the code in an hour. A separate session prompted to "find errors" discovers that an empty basket plus a promo code returns a negative total. Fixed before review.

**Retrospective.** A week later, production reveals the AI used a `promo.expires_at` field that does not exist in the API. The error escaped. Root cause: the Break pass did not check the code against `promo-api.yaml`. Fix: the team checklist gains "every external API field checked against the spec", logged as D-014.

---

## Kanban

A **"Verification (Break)"** column with its own WIP limit appears between "In progress" and "Done". By the theory of constraints, this becomes the bottleneck when working with AI, and the board makes it visible.

### Example: customer support

A support team of six drafts customer replies with AI.

```
New → AI draft → Verification (WIP 5) → Send (human) → Closed
```

- Routine questions ("how do I reset my password") — 🟢: every tenth draft is checked.
- Refunds and complaints — 🟡: every draft is checked by a senior agent.
- Sending to the customer is always R3: a human presses "Send".

After a week the Verification column is permanently full: 20 cards against a limit of 5. Instead of raising the limit, the team moves work to a better quadrant: for the 12 most common refund types they write reference replies; the AI fills in order data, and verification shrinks to checking three fields. The queue drops to 4 cards.

---

## Waterfall and the V-model

The V-model is built on the idea that every level of building has a matching level of verification. The Break pass is that independent verification, and Reversibility Gates line up with stage gates.

| Phase | Where AI helps | Quadrant | Verification |
|---|---|---|---|
| Requirements | Draft spec sections from interview transcripts | 🟡 | Every requirement traced to its transcript; customer signs off |
| Design | Architecture options | 🔵 → 🔴 | AI proposes, the architect decides and logs it |
| Build | Code, migrations | 🟡 | Tests, review |
| Testing | Test cases generated from the spec | 🟡 | Traceability: every requirement covered by at least one test |
| Rollout | User guides | 🟢 / 🟡 | Spot check with a real user |

### Example: specification for a document-management system

In one day the AI turned 14 interview transcripts into a 60-page draft spec. Without VeriFirst it would have gone straight to the customer. With it:

1. The **Intent Contract** required a transcript reference for every requirement.
2. The **Break pass** found 9 requirements without one. Six had been "filled in" by analogy with typical systems; the customer never said them.
3. Before the **"spec sign-off" stage gate** (R3, irreversible: the budget and contract follow), the project manager walked through the disputed items with the customer in person.

Result: 2 days instead of 3 weeks of manual work, and not a single requirement the customer had not stated.

---

## Hybrid models

Work the same way. A common setup is Waterfall at the customer-contract level and Scrum inside the build phase. Reversibility Gates sit at phase boundaries; the Trust Map and Make–Break run inside sprints.
