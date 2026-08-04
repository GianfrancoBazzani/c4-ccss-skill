---
name: ccss
description: >-
  Authoritative knowledge base for the CryptoCurrency Security Standard (CCSS) v9.0 by the CryptoCurrency Certification Consortium (C4) — all 10 aspects, 41 aspect controls and 59 requirements verbatim across Levels I/II/III, plus the certification process, CCSSA/CCSSI/CCSSA-PR roles, peer review and independence rules, RoC/RRoC/SRoC/CoC documents, audit finding statuses,  the official glossary, and C4 listing fees.
  Use this skill whenever CCSS, CCSSA, CCSSI, CCSSA-PR, C4, "CryptoCurrency Security Standard", or "CryptoCurrency Certification Consortium" appear, and also when someone asks — without naming the standard — about crypto custody certification levels, what Level I/II/III demands, key material generation/storage/access/usage requirements, key compromise policies, wallet generation or geographic key distribution rules, CCSS trusted environment scoping, what a Report on Compliance contains, who can peer review an audit, how much a CCSS listing costs, or how to become a certified CCSS auditor or implementer. Consult it even for questions that sound simple, such as "what level is requirement 1.03.2.2" or "does CCSS require multisig" — answering CCSS from memory produces plausible-sounding but wrong requirement IDs, levels and wording, and this skill exists to make answers quotable.
allowed-tools:
  - Read
  - Grep
  - Glob
  - WebFetch
---

# CryptoCurrency Security Standard (CCSS) v9.0

CCSS is C4's security standard for information systems that use cryptocurrencies — exchanges, custodians, wallets, web applications, storage solutions. It complements rather than replaces general information security standards: following CCSS while ignoring something like ISO/IEC 27001 will likely still lead to compromise.

Your job with this skill is to answer CCSS questions **accurately and quotably**. Requirement IDs, levels, and wording are easy to half-remember and get subtly wrong, so look them up rather than recalling them.

## How to answer

**Read the relevant reference file before answering.** Not "if unsure" — the failure mode this skill prevents is confident recall of a requirement that reads almost right but cites the wrong ID or the wrong level. `references/requirement-index.md` is small; start there to locate what you need, then open the domain file for exact text.

**Quote requirement text verbatim and cite the ID.** Write "1.03.2.1 (Level I) — *A backup(s) of the operational key material exists.*" rather than "CCSS requires you to back up your keys". Auditors need the standard's actual words because those words are what they test against, and a requirement that sounds right but reads differently is worse than no answer. Paraphrase freely when *explaining*, but mark clearly when you are explaining versus quoting.

**Check `references/glossary.md` when a question turns on a defined word.** CCSS defines terms in ways that change answers: Actor, Key Material, Approved Communication Channels, Trusted Environment and Comparable Control — the glossary carries C4's exact wording for all of these, so quote it from there rather than paraphrasing from memory.

**Separate the standard from the process.** "What does CCSS require for key backups?" is a requirements question. "Who signs Appendix I?" is a process question. They live in different files and mixing them produces vague answers.

**Say when something isn't in the standard.** CCSS is narrower than people expect — it has nothing to say about many things auditors get asked. "CCSS v9.0 has no requirement covering X; the closest is Y, which addresses Z" is a better answer than stretching a requirement to fit.

**Don't infer controls from silence.** If someone describes a system and a control simply isn't mentioned, that is not evidence the control exists. This is exactly how C4's own exam scenarios are constructed, and it is how real audits work — a CCSSA must evidence what is in place, and must evidence inapplicability before marking anything Not Applicable.

## The structure of the standard

The standard is built on top of three levels of granularity, CCSS defines a set of security **Requirements** across three compliance levels (Level I, II, and III), where each level builds on the previous with increasingly strict controls. Each requirement refers to a specific **Aspect Control**, which are organized by **Aspects**.

| Unit | What it is | Example |
| --- | --- | --- |
| **Aspect** | The broadest unit — it represents a security topic or domain, with an objective explaining *why* it matters. | `1.01 Key Material Generation` |
| **Aspect Control** | A specific security measure within an aspect, targeting one specific sub-problem within that aspect. | `1.01.1 Actor-generated Key Material` |
| **Requirement** | A concrete, verifiable action an organization must implement to satisfy a given control, and they vary by Level (I, II, III). Each requirement gets progressively stricter. | `1.01.1.1` (Level I) |

CCSS v9.0 (published 2024-12-17, [official table](https://cryptoconsortium.org/ccss-table-v9/)) contains:

- **10 aspects**, in two domains — Cryptographic Asset Management (1.01–1.06) and Operations (2.01–2.04)
- **41 aspect controls** — this is the number C4 quotes, and the certification exams cover all 41
- **59 requirements** — 30 Level I, 18 Level II, 11 Level III

| Aspect | Name | Controls |
| --- | --- | :---: |
| 1.01 | Key Material Generation | 4 |
| 1.02 | Wallet Generation | 5 |
| 1.03 | Key Material Storage | 6 |
| 1.04 | Key Material Access | 3 |
| 1.05 | Key Material Usage | 10 |
| 1.06 | Data Sanitization Documentation | 2 |
| 2.01 | Security Tests/Audits | 2 |
| 2.02 | Log and Monitor | 4 |
| 2.03 | Governance and Risk | 3 |
| 2.04 | Key Compromise Documentation | 2 |

## How levels work

**Levels are cumulative.** Level II means all applicable Level I *and* Level II requirements. Level III means all three tiers. A requirement's level tag says when it *first* applies, not that it stops applying higher up.

**A control with no requirement at a level imposes nothing extra there.** Most aspect controls have requirements at only one or two levels. `1.01.4 Entropy Pool` has a single Level I requirement; satisfying it carries that control all the way up. The "Aspect controls with no requirement at a given level" table in `references/requirement-index.md` shows this at a glance.

**The system certifies at the lowest level achieved by any aspect control.** This is the rule with the sharpest consequences: CCSS is a weakest-link standard. One Level I requirement found Not In-Place anywhere across the 41 controls caps the entire system below Level I, no matter how strong everything else is. When someone asks "what level would this system get", the answer is driven by their worst control.

**Not Applicable is a determination, not an omission.** A requirement can be marked Not Applicable when it genuinely does not apply to the environment — but the CCSSA must provide evidence that testing confirmed the environment does not support or provide a facility meeting the requirement's intent.

## What gets certified

**Systems are certified, not entities.** One company can hold several certification for several systems. Fireblocks, for instance, has four separately certified systems. This matters commercially and in scoping conversations.

Three system types — Self-Custody (holds keys to the entity's own funds only), Qualified Service Provider (facilitates a subset of custody services to other systems, so only needs to meet certain requirements), and Full System (meets all applicable requirements, possibly leaning on a certified QSP for some). Details, examples, and the listing-fee consequences are in `references/certification-process.md` and `references/engagement-and-fees.md`.

## Where to look

| Question is about | Read |
| --- | --- |
| Finding a requirement ID, its level, or which control/aspect it belongs to; counts and totals; which levels a control touches | `references/requirement-index.md` |
| Exact wording of requirements 1.xx — key material generation, wallet generation, storage, access, usage, data sanitization; aspect objectives | `references/requirements-domain-1-cryptographic-asset-management.md` |
| Exact wording of requirements 2.xx — security tests/audits, log and monitor, governance and risk, key compromise | `references/requirements-domain-2-operations.md` |
| Certification flow, CCSSA/CCSSI/CCSSA-PR roles, peer review rules, independence and conflict of interest, RoC/RRoC/SRoC/CoC, audit finding statuses, evidence types and IPE, trusted environment scoping, exams and renewal | `references/certification-process.md` |
| Defined terms and their exact C4 definitions | `references/glossary.md` |
| Listing fees, fee structure, what drives audit effort, peer review cost, OpenZeppelin service-to-requirement mapping | `references/engagement-and-fees.md` |
| How to *test* a specific requirement — which evidence to review, inspect, observe, and who to interview, per requirement ID | `references/audit-documents/CCSS v9 Testing Procedures for Course.md` |
| Anything the curated files summarise but don't answer in full — the primary C4 sources | `references/audit-documents/` (see below) |
| Published exam scenarios, and worked examples of how C4 constructs a system description | `references/exam-scenarios/` |

The two domain files are the large ones — use the index or `Grep` to jump to the right section rather than reading them end to end.

**`references/audit-documents/` holds C4's primary sources**, converted to markdown so they are greppable. The curated files above are summaries of these; go to the source when a question needs more depth than a summary carries, or when the user is actually doing the work rather than asking about it:

- `CCSS v9 Testing Procedures for Course.md` — per-requirement testing procedures, one section per requirement ID. This is what a CCSSA actually works from when planning evidence gathering.
- `Auditor-Guide-2025.md` — audit process, IPE, sampling methodology (including sample sizes by population), peer review mechanics, professional ethics, audit flow.
- `CCSS-Audit-Methodology-Handbook.md` — how to scope the Trusted Environment, how to write up findings in the RoC, worked examples of acceptable and unacceptable reporting.
- `CSSAA Auditor Course- RoC_9_CCSS_Report-on-Compliance_Template (required).md` — the RoC template's structure and every field an auditor fills in. The `.docx` alongside it is the working file; the `.md` is for reading.
- The SRoC template is present as `.docx` only, so it cannot be read directly — describe it from `references/certification-process.md` rather than guessing at its fields.

**`requirement-index.md` is the authority on levels.** The engagement file contains a service-to-requirement mapping derived from internal OZ material, and derived lists drift — an ID can sit under the wrong level heading, or name a requirement that no longer exists. If any other file disagrees with the index about which level a requirement sits at, the index wins. When you reproduce a list of IDs from anywhere, check the levels against the index first, because a copied list carries its errors into whatever the auditor sends the client.

## Answer shape

Match the question. A level lookup deserves one line; "walk me through what Level II adds for key storage" deserves structure.

Length is a real cost here. Auditors ask these questions mid-task, often while drafting something for a client, and a thorough answer they have to mine for the one fact they needed is worse than a short one. When the question is narrow or the user signals haste ("quick one", "just need to know if…"), lead with the answer in one or two sentences and stop. Add the surrounding detail only when it changes what they should do — a caveat that flips the conclusion earns its space; background on the aspect's objective usually does not. If you find yourself writing a fourth section, ask whether the user asked a fourth question.

Some patterns that work:

**Single requirement lookup** — give the ID, level, aspect control, verbatim text, and one line of practical reading if it helps.

> **1.03.2.2 (Level II)** — aspect control *1.03.2 Key Material Backup(s)*, aspect *1.03 Key Material Storage*.
>
> "<verbatim text>"
>
> In practice this means …

**"What does Level N require for X?"** — list every requirement at that level *and below* for the relevant aspect controls, since levels are cumulative. Note explicitly where a control adds nothing at that level.

**"Would this system pass?"** — the user chose a knowledge skill, not an assessment one, so answer by laying out which requirements are engaged and what each demands, and let them make the determination. If they describe a system, point out which requirements their description doesn't address rather than assuming pass or fail.

**Process questions** — answer directly and cite the constraint, e.g. "A CCSSA-PR cannot peer review the same entity again for three years after their initial peer review of that entity."

## Version and accuracy

This skill encodes **CCSS v9.0**, published 2024-12-17. Requirement text is reproduced verbatim from the published table at <https://cryptoconsortium.org/ccss-table-v9/>, which is the authority when C4's own documents disagree, and every requirement ID, level and wording in the two domain files has been checked against it.

C4's Report on Compliance template v1.3 words three requirements differently from the table — 1.05.1.2 ("Access to Key Material" vs the table's "Access to the operational key material"), 1.05.4.1 ("All actors" vs "All individual actors"), and 1.06.1.1 ("NIST 800-88" vs "NIST SP 800-88"). The domain files follow the table. If an auditor is quoting from a RoC they are filling in and the wording looks off, this is why; say so rather than assuming one side is a typo.

If a question depends on the current version being v9.0 — or if the user suggests a newer version exists — check <https://cryptoconsortium.org/ccss-table-v9/> and say plainly that the skill's content is v9.0 rather than guessing at changes.

Requirement text is C4's intellectual property, reproduced here for use in CCSS audit and implementation work. Attribute C4 and link the official table when quoting substantially in anything client-facing.
