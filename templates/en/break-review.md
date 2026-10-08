# Break Review — checklist and prompts

> Run in a **separate** context from the one that produced the result: a new session, a different model, or a human reviewer. The goal is to prove the result wrong, not to approve it.

## Checklist

| # | Check | Pass? | Notes |
|---|---|---|---|
| 1 | **Done criteria** — every criterion from the Intent Contract is met | ☐ | |
| 2 | **Boundaries** — nothing was changed, assumed or invented outside the limits | ☐ | |
| 3 | **Fabrication** — every fact, source, number, name, API exists and is correct | ☐ | |
| 4 | **Logic** — no contradictions, unjustified leaps or arithmetic errors | ☐ | |
| 5 | **Edge cases** — empty, extreme and unusual-but-realistic inputs handled | ☐ | |
| 6 | **Scope creep** — no changes that were not requested | ☐ | |
| 7 | **Overconfidence** — uncertain claims are marked as uncertain | ☐ | |
| 8 | **Decision Log** — nothing contradicts recorded decisions (or it is flagged) | ☐ | |

**Verdict:** ✅ Accept / 🔁 Back to Make (iteration __ of 3) / ⚠️ Revisit the contract

---

## Prompt snippets

### General adversarial review

```
You are a strict reviewer. Your only job is to find problems in the result below.
Do not praise it and do not rewrite it.

Intent Contract:
<paste contract>

Result:
<paste result>

Check: (1) every Done criterion, (2) Boundaries, (3) any fabricated facts,
sources, numbers or names, (4) logic and arithmetic, (5) edge cases,
(6) changes nobody asked for, (7) overconfident claims.

Return a table: issue | severity (critical / major / minor) | evidence | suggested fix.
If you find nothing material, say so explicitly and list what you checked.
```

### Fact check

```
List every factual claim in the text below as a numbered list.
For each: is it verifiable? What source would confirm it? Mark any claim
you cannot confirm as UNVERIFIED. Do not assume a claim is true because
it sounds plausible.
```

### Code

```
Review this code as if it will run in production tomorrow and you will be
paged if it fails. Find: wrong behaviour vs the Done criteria, unhandled
edge cases, invented APIs or functions, security issues, and changes
outside the requested scope. Propose specific failing test cases.
```

### Pre-mortem

```
Assume this result was used and, three months later, it turned out to be a
serious mistake. Write the three most likely explanations of what went wrong.
```
