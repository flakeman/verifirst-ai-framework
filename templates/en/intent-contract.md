# Intent Contract

> Copy this block into your task, issue or prompt. Fill every field. If you cannot fill **Done criteria**, the task is not ready to be delegated.

```markdown
## Intent Contract

**Task:** <one sentence>
**Trust Map quadrant:** 🟢 / 🟡 / 🔵 / 🔴

### Goal
Why is this needed? What problem does it solve, and for whom?

### Done criteria
Observable, checkable conditions. Each should be answerable with yes/no.
- [ ] ...
- [ ] ...

### Boundaries
What must NOT be changed, assumed or invented.
- Do not change: ...
- Do not assume: ...
- Do not invent facts, sources, numbers or names. If something is unknown, say "unknown" and list it as an open question.

### Inputs & context
- Materials: ...
- Constraints: ...
- Relevant decisions from the Decision Log: D-...

### Verifier & method
- Who/what verifies: ...
- How: tests / control totals / source check / expert read / ...

### Output format
- Shape: ...
- Also return: a list of assumptions made and open questions.
```

---

## Example

```markdown
## Intent Contract

**Task:** Write a SQL query for monthly revenue by region for 2025.
**Trust Map quadrant:** 🟡

### Goal
Finance needs the regional breakdown for the annual report.

### Done criteria
- [ ] Sum across all regions equals the total from the `finance.annual_totals` table (±0).
- [ ] 12 months × every active region, no gaps (zero where no sales).
- [ ] Refunds are subtracted, test orders excluded.

### Boundaries
- Do not modify any tables; read-only queries.
- Do not assume region mapping — use `dim_region` only.
- Do not invent column names; ask if a field is missing.

### Inputs & context
- Schema: attached `schema.sql`.
- D-012: test orders are flagged `is_test = true`.

### Verifier & method
- Analyst runs the query and compares totals with `finance.annual_totals`.

### Output format
- One SQL query + a 3-line explanation + list of assumptions.
```
