# CCSS v9.0 — Domain 2: Operations

Aspects 2.01–2.04 cover security testing, logging and monitoring, governance and risk, and key compromise preparedness.

Requirement text is reproduced verbatim from the CryptoCurrency Security Standard v9.0 (published 2024-12-17) by the CryptoCurrency Certification Consortium (C4), as published in the official table: <https://cryptoconsortium.org/ccss-table-v9/>. Where C4's Report on Compliance template v1.3 words a requirement differently, the table wins — see the Version and accuracy section of `SKILL.md` for the three known divergences. Quote requirement text exactly and cite the requirement ID; never paraphrase a requirement and present it as the standard's wording.

## Contents

- [2.01 Security Tests/ Audits](#201-security-tests-audits)
- [2.02 Log and Monitor](#202-log-and-monitor)
- [2.03 Governance and Risk](#203-governance-and-risk)
- [2.04 Key Compromise Documentation](#204-key-compromise-documentation)

## 2.01 Security Tests/ Audits

**Objective.** This aspect covers third-party reviews of the security systems, technical controls, and policies that protect the CCSS Trusted Environment from all forms of risk as well as vulnerability and penetration tests designed to identify paths around existing controls. Regardless of the technical skills, knowledge, and experience of personnel who build and maintain the CCSS Trusted Environment, it has been proven that third-person reviews often identify risks and control deficiencies that were either overlooked or underestimated by personnel. For the same reasons that development companies require different people to test a product from those who write it, different people than those who implement a cryptocurrency system should assess its security. Third parties provide a different viewpoint and are independent of the technical controls and can be objective without risk of retaliation.

*2 aspect controls — 4 × Level I, 1 × Level II, 1 × Level III.*

### 2.01.1 Security Development and Documentation

**2.01.1.1 (Level I)** — An individual(s) with expertise in information security must be engaged in all stages of the design, development, deployment, and ongoing maintenance of systems providing cryptocurrency functions.

**2.01.1.2 (Level II)** — A regular security assessment that includes vulnerability and penetration testing has been completed by an independent, qualified third-party. Documentation shows that all concerns raised by the assessment have been evaluated for risk and addressed by the entity.

**2.01.1.3 (Level III)** — A regular security audit at a level similar to SOC 2, ISAE3402, or ISO/IEC 27001, that includes vulnerability, penetration testing, and code audit (if applicable) has been completed by an independent qualified third-party. Documentation shows that all concerns raised by the audit have been evaluated for risk, addressed by the entity, and known vulnerabilities have been removed from the CCSS Trusted Environment. Ongoing audits are scheduled on a (minimum) yearly basis.

### 2.01.2 Smart Contract Software Code Audit Documentation

**2.01.2.1 (Level I)** — All smart contract software code versions deployed to the environment(s) where the entity stakeholders interact with the smart contract have been audited by an external third-party auditor skilled in the development languages used for the smart contract software. NOTE: the requirement is not applicable to any environments used for development, testing, or staging. This requirement applies to smart contracts deployed to the "production" network or the like.

**2.01.2.2 (Level I)** — All smart contract software code audit reports are accessible to the entity stakeholders. The audit reports cover the currently deployed versions to the environment(s) where the entity stakeholders interact with the smart contract. NOTE: the requirement is not applicable to any environments used for development, testing, or staging. This requirement applies to smart contracts deployed to the "production" network or the like.

**2.01.2.3 (Level I)** — All issues with a severity of medium or higher identified in a code audit of the smart contract software are addressed by the entity before deployment to the environment(s) where the entity stakeholders interact with the smart contract. NOTE: the requirement is not applicable to any environments used for development, testing, or staging. This requirement applies to smart contracts deployed to the "production" network or the like.

**Level II:** none.

**Level III:** none.

## 2.02 Log and Monitor

**Objective.** This aspect covers monitoring the CCSS Trusted Environment's technical components audit logs for suspicious activity. When suspicious activity is identified, alerts must be generated so that personnel can triage and respond to the event to detect and respond to suspicious activity proactively.

*4 aspect controls — 2 × Level I, 3 × Level II, 2 × Level III.*

### 2.02.1 Application Audit Logs

**2.02.1.1 (Level I)** — Audit trails exist for a subset of actions performed within the CCSS Trusted Environment.

**2.02.1.2 (Level II)** — All actions performed by all users within the CCSS Trusted Environment are logged. Audit logs are retained for at least one year in a trusted environment.

**Level III:** none.

### 2.02.2 Audit Log Backup

**Level I:** none.

**2.02.2.1 (Level II)** — In addition to recording all actions performed within the CCSS Trusted Environment, this audit information is periodically backed up to a separate server.

**2.02.2.2 (Level III)** — In addition to recording all actions performed within the CCSS Trusted Environment, this audit information is continually backed up to a separate server.

### 2.02.3 Audit Log Monitoring

**2.02.3.1 (Level I)** — The CCSS Trusted Environment's audit logs are monitored for suspicious activity, and alerts are generated when suspicious activity is detected. Appropriate personnel address the alerts generated. The monitoring frequency is defined by the entity and meets all components of requirement 2.03.2.1.

**2.02.3.2 (Level II)** — The CCSS Trusted Environment's audit logs are continuously monitored for suspicious activity, and alerts are generated in real time when suspicious activity is detected. Appropriate personnel address the alerts generated.

**Level III:** none.

### 2.02.4 Blockchain State Monitoring

**Level I:** none.

**Level II:** none.

**2.02.4.1 (Level III)** — Relevant blockchain state (confirmed and unconfirmed) as it relates to the CCSS Trusted Environment are continuously monitored for anomalous behavior, generating alerts. Appropriate personnel address the alerts that are generated.

## 2.03 Governance and Risk

**Objective.** This aspect covers the governance policies, standards, and procedures that guide and control an entity to ensure its CCSS Trusted Environment is effective, efficient, and secure. It also includes the requirements for a comprehensive risk management program to identify potential risks to the CCSS Trusted Environment and apply appropriate risk treatments.

*3 aspect controls — 3 × Level I, 1 × Level II, 0 × Level III.*

### 2.03.1 Governance

**2.03.1.1 (Level I)** — A member of executive management is responsible for the security of the system and formally acknowledges their responsibilities in writing.

**Level II:** none.

**Level III:** none.

### 2.03.2 Risk Management

**2.03.2.1 (Level I)** — The entity has identified security threats to the CCSS Trusted Environment and have defined and implemented controls to reduce the residual risk of an attack to an acceptable level using a threat model. The following considerations are addressed:
  1. The entity reviews the threat model periodically to ensure it is up-to-date, the controls currently implemented are still effective, and the risk of an attack is reduced.
  2. If a procedure requires a defined frequency to perform tasks for a control, such as reviewing audit logs, the threat model specifies the task frequency.

**2.03.2.2 (Level II)** — The entity implements a risk management program based on industry recognized risk management standards and frameworks such as ISO/IEC 27005 and NIST SP 800-37.

**Level III:** none.

### 2.03.3 Service Provider Management

**2.03.3.1 (Level I)** — Service provider management is implemented for any vendor or service provider that could impact the security of the CCSS Trusted Environment and addresses:
  1. Procurement processes to ensure any vendor or service provider meets applicable CCSS requirements before contractual engagement.
  2. Annual review of the vendor or service provider's compliance with applicable CCSS requirements. The frequency of review may increase from at least annually based on the entity threat model as defined in requirement 2.03.2.1.

**Level II:** none.

**Level III:** none.

## 2.04 Key Compromise Documentation

**Objective.** This aspect covers the existence and use of documented policies and procedures that define the actions that must be taken in the event key material or its operator/holder are believed to have become compromised. Entities must be prepared to deal with a situation where key material has - even potentially - become known, determinable, or destroyed. Policies and procedures to govern these events decrease the risks associated with lost funds and increase the availability of the system to its users. Examples of when a Key Compromise Policy (KCP) would be invoked include the identification of tampering of a tamper-evident seal placed on the media that stores key material, the apparent disappearance of an operator whose closest friends and family cannot identify their whereabouts, or the receipt of communication that credibly indicates an operator or key material is likely at risk of being compromised. The execution of KCP makes use of Approved Communication Channels to ensure KCP messages are only sent/received by authenticated actors.

*2 aspect controls — 2 × Level I, 1 × Level II, 1 × Level III.*

### 2.04.1 Key Compromise Policy Existence

**2.04.1.1 (Level I)** — An inventory of all key material exists and the entity has an awareness of which key material is critical to the successful operation of the CCSS Trusted Environment.

**2.04.1.2 (Level I)** — A Key Compromise Policy and procedures are documented. The following is addressed:
  1. Each specific classification of key material used throughout the CCSS Trusted Environment.
  2. A detailed plan of dealing with its compromise that includes the use of Approved Communication Channels during execution.
  3. Identities of actors via roles (not names), and includes secondary actors in the event any primary actor is unavailable to carry out the KCP.

**2.04.1.3 (Level II)** — The key material inventory is reviewed at least annually to ensure that all key material has been recorded and that the recorded information for key material is accurate and up-to-date.

**Level III:** none.

### 2.04.2 Key Compromise Policy Training and Rehearsals

**Level I:** none.

**Level II:** none.

**2.04.2.1 (Level III)** — The Key Compromise Policy and procedures are tested at least annually to ensure their viability and to ensure personnel remain trained to use them in the event of a compromise. The following is addressed:
  1. The testing exercise is documented and includes the attendees, scenarios tested, outcomes of testing, remediation required, actions, and the next testing date.
  2. Any improvements identified from the test are updated in the Key Compromise Policy and procedures.
  3. The testing includes ensuring backup(s) containing key material are reviewed and tested where applicable.
  4. Any changes to the system's people, processes, and technology components trigger a test of the Key Compromise Policy and procedures.
