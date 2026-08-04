# CCSS engagement scoping, fees, and OpenZeppelin service mapping

Commercial and delivery-side knowledge: what an audit costs, what drives the effort, and which OpenZeppelin services map onto which requirements.

## Contents

- [CCSS engagement scoping, fees, and OpenZeppelin service mapping](#ccss-engagement-scoping-fees-and-openzeppelin-service-mapping)
  - [Contents](#contents)
  - [Fee structure](#fee-structure)
  - [C4 listing fees](#c4-listing-fees)
  - [What drives audit effort](#what-drives-audit-effort)
  - [Peer review cost](#peer-review-cost)
  - [Target customers](#target-customers)
  - [OpenZeppelin services mapped to requirements](#openzeppelin-services-mapped-to-requirements)
    - [Non-CCSS-specific services required to pass an audit](#non-ccss-specific-services-required-to-pass-an-audit)
    - [CCSS-specific services](#ccss-specific-services)

## Fee structure

Audit fees are set between the CCSSA and the audited entity. The CCSSA is responsible for ensuring the agreed fee reflects enough time to actually complete the audit, and the fee must also cover the CCSSA-PR's fee and C4's listing fee. The CCSSA forwards the peer reviewer's fee to them; C4 invoices the CCSSA for the listing fee after approving the SRoC.

Breakdown:

1. **Readiness (GAP) assessment** — CCSSI or CCSSA billable time to evaluate system readiness. A fixed number of billable hours for a high-level review of the people, processes, and technology components. The fee should cover the time to *identify* that measures are implemented and documentation exists — not the time to review them in depth.
2. **Audit** — CCSSA billable time to apply evidence-gathering techniques, review the results, and produce the RoC. Covers reviewing system documents, interviewing personnel, inspecting configurations, and observing processes to confirm they match documentation.
3. **Peer review** — CCSSA-PR billable time.
4. **C4 listing fee** — see below.

This breakdown covers audit fees only. Any preparation or remediation work an implementer does beforehand is separate.

## C4 listing fees

Charged annually by C4 to list the certified system in the CCSS Certified Systems List.

| | Self Custody | Qualified Service Provider | Full System |
| --- | --- | --- | --- |
| **Definition** | Systems that hold all keys to the system that controls the entity's own funds. | A system that meets many of the requirements for CCSS certification with the exception of the few requirements that another system has control over. A QSP facilitates a subset of custody services to other systems and therefore is only required to meet certain requirements. If a system uses a QSP, the audit focus is only on the few remaining requirements to become certified. | An information system that meets all applicable CCSS requirements in totality. Where a system uses a CCSS certified QSP (e.g. a wallet infrastructure provider's wallet software), some requirements may be met by the QSP system, as determined by the CCSSA. |
| **Examples** | A Web3 marketing firm that accepts cryptocurrency and controls the private keys for the system used to control their funds. | An HSM or MPC system providing key management services used by another entity's system. | A system that can reach quorum without any additional system. An exchange that incorporates a QSP into their system. |
| **Listing fee (annual)** | **$250** | **$2,000** | **$3,500** |

Discounts and multi-system rules:

- When multiple systems (up to 3) are covered in the same audit, C4 charges only the listing fee of the **most expensive** system.
- When auditing 4–6 systems, C4 charges only the **two most expensive** systems' fees, and so on in that pattern.
- Systems that **maintain** a Certificate of Compliance receive a **25% discount** on the annual listing fee.

## What drives audit effort

Audit effort is determined at the scoping stage by the boundaries of the **CCSS Trusted Environment**. The entity defines it; the CCSSA verifies it covers all people, processes and technology components that are key management systems, plus anything else that could impact their security.

Not identifying scope before the audit means the CCSSA ends up defining it during the audit — extra effort, time and cost, and a worse engagement for everyone. The [CCSS Audit Methodology Handbook](audit-documents/CCSS-Audit-Methodology-Handbook.md) covers Trusted Environment scoping in depth.

Effort scales with the number of distinct key management systems, the number of in-scope roles to interview, geographic distribution of key material and personnel, and the target level (Level III adds documented key generation ceremonies, DRBG conformance evidence, geographic and entity key distribution, and audited media sanitization).

## Peer review cost

The CCSSA-PR is an independent CCSSA drawn from a randomised PROL supplied by C4, so the peer reviewer cannot be from the same organization as the CCSSA. That makes part of the audit budget variable and outside the CCSSA's control.

How to handle it commercially:

- Tell the customer up front that an additional charge applies for peer review.
- The exact amount is unknown at engagement time, but it **can be capped** — communicate the maximum the auditor is willing to cover.
- The standard review price is typically fixed.
- Budget **10–15 hours** of reviewer effort, plus **1–2 hours** for re-review if changes are required.
- For a CCSSA's first peer review, the reviewer is typically a CCSS Steering Committee member; auditors may be introduced by email to confirm availability.

## Target customers

Any project or company whose system makes use of cryptocurrencies — exchanges, web applications, custodians, and cryptocurrency storage solutions.

Remember that **systems are certified, not entities**, so a single customer may represent several certifiable systems (and therefore several engagements). Fireblocks is the canonical example, with four separately certified systems.

## OpenZeppelin services mapped to requirements

Which OZ offerings satisfy which CCSS requirements. Useful when scoping what an entity still needs before it is audit-ready.

**Note on independence:** a CCSSA must avoid any conflict of interest and must not audit their own work. If OZ delivers implementation or advisory services against these requirements, the OZ auditor who did that work cannot be the CCSSA for that system. Keep the implementer and auditor engagements staffed separately.

### Non-CCSS-specific services required to pass an audit

**Advisory to design and implement key management policies, standards, key ceremony reports, runbooks, access management policies and procedures, plus training:**

- Level I (20): 1.01.1.1, 1.01.1.2, 1.01.4.1, 1.03.1.1, 1.03.2.1, 1.03.3.1, 1.03.4.1, 1.04.1.1, 1.05.1.1, 1.05.2.1, 1.05.2.2, 1.05.3.1, 1.05.4.1, 1.05.5.1, 1.05.6.1, 1.05.9.1, 1.05.10.1, 1.06.1.1, 2.04.1.1, 2.04.1.2
- Level II (13): 1.01.1.3, 1.01.2.1, 1.01.2.2, 1.02.1.1, 1.02.2.1, 1.02.3.1, 1.02.5.1, 1.03.2.2, 1.03.3.2, 1.03.5.1, 1.04.2.1, 1.05.8.1, 2.04.1.3
- Level III (8): 1.01.3.1, 1.01.3.2, 1.02.4.1, 1.03.6.1, 1.04.3.1, 1.05.1.2, 1.06.2.1, 2.04.2.1

- **Advisory and training** to give the entity internal security expertise: 2.01.1.1
- **Smart contract audits and/or pentesting**: 2.01.1.2, 2.01.2.1, 2.01.2.2, 2.01.2.3
- **Advisory to design and implement logging mechanisms**: L1 2.02.1.1; L2 2.02.1.2, 2.02.2.1; L3 2.02.2.2
- **Advisory to design and implement monitoring and incident response**: L1 2.02.3.1; L2 2.02.3.2; L3 2.02.4.1
- **Threat analysis and modeling** (ISO/IEC 27005, NIST SP 800-37): 2.03.2.1, 2.03.2.2

**Requirements no OZ service line above addresses** — the entity must handle these itself, so flag them early in scoping: **1.05.7.1** (key management responsibilities formally acknowledged in writing), **2.01.1.3** (annual SOC 2 / ISAE3402 / ISO 27001-level third-party audit), **2.03.1.1** (governance), **2.03.3.1** (service provider management).

### CCSS-specific services

- CCSS Implementer (CCSSI) service
- CCSS Audit Readiness Assessment service
- CCSS Auditor (CCSSA) service
- CCSS Auditor Peer Reviewer service, when drawn from another auditor's PROL
- CCSS re-audit retainers (certification requires an annual audit, so re-audits are recurring revenue by design)
