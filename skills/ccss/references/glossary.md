# CCSSA glossary

Terms as defined by C4 for CCSS auditors. Source:
<https://cryptoconsortium.org/cryptocurrency-security-standard-auditor-ccssa-glossary/>

These definitions are load-bearing. Several CCSS requirements turn entirely on a
defined term — for example "Regularly" means *annually*, not "often", so an entity
doing something quarterly satisfies it and one doing it "when we remember" does not.
When a question hinges on a word that appears here, quote the definition.

## Frequency and qualifier terms

These are the ones most often misread.

| Term | Definition |
| --- | --- |
| **Regularly** | Annually. |
| **Periodically** | As determined sufficient by the auditor. |
| **Continually** | Constant and uninterrupted activity or presence. |

## Audit and process terms

| Term | Definition |
| --- | --- |
| **Audit Documentation** | The record of audit procedures performed, relevant audit evidence obtained, and conclusions the auditor reached. |
| **CCSSA** | CryptoCurrency Security Standard Auditor. |
| **CCSSA-PR** | CryptoCurrency Security Standard Auditor Peer Reviewer. |
| **CoC** | Certificate of Compliance. |
| **CoC Listing information** | Entity website, contact details, audited system, associated fees, and logo at minimum 500×500 pixels. |
| **Entity** | The body controlling systems undergoing audit. Used interchangeably with Organization. |
| **Organization** | The body controlling audited systems. Used interchangeably with Entity. |
| **Listing Fee** | Cost paid to C4 by the CCSSA for each completed audit, covering website listing and provision of compliance documentation. |
| **PROL** | Peer Review Options List. |
| **RoC** | Report on Compliance. |
| **Redacted RoC** | Audit report with all sensitive information and personally identifiable information removed. |
| **SRoC** | Summary Report on Compliance. |
| **Comparable Control** | Entity-implemented control providing equivalent protection to CCSS-defined controls. |
| **Qualified for In-Place** | Demonstrated process meets requirements within system control, qualifying for implementation by consumer systems. |
| **Not Applicable** | Requirement designation when it doesn't apply to the assessed environment, with documented evidence of inapplicability. |

## System type terms

| Term | Definition |
| --- | --- |
| **Self Custody** | Systems holding all keys controlling the entity's own funds. |
| **Qualified Service Provider (QSP)** | System meeting many CCSS requirements except those under another system's control. C4's glossary lists **QSP** as a separate entry abbreviating the same term. |
| **Full System** | Information system meeting all applicable CCSS requirements in totality. |
| **Service Provider** | Individual or organization delivering specialized services or functions. |
| **Clients Assets Custodied** | Total assets held by the entity on clients' behalf as determined at audit start. |
| **Entity Stakeholders** | Individuals or groups with vested interest in organizational operations or security. |

## Key material and cryptography terms

| Term | Definition |
| --- | --- |
| **Actor** | Any entity involved in key generation, management, or operations with the ability to impact key material security. |
| **Operator** | Individual involved in key management and operations, though not necessarily accessing actual key material. |
| **Key Holder** | Person, organization, system, or service making direct use of cryptographic key or seed material. |
| **Key** | Private key material or seed phrases that must remain confidential to prevent unauthorized asset access. |
| **Key Material** | Parameters used to derive or represent cryptographic keys, including seeds and key shares. |
| **Key Creation** | Process of generating cryptographic keys. |
| **Key Generation** | Cryptographic process creating key material such as seed phrases or private key pairs. |
| **Seed** | Entropy slice initializing PRNGs or other cryptosystems like HD wallets. |
| **Entropy** | Randomness, usually collected from hardware, environmental factors (time of execution), or external sources (user-input). |
| **Entropy Pool** | Collection of inputs providing unguessable output for cryptographic operations. |
| **Pseudo-Random Number Generator (PRNG)** | Algorithm producing cryptographically difficult-to-guess values, typically seeded with entropy. |
| **Deterministic Random Bit Generator (DRBG)** | PRNG producing multiple values from a single seed. |
| **Digital Signature** | Mathematical scheme verifying message authenticity and integrity. |
| **Strong Encryption** | Industry-standard encryption requiring estimated global computing power and 1,000× more time than the key's lifespan. |
| **Address** | Encoded form of a public key usable as transaction recipient in cryptocurrency systems. |
| **Wallet** | Public-private keypair collection managing numerous keypairs, either JBOK or hierarchical deterministic type. |
| **Hierarchical Deterministic Wallet** | Wallet using secure key derivation to create numerous unique addresses from a single master seed. |
| **Single-Signer** | Digital signature scheme requiring only one piece of key material for transaction authorization. |
| **Multi-Signer** | Security feature requiring multiple key material signers for a valid transaction signature. |
| **Geographic Locations** | Distinct physical locations reducing single-point-of-failure risk through distributed key material. |
| **Destruction** | Sanitization method rendering data recovery infeasible using state-of-the-art techniques. |

## Access, environment, and governance terms

| Term | Definition |
| --- | --- |
| **Trusted Environment** | Physical location, hardware, and software used in private key-related operations. |
| **Production Environment** | Live operational environment where finalized systems operate with real-world interactions. |
| **Operating System** | Software controlling hardware to enable user and application program operation. |
| **Approved Communication Channels** | Channels providing high confidence of communicator identities through voice verification, digital signatures, or multiple separate channels. |
| **Factor of Authentication** | Multiple identity demonstrations required for access, including passwords, tokens, or biometrics. |
| **One-Time Password** | Token valid for single use only; security depends on delivery channel and generation system. |
| **Identity Verification** | Tiered process confirming authenticity of actor identity claims through documentation and verification services. |
| **Least Privilege Principle** | Security principle restricting user access privileges to the necessary minimum for assigned tasks. |
| **Policy** | Formalized statement or document that outlines an organization's approach and commitments to securing its assets, data, and operations. |
| **Procedure** | Specific actions implementing security policies, providing operational instructions for secure task performance. |
| **Key Compromise Policy** | Procedures and actions responding to suspected or confirmed cryptographic key material exposure. |
| **Threat Model** | Process identifying, communicating, and understanding threats and mitigations protecting something valuable. |
| **Suspicious Activity** | Anomalous behavior identified through monitoring, deviating from established norms or protocols. |
| **Protocol** | Predefined rules dictating data transmission and component interaction in a standardized manner. |
| **Smart Contract** | Program or code that autonomously executes predefined rules and agreements when specific conditions are met. |
