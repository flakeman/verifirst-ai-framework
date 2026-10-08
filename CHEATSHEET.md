# VeriFirst in 5 minutes

[Русская версия](CHEATSHEET.ru.md) · [Full framework](README.md)

![VeriFirst: Trust Map and the cycle](assets/verifirst-en.svg)

**One rule:** design the work so that an AI mistake is easy to notice and cheap to fix.

## Before the task — 2 questions

1. **What does an unnoticed error cost?** Low / High
2. **How fast can it be verified?** Easy / Hard

| | Easy to verify | Hard to verify |
|---|---|---|
| **Low cost** | 🟢 **Delegate** — AI does it, spot-check | 🔵 **Explore** — AI gives options, you pick |
| **High cost** | 🟡 **Delegate + Review** — always verified before use | 🔴 **Advise** — AI advises, you decide |

Hard to verify? Split it, demand sources, prepare tests or reference examples first.

## Set the task — 6 lines

**Goal** · **Done criteria** (yes/no checks) · **Boundaries** (what must not be changed or invented) · **Inputs** · **Verifier** · **Output format**.
No Done criteria → not ready to delegate.

## Check the result — in a separate session or by another person

☐ Done criteria met ☐ Nothing invented (facts, sources, numbers, APIs) ☐ Logic and arithmetic ☐ Edge cases ☐ No unrequested changes ☐ No false confidence

Max 3 Make–Break rounds. Still failing → rewrite the task, not the result.

## Before acting

| R0 read | R1 local, reversible | R2 reversible with effort | R3 irreversible |
|---|---|---|---|
| free | free | backup or approval first | **always a human**, one action at a time |

## Remember and measure

- **Decision Log:** decision · reason · rejected options · revisit if. Feed it back to the AI.
- **TTV** — time until the result is verified, not until it is produced. Track **escaped errors**.

## Start tomorrow

1. Name the quadrant before every non-trivial AI task.
2. Write the Done criteria in one or two lines.
3. Never accept 🟡 or 🔴 output without a separate Break pass.

Make your AI follow these rules automatically: [AI instructions](ai-instructions/README.md).
