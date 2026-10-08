# Mapping to NIST AI RMF and ISO/IEC 42001

[Русская версия](../ru/standards-mapping.md) · [← Back to the framework](../../README.md)

This table shows which VeriFirst elements support the requirements of two widely used AI governance frameworks. It helps when talking to risk managers and auditors in their language.

> **Important.** This is an indicative mapping, not a compliance claim. VeriFirst does not make an organisation ISO/IEC 42001 certified and does not cover every NIST AI RMF category. The full text of ISO/IEC 42001 is paid; this mapping is based on the standard's structure and public descriptions. Check the primary sources before an audit.

## The two frameworks in brief

- **NIST AI RMF 1.0** (NIST AI 100-1, January 2023) — a voluntary AI risk-management framework from the US NIST. Its core has four functions: GOVERN, MAP, MEASURE and MANAGE, each split into categories ([primary source](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf)).
- **ISO/IEC 42001:2023** — the international, certifiable standard for AI management systems. Its mandatory requirements are clauses 4–10 in the common ISO structure (context, leadership, planning, support, operation, performance evaluation, improvement). Annex A provides a reference set of controls A.2–A.10 ([structure](https://urmconsulting.com/faq/how-is-iso-42001-structured), [Annex A control groups](https://docs.modulos.ai/frameworks/iso-42001/annexes-a-d.html)).

## Element mapping

| VeriFirst element | NIST AI RMF | ISO/IEC 42001 |
|---|---|---|
| **Trust Map** (triage by cost of error and verifiability) | MAP 1 (context), MAP 2 (system categorisation), MAP 5 (impacts), MANAGE 1 (risk prioritisation) | Clause 6 (planning, risk assessment), A.5 (assessing impacts of AI systems) |
| **Intent Contract** (goal, criteria, boundaries) | MAP 1 (intended purpose and context), MAP 3 (goals and expected benefits) | A.6 (life cycle: requirements), A.9 (intended use) |
| **Make–Break** (independent verification) | MEASURE 1 (methods and metrics), MEASURE 2 (trustworthiness evaluation) | A.6 (verification and validation), clause 9 (performance evaluation) |
| **Decision Log** | GOVERN 1 (policies and documentation), MANAGE 4 (documented risk treatment plans) | Clause 7 (documented information), A.8 (information for interested parties) |
| **Reversibility Gates R0–R3** | GOVERN 2 (roles and accountability), MANAGE 1–2 (risk response) | Clause 8 (operation), A.3 (roles and authority), A.9 (responsible use) |
| **Metrics** (TTV, escaped errors) | MEASURE 3 (tracking risks over time), MEASURE 4 (feedback on measurement efficacy) | Clause 9 (monitoring and measurement), clause 10 (improvement) |
| **Company policy** ([scaling](scaling.md)) | GOVERN 1 (policies), GOVERN 4 (risk-aware culture) | Clause 5 (leadership and policy), A.2 (policies related to AI) |
| **AI system register** | GOVERN 1, MAP 2 | Clause 4 (context and scope of the management system), A.5 |
| **Verifiability owner** | GOVERN 2 (accountability) | A.3 (internal organisation) |
| **Contracts at team and supplier interfaces** | GOVERN 6, MANAGE 3 (third-party risks) | A.10 (third-party and customer relationships) |

## What VeriFirst does not cover

VeriFirst focuses on verifying AI output in everyday work. A complete AI governance programme also needs:

- **Fairness and inclusion** — NIST GOVERN 3 and the trustworthiness characteristics in MEASURE 2 (bias, privacy, security).
- **Data for AI systems** — data quality, provenance and preparation (ISO A.7).
- **Resources** — compute, tooling, competence (ISO A.4, clause 7).
- **Stakeholder engagement** — NIST GOVERN 5, ISO A.8 for external reporting.
- **A formal management system** — internal audit, management review, statement of applicability (ISO clauses 9–10).

## Sources

- [NIST AI 100-1: Artificial Intelligence Risk Management Framework (AI RMF 1.0)](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf), NIST, January 2023
- [How is ISO 42001 structured](https://urmconsulting.com/faq/how-is-iso-42001-structured), URM Consulting
- [ISO 42001 Annexes A–D](https://docs.modulos.ai/frameworks/iso-42001/annexes-a-d.html), Modulos

Checked: 8 October 2026.
