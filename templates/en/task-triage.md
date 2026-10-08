# Task Triage — Trust Map worksheet

> Fill in before starting any non-trivial AI task. Takes 2 minutes.

**Task:** _one sentence_

## 1. Cost of error

If the result is wrong and nobody notices, what happens?

- [ ] Nothing much / easy to redo → **Low**
- [ ] Money, reputation, legal, safety, customer impact, or errors that surface much later → **High**

## 2. Ease of verification

How will the result be confirmed as correct?

- [ ] Tests, control totals, a reference example, quick visual check, or a short read by someone who knows the subject → **Easy**
- [ ] Requires deep expertise, long research, or only time will tell → **Hard**

## 3. Quadrant

| | Easy to verify | Hard to verify |
|---|---|---|
| **Low cost** | 🟢 Delegate | 🔵 Explore |
| **High cost** | 🟡 Delegate + Review | 🔴 Advise |

**Result:** 🟢 / 🟡 / 🔵 / 🔴

## 4. Can it move to a better quadrant?

- [ ] Split into smaller, individually checkable pieces
- [ ] Require sources / references for every factual claim
- [ ] Prepare tests, control totals or expected examples in advance
- [ ] Request structured output that can be validated automatically

**After changes:** 🟢 / 🟡 / 🔵 / 🔴

## 5. Working mode

| Quadrant | Mode | Break pass | Who accepts |
|---|---|---|---|
| 🟢 | AI end-to-end | Spot-check | Anyone |
| 🟡 | AI does, always verified | **Required** | Owner after verification |
| 🔵 | AI proposes options | Optional | Owner picks |
| 🔴 | AI advises only | **Required** for any AI analysis used | Human decides and owns |
