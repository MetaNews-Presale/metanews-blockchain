# MetaVerify Attestations

*Last updated: March 2025*

---

## 🔍 Overview

**MetaVerify Attestations** enable organizations to issue official, on-chain confirmations of employment, partnerships, and affiliations on the **MetaNews Blockchain**.  

These attestations connect verified wallets to organizations, roles, and social handles — creating a tamper-proof and transparent network of trust.  
Each attestation can be **revoked**, **updated**, or **disputed**, ensuring all data remains accurate and auditable.

---

## 🧭 Objective

- Establish a verifiable and immutable system for organizational attestations.  
- Eliminate spoofed partnerships, fake representatives, and unverifiable staff claims.  
- Build an open, on-chain registry of trusted organizations and individuals.  
- Enable real-time updates, revocations, and disputes with full transparency.

---

## 🧩 Core Smart Contracts

| Contract | Purpose |
|-----------|----------|
| **OrgRegistry** | Registers and manages organizations, controllers, and verified domains. |
| **AttestationHub** | Manages wallet ↔ organization ↔ social handle relationships. |
| **EndorsementLedger** *(optional)* | Enables endorsements or peer-backed trust signals. |

---

## 🏢 OrgRegistry Structure

Each organization record contains:

| Field | Description |
|--------|-------------|
| `orgId` | Unique organization identifier. |
| `controller` | Multisig wallet authorized to issue and manage attestations. |
| `domainHash` | Hashed domain used for on-chain proof of ownership. |
| `metadataURI` | Off-chain reference containing organization details (e.g., logo, name, and metadata). |

**Events:**  
- `OrgCreated`  
- `OrgUpdated`  
- `OrgVerifiedDomain`

---

## 🧾 AttestationHub Structure

Each attestation binds a verified wallet to an organization with specific role data.

| Field | Description |
|--------|-------------|
| `attId` | Unique attestation identifier. |
| `orgId` | References the issuing organization. |
| `subjectWallet` | Wallet address of the verified individual. |
| `socialType` | Platform reference (e.g., TWITTER, TELEGRAM, LINKEDIN). |
| `socialHandleHash` | Hashed username or handle. |
| `relationType` | Relationship type (Employee, Contractor, Partner, etc.). |
| `status` | Current state: Active, Revoked, Expired, or Disputed. |

**Events:**  
- `Attested`  
- `Updated`  
- `Revoked`  
- `Disputed`

---

## 🔑 Supported Role Types

| Role Type | Description |
|------------|-------------|
| **EMPLOYEE** | Permanent or part-time staff members. |
| **CONTRACTOR** | Temporary or project-based contributors. |
| **PARTNER** | Official business or ecosystem partners. |
| **ADVISOR** | Registered strategic advisors or consultants. |
| **AMBASSADOR** | Public advocates or brand representatives. |
| **OFFICIAL_SPOKESPERSON** | Verified communication or PR representative. |

---

## 🔐 Domain Verification (Trust Bootstrapping)

Organizations verify ownership without using traditional emails or manual approvals.  
Instead, they prove authenticity through **DNS** or **HTTPS** validation:

1. Add a DNS TXT record:  
   ```
   metaverify=<orgId|wallet>
   ```
2. Or host a signed JSON file:  
   ```
   /.well-known/metaverify.json
   ```
3. Successful verification triggers the on-chain event `OrgVerifiedDomain`.

This approach provides cryptographic proof of authenticity directly from the domain level.

---

## 👥 Subject (User) Verification Flow

1. The individual connects their wallet and verifies their socials via **MetaVerify**.  
2. The organization issues an **on-chain attestation** linking the wallet to the verified handle.  
3. Metadata includes role, title, department, and start date.  
4. The attestation is immediately visible and verifiable through public explorers and APIs.

---

## 🔁 Attestation Lifecycle

| Phase | Description | Event |
|--------|-------------|--------|
| **Create** | Organization issues a new attestation | `Attested` |
| **Update** | Role or metadata modified | `Updated` |
| **Revoke** | Relationship ended or withdrawn | `Revoked` |
| **Dispute** | Subject or third-party challenges authenticity | `Disputed` |

Attestations remain permanently recorded on-chain for full transparency and historical reference.

---

## 🧩 Example Smart Contract Functions (Simplified)

```solidity
function attest(
    uint256 orgId,
    address subjectWallet,
    bytes32 socialType,          // e.g. keccak256("TELEGRAM")
    bytes32 socialHandleHash,    // e.g. keccak256("@handle")
    uint8 relationType,          // enum
    uint64 startTs,
    string calldata metadataURI
) external onlyOrgController(orgId);

function revoke(uint256 attId, uint64 endTs, uint16 reasonCode)
    external onlyOrgControllerOf(attId);
```

---

## ⚙️ Public APIs

| Endpoint | Description |
|-----------|-------------|
| **GET /org/{orgId}** | Returns organization info, verified domain, and metadata. |
| **GET /subject/{wallet}** | Returns all active and historical attestations for a wallet. |
| **GET /social/{platform}/{handle}** | Returns the verified wallet and organization associated with a social handle. |

---

## 💬 Practical Examples

### Example 1 — Fake Representative on Telegram

A scammer pretends to represent a major brand.  
Users can instantly verify their handle on MetaVerify:

- **Verified:** “This handle is officially attested by the organization.”  
- **Unconfirmed:** “No valid attestation found.”  
- **Rejected:** “This handle has been flagged as false.”

---

### Example 2 — Fake Partnership Claim

A project claims a partnership with another organization.  
Unless both parties issue mutual attestations, MetaVerify displays the claim as **Unverified** or **Rejected**.

---

## 💰 Economics (Illustrative)

> *Example values only — final pricing will be determined before launch.*

| Action | Example Fee | Description |
|--------|--------------|-------------|
| **Organization Registration** | 10–20 MET | One-time setup with annual renewal. |
| **Attestation Creation** | 1–2 MET | Paid per verified relationship. |
| **Update / Revoke** | Micro-fee | Prevents spam and sustains the treasury. |

**Fee Distribution (Illustrative):**  
- 60% → Treasury (ecosystem maintenance)  
- 40% → Burn (deflationary mechanism)

---

## 💠 Future Integrations

- **Vanity Name Linking:** Associate attestations with `.meta` and `.verify` names.  
- **HR & LinkedIn Connectors:** Enable direct verification through corporate systems.  
- **Endorsement Ledger:** Build social credibility through peer validation.  
- **AI Trust Scoring:** Introduce predictive reliability scores for verified entities.  

---

## 📜 Conclusion

**MetaVerify Attestations** redefine organizational identity verification by placing trust on-chain.  
Through transparent contracts, automated revocations, and immutable audit trails, the system ensures that every claim — from employment to partnerships — is verifiable, authentic, and traceable on the **MetaNews Blockchain**.

---

© 2025 MetaNews. All rights reserved.