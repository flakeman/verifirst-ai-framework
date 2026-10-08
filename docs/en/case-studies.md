# Case studies: VeriFirst in practice

[Русская версия](../ru/case-studies.md) · [← Back to the framework](../../README.md)

Real situations from the author's work with AI: rolling out AI in an IT team on a 1C (ERP) project, and his own product projects. Company names, internal systems and people are removed. Each case shows which VeriFirst element worked, or would have.

---

## Case 1. AI analyst for 1C: stopping the AI from inventing object names

**Task.** Requests from users and methodologists arrived in free form. To turn them into a developer task, an analyst had to dig through the 1C configuration source code by hand. It was slow, and task quality varied.

**Risk.** An AI agent writing a task card can confidently name a catalogue, attribute or module that does not exist in the configuration. A developer then wastes time looking for it — or, worse, the card goes into work with the error. On the Trust Map this is 🔴: the error is costly and checking every name by hand is hard.

**What was done.** The agent was connected to the 1C source code through an MCP server, and it checks every object name against the real code. The agent works by a set of rules, a glossary and a register of changes; each card contains analysis, a draft solution and separate questions for the developer and the architect.

**VeriFirst element.** Moving the task to a better quadrant: name checking became automatic, shifting the task from 🔴 to 🟡. The "questions for the developer and architect" section is the open questions the AI does not fill in by itself. The glossary and the change register act as a decision log.

**Result.** 38 change cards prepared through the agent, each tied to real configuration objects.

---

## Case 2. Product catalogue matching: verifiability on a control sample

**Task.** During a migration between 1C configurations, short product names from stock balances had to be matched against a reference catalogue of 41,000 items. By hand this took about 5 hours per site.

**What was done.** First a Python prototype, tested on pilot data with known correct answers: 247 of 248 items matched (99.6%). Only then a web service (FastAPI, Docker, CI/CD) with a user guide.

**VeriFirst element.** The done criterion was measurable before scaling: the share of correct matches on a control sample. This is 🟡 — a catalogue error is costly, but the result is easy to check against the reference.

**Result.** The work went from 5 hours to 30 minutes.

---

## Case 3. An off-spec architecture the AI did not flag

**Task.** Project documentation (DDD, architecture) for the author's own product, based on a detailed specification.

**What went wrong.** The AI proposed a monolithic architecture although the specification explicitly required microservices — and did not flag it as a deviation. The author spotted the mismatch himself, in comments on the document.

**What was done.** The AI built a "specification requirement → what was built" table. The author went through it row by row and decided each one: microservices, escrow without blockchain, a mandatory anti-fraud minimum, and so on. The document was rewritten around those decisions.

**VeriFirst element.** Boundaries in the Intent Contract ("do not deviate from the spec without an explicit flag") and the decision-log rule: if a proposal contradicts a recorded requirement, the AI must say so explicitly. The row-by-row table is a Break pass against the specification.

**Lesson.** The most expensive AI errors are not typos but silent deviations from what was agreed.

---

## Case 4. An official document with an invented fact

**Task.** Turn a document template into an order putting a system into operation.

**What went wrong.** The AI wrote in the preamble that a pilot operation had been successfully completed. There was no pilot: the boxed version was deployed straight onto an internal server and put into use. The author caught it while proofreading.

**Why it matters.** A signed order is R3: correcting it after signature is expensive. A plausible detail typical of such documents easily survives a quick read.

**VeriFirst element.** The boundary "do not invent facts about the project's history" and the "Unverified" section in the AI's answer. The R3 gate: a document for signature is checked by a person who knows the facts.

---

## Case 5. A CV: the right format and honest assumptions

**Task.** Describe AI projects in a CV form for a recruiter.

**What went wrong.** The first version listed capabilities, but the format needed was "problem → solution → result". The done criterion had not been stated up front, so an extra round of edits was needed.

**What worked.** In the second version the AI explicitly noted that it had inferred the problem statements for two projects from their content rather than from the author's words, and asked for them to be checked. It also warned that a recruiter may ask to back up the figures.

**VeriFirst element.** Done criteria in the Intent Contract save an iteration. The "Assumptions" and "Unverified" sections turn the AI's hidden guesses into visible questions.

---

## Case 6. An AI agent in a task tracker: Definition of Done as a gate

**Task.** An AI agent should pick up tasks from the tracker on its own, but must not hand over unfinished work or get stuck in loops.

**What was done.** The agent takes a card from the Ready column, checks its template, does the work, runs the tests and moves it to Review only when the Definition of Done checklist is fully closed. Final acceptance stays with a human. Protection against duplicates and loops was added.

**VeriFirst element.** Automated checks are part of the Break pass, but acceptance remains human. Loop protection corresponds to the iteration limit in the Make–Break loop.

---

## Takeaways

1. **AI most often fails not on the hard parts but on the plausible ones:** object names, "typical" facts, familiar architecture choices.
2. **The best defence is making verification automatic or measurable** (checking against source code, a control sample, tests), not asking the AI to "be more careful".
3. **Deviations from agreements must be caught explicitly:** a "requirement → built" table and a decision log.
4. **Before anything irreversible** (signing, publishing, sending), the result is checked by a person who knows the facts.
