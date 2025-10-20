# MetaVerify Vanity Names

_Last updated: March 2025_

---

## 🔍 Overview

**MetaVerify Vanity Names** bring human-readable identities to the **MetaNews Blockchain**.  
They replace long wallet addresses with short, brandable names.

Each name acts as an on-chain identity token — integrating directly with **MetaVerify** the **Verified Tick Utility** to display verification status, ownership, and related metadata.

---

## 🧭 Objectives

- Simplify blockchain identities with readable and memorable names.
- Link verified badges and reputation data to public wallet identities.
- Enable users and organizations to claim unique digital handles under the `.meta`, `.verify`, and `.news` namespaces.
- Create a sustainable, MET-powered registration and renewal model.

---

## 🧩 System Overview

| Component             | Description                                                             |
| --------------------- | ----------------------------------------------------------------------- |
| **Vanity Name NFT**   | ERC-721 token representing ownership of a human-readable identity.      |
| **Resolver Contract** | Maps the name to wallet addresses and badge status.                     |
| **Metadata**          | Stores verification status, social links, and optional profile info.    |
| **API Endpoints**     | Resolve names ↔ wallets ↔ badges for apps, explorers, and integrations. |

---

## 🔤 Naming Conventions

| Namespace   | Intended Use                                                     |
| ----------- | ---------------------------------------------------------------- |
| **.meta**   | General-purpose personal and creator identities.                 |
| **.verify** | Verified users, brands, and organizations.                       |
| **.news**   | Publishers, journalists, and creators in the MetaNews ecosystem. |

---

## ⚙️ Minting & Ownership Flow

1. **User connects a wallet** on the MetaNews Blockchain.
2. **Chooses an available name** (e.g., `alex.meta`).
3. **Pays registration fee in MET** — triggering the NFT mint.
4. **Ownership recorded on-chain** via ERC-721 smart contract.
5. **Optional**: Link verified social accounts to display the verified tick badge.

Each minted name is **fully transferable**, allowing secondary-market sales or ownership migration.

---

## 🔗 Integration with Verification

- Each name can **display a verified badge** once the wallet completes the Verified Tick process.
- The name record stores and exposes:
  - Wallet address
  - Verification badge status (Verified / Revoked / Pending)
  - Associated profile metadata

Public APIs allow any third-party app or dApp to instantly resolve this data.

---

## 💰 Economic Model (Illustrative)

> _All prices below are examples and subject to change prior to public launch._

| Type                  | Example Fee        | Description                             |
| --------------------- | ------------------ | --------------------------------------- |
| **Base Registration** | `10 MET / year`    | Standard name registration (renewable). |
| **Premium Names**     | Auction-based      | Short or high-demand names.             |
| **Renewal**           | Annual MET payment | Names must be renewed each year.        |

**Revenue Allocation (illustrative):**

- 60% → Treasury (ecosystem growth)
- 40% → Burn (MET deflation)

Final fee model and revenue distribution will be announced closer to release.

---

## 🧠 Technical Architecture

| Component                | Function                                                                      |
| ------------------------ | ----------------------------------------------------------------------------- |
| **Smart Contract**       | ERC-721 ownership + resolver mapping.                                         |
| **Resolver**             | Translates `.meta`, `.verify`, or `.news` to wallet addresses and badge data. |
| **Frontend Integration** | “Claim your .meta name” within the MetaVerify dashboard.                      |
| **APIs**                 | REST/GraphQL endpoints to resolve name-to-wallet and wallet-to-name mappings. |
| **Profile Pages**        | Accessible via URLs such as `username.meta.news`.                             |

---

## 🌐 API Endpoints

| Endpoint                  | Description                                  |
| ------------------------- | -------------------------------------------- |
| **GET /resolve/{name}**   | Returns wallet address and badge status.     |
| **GET /reverse/{wallet}** | Returns all vanity names linked to a wallet. |

These endpoints enable instant verification and reputation lookups for wallets, organizations, or brands across the MetaNews ecosystem.

---

## 👤 User Flow Example

1. User connects wallet.
2. Searches for an available name (`creator.meta`).
3. Confirms registration and pays in MET.
4. Name is minted on-chain and displayed in their profile.
5. If the wallet is verified, a badge appears next to the name.

---

## 💎 Use Cases

| Category         | Example          | Description                                              |
| ---------------- | ---------------- | -------------------------------------------------------- |
| **Individuals**  | `sara.meta`      | Personal blockchain identity linked to verified socials. |
| **Businesses**   | `acme.verify`    | Corporate verification and public trust proof.           |
| **Creators**     | `studio.news`    | Publisher identity for verified media releases.          |
| **Integrations** | Exchanges, dApps | Display verified names instead of raw addresses.         |

---

## 🧩 Future Features

- Integration with **organizational attestations** (linking names to company-issued proofs).
- **Name migration** support for wallet replacements.
- Integration with **AI-powered trust scores** from the upcoming MetaVerify Reputation Layer.
- **On-chain auctions** for premium and reserved names.

---

## 📜 Conclusion

The **MetaVerify Vanity Names** system brings readability, authenticity, and brand recognition to blockchain identities.  
By combining NFTs, AI verification, and MET token economics, it builds a user-owned identity layer for the decentralized media and creator economy.

---

© 2025 MetaNews. All rights reserved.
