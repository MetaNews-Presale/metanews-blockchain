# Verified Tick Utility (with MET Payment)

*Last updated: March 2025*

---

## 🔍 Overview

The **Verified Tick Utility** is a decentralized identity-verification framework built on the **MetaNews Blockchain**.  
It enables users to authenticate their social presence across multiple platforms using **AI-driven verification** and **MET token payments**.

Each verified account receives an on-chain badge that confirms authenticity, strengthens user trust, and integrates seamlessly with the broader MetaVerify ecosystem.

---

## 🧭 Objectives

- Verify the authenticity of user identities across social platforms.  
- Prevent impersonation and fake brand accounts.  
- Provide an intuitive MET-based payment and renewal system.  
- Establish a transparent, automated, and on-chain proof of identity.

---

## 🧩 System Architecture

| Layer | Function |
|-------|-----------|
| **Frontend** | Guides users through wallet connection, social linking, and proof submission. |
| **AI Engine** | Compares public content and bios to validate identity claims. |
| **Scraping Layer** | Collects data from supported social platforms for analysis. |
| **Smart Contracts** | Issue, renew, and revoke on-chain verification badges. |
| **Automation Layer** | Handles retries, scheduled re-verifications, and data recovery. |

---

## 💳 Payment Flow (MET Token)

- All verification fees are paid in **MET**, the native token of MetaNews Blockchain.  
- Example pricing:  
  - **1 MET** (illustrative) may cover one social account verification.  
  - **~3 MET** (illustrative) may cover a full multi-platform verification package.  
- Actual pricing and structure will be determined at a later stage.  
- Payments are made directly on-chain and trigger the AI verification process.  
- Optional **fiat purchases** are supported through Wert.io for users without crypto.

---

## 🔐 Wallet & Token Flow

1. User connects their **EVM-compatible wallet** (e.g., MetaMask).  
2. Switches to the **MetaNews Blockchain**.  
3. Verification payment is made in MET.  
4. Backend logic performs AI and scraping checks.  
5. On success, the verification contract updates the user’s wallet status on-chain.  
6. Emitted smart contract events:  
   - `VerificationGranted`  
   - `VerificationRevoked`  
   - `RenewalConfirmed`

---

## 🧠 Verification Workflow

### Step 1 – Social Proof Posting

- User submits public profile links (Twitter, YouTube, TikTok, Instagram).  
- System generates a **unique signed message**.  
- User posts it publicly on each platform.  
- The scraping engine detects and verifies the post.  
- Once validated, the process advances to AI matching.

### Step 2 – BIO & AI Matching

- User provides their **public BIO or profile description**.  
- The AI engine compares it against data scraped from linked profiles.  
- NLP models and fuzzy logic determine semantic alignment.  
- If match confidence exceeds threshold → verification is approved.

---

## 🧩 AI Verification Logic

| Platform Type | Data Sources | Methodology | Match Threshold |
|----------------|--------------|--------------|-----------------|
| **Text-based** (Twitter, LinkedIn, Threads) | Bio, username, about text | NLP keyword extraction, semantic embeddings | ≥ 80 % |
| **Video-based** (TikTok, YouTube, Instagram Reels) | Audio, captions, visuals | Whisper transcription + GPT-4o multimodal analysis | ≥ 75 % combined |

**Scoring Weights:**  
- Audio Relevance – 40 %  
- Caption Relevance – 30 %  
- Visual Relevance – 30 %

---

## ⚙️ Automation & Lifecycle

- **Monthly re-verification** via AI to ensure authenticity and consistency.  
- **Automatic revocation** for expired payments or mismatched content.  
- **24-hour grace period** before badge removal.  
- **Wallet migration flow** supports verified badge transfers.  
- **Conflict resolution** revokes older verifications for reused socials.  

---

## 🧩 Admin & Dashboard Tools

- Approve or reject borderline verifications.  
- View AI confidence scores and retry logs.  
- Manage appeals, badge renewals, and wallet migrations.  
- Access analytics on verification success rates and platform usage.  

---

## 🧪 Technology Stack

| Component | Technology |
|------------|-------------|
| **AI / NLP** | OpenAI Embeddings, GPT-4o, GPT-4o-mini |
| **Audio Analysis** | Whisper API |
| **Scraping** | Puppeteer, Cheerio, Axios |
| **Smart Contracts** | Solidity (MetaNews Blockchain) |
| **Backend** | Node.js / Express |
| **Frontend** | React / Next.js |
| **Automation** | Cron Jobs + Workers |
| **Database** | PostgreSQL / MongoDB |

---

## 💠 Future Enhancements

- Integration with **MetaVerify Vanity Names** (display badges next to `.meta` handles).  
- Support for **LinkedIn**, **Discord**, and future social platforms.  
- On-chain analytics for verification volume and reputation scoring.  
- KYB/KYC extension for business and enterprise accounts.  

---

## 📜 Conclusion

The **Verified Tick Utility** transforms social verification into a decentralized, AI-assisted process secured by the **MetaNews Blockchain**.  
By linking blockchain transparency with intelligent content matching, it provides a trustworthy, automated foundation for digital identity in the Web3 era.

---

© 2025 MetaNews. All rights reserved.
