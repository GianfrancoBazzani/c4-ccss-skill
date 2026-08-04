# c4-ccss-skill

An agent Skill that turns your agent into an accurate, quotable reference for the **CryptoCurrency Security Standard (CCSS) v9.0** by the [CryptoCurrency Certification Consortium (C4)](https://cryptoconsortium.org).

LLMs answering CCSS questions from memory produce plausible-sounding but wrong requirement IDs, levels, and wording. This skill fixes that by shipping the full standard and C4's audit documentation as local reference files, and instructing the agent to look requirements up and quote them verbatim instead of recalling them.

## Install

```bash
npx skills add GianfrancoBazzani/c4-ccss-skill
```

## What's inside

The `ccss` skill covers:

- **The standard itself** — all 10 aspects, 41 aspect controls, and 59 requirements verbatim across Levels I/II/III, split by domain (Cryptographic Asset Management 1.01–1.06, Operations 2.01–2.04), plus a requirement index that is the authority on which level every requirement sits at.
- **The certification process** — CCSSA/CCSSI/CCSSA-PR roles, peer review and independence rules, RoC/RRoC/SRoC/CoC documents, audit finding statuses, evidence types and IPE, trusted environment scoping, exams and renewal.
- **The official glossary** — C4's exact definitions of terms that change answers (Actor, Key Material, Trusted Environment, Comparable Control, …).
- **Engagement and fees** — C4 listing fees, fee structure, and what drives audit effort.
- **C4 primary sources** (`references/audit-documents/`) — the Auditor Guide 2025, the CCSS Audit Methodology Handbook, per-requirement testing procedures, and the RoC template, converted to markdown so they're greppable.
- **Published exam scenarios** (`references/exam-scenarios/`) — worked examples of how C4 constructs system descriptions.

## When it triggers

The skill activates whenever CCSS, CCSSA, CCSSI, CCSSA-PR, or C4 come up — and also on questions that don't name the standard, like:

- "What does Level II add for key material storage?"
- "What level is requirement 1.03.2.2?"
- "Does CCSS require multisig?"
- "Who can peer review a CCSS audit?"
- "How much does a CCSS listing cost?"
- "How do I test requirement 1.05.4.1 — what evidence do I need?"

Answers quote requirement text verbatim with the ID and level (e.g. "1.03.2.1 (Level I) — *A backup(s) of the operational key material exists.*"), so they can go straight into client-facing audit work.

## Version

Encodes **CCSS v9.0**, published 2024-12-17. Requirement text is reproduced verbatim from the [official CCSS table](https://cryptoconsortium.org/ccss-table-v9/), which wins whenever C4's own documents disagree.

## Attribution

Requirement text and audit documentation are the intellectual property of the CryptoCurrency Certification Consortium (C4), reproduced here for use in CCSS audit and implementation work. Attribute C4 and link the [official table](https://cryptoconsortium.org/ccss-table-v9/) when quoting substantially in anything client-facing.
