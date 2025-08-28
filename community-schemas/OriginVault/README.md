                         ██████╗ ██████╗ ██╗ ██████╗ ██╗███╗   ██╗██╗   ██╗ █████╗ ██╗   ██╗██╗  ████████╗ 
                        ██╔═══██╗██╔══██╗██║██╔════╝ ██║████╗  ██║██║   ██║██╔══██╗██║   ██║██║  ╚══██╔══╝ 
                        ██║   ██║██████╔╝██║██║  ███╗██║██╔██╗ ██║██║   ██║███████║██║   ██║██║     ██║  
                        ██║   ██║██╔══██╗██║██║   ██║██║██║╚██╗██║╚██╗ ██╔╝██╔══██║██║   ██║██║     ██║ 
                        ╚██████╔╝██║  ██║██║╚██████╔╝██║██║ ╚████║ ╚████╔╝ ██║  ██║╚██████╔╝███████╗██║
                         ╚═════╝ ╚═╝  ╚═╝╚═╝ ╚═════╝ ╚═╝╚═╝  ╚═══╝  ╚═══╝  ╚═╝  ╚═╝ ╚═════╝ ╚══════╝╚═╝   

<div style="width: 100%; display: flex; justify-content: center; align-items: center;">
      <img src="https://gray-objective-tiglon-784.mypinata.cloud/ipfs/Qma7EjPPPfomzEKkYcJa2ctEFPUhHaMwiojTR1wTQPg2x8" alt="OriginVault logo" width="300" height="300">
</div>
---

## OriginVault Credential Schemas

[OriginVault](https://www.originvault.io/) is a Web5 platform designed to empower creators, organizations, and developers with **decentralized identity**, **user-owned data**, and **verifiable content provenance**. It bridges Web2 simplicity with Web3 trust to build a secure, scalable, and interoperable ecosystem.

This directory contains **Verifiable Credential (VC) schemas** used across the OriginVault platform. These are designed in alignment with W3C standards and CAWG best practices.

---

### 📦 Schema Usage

- Schemas defined here are deployed to the [OriginVault Schema Registry](https://schema.originvault.io/)
- They are used by OriginVault issuers to issue DIDs, content credentials, endorsements, affiliations, and more
- Each schema may include:
  - JSON Schema definition
  - JSON-LD context
  - README documentation

---

### 🧩 Developer Tooling

We publish all schemas as TypeScript types through our developer package:

📦 [`@originvault/ov-types`](https://www.npmjs.com/package/@originvault/ov-types)

```bash
npm install @originvault/ov-types
```

This enables strong typing and auto-complete for frontend and backend VC processing in TypeScript.

---

### 🧭 Structure

Each directory contains schemas and contexts for a specific version of a schema.

```
community-schemas/
├── OriginVault/
│   ├── draft-schemas/
│   │   ├── content-registration/
│   │   ├── proof-of-presence/
│   │   ├── proof-of-upload/
│   │   ├── user-registration/
│   │   ├── did-assertion/
│   │   ├── software-source-code/
│   │   ├── software-application/
│   │   ├── interaction-counter/
│   │   ├── action-access-specification/
│   │   ├── contributor/
│   │   └── ownership-info/
│   ├── DIDAttestation/
│   │   ├── v1.1/
│   │   ├── v2.0/
│   ├── README.md
│   └── ...
```

---

### 🚧 Draft Schemas

These schemas are actively evolving. Refer to each directory for detailed documentation:

- **Content Registration** (`draft-schemas/content-registration/`)  
  Registers digital content on OriginVault, anchoring its hash, registration date, and registrant.
- **Proof of Presence** (`draft-schemas/proof-of-presence/`)  
  Proves that a subject (person or device) was present at a specific geographic location and time.
- **Proof of Upload** (`draft-schemas/proof-of-upload/`)  
  Attests that a content item was uploaded to a storage location at a given time, including file metadata.
- **User Registration** (`draft-schemas/user-registration/`)  
  Records user registration events using Schema.org RegisterAction and Person representations.
- **DID Assertion** (`draft-schemas/did-assertion/`)  
  Provides a structured way to assert claims about entities using Schema.org review patterns.
- **Software Source Code** (`draft-schemas/software-source-code/`)  
  Describes repositories, languages, runtime platforms, and maintainers of code.
- **Software Application** (`draft-schemas/software-application/`)  
  Describes software applications, versions, platforms, and publishers.
- **Interaction Counter** (`draft-schemas/interaction-counter/`)  
  Counts user interactions such as likes, views, and downloads.
- **Action Access Specification** (`draft-schemas/action-access-specification/`)  
  Defines platform, time, region, and subscription prerequisites for actions.
- **Contributor** (`draft-schemas/contributor/`)  
  Attests to secondary contributors to CreativeWorks or Events using Schema.org contributor property.
- **Ownership Info** (`draft-schemas/ownership-info/`)  
  Provides structured ownership information for products and services using Schema.org OwnershipInfo type.

---

### 🛠️ Contributing

All schema updates should follow the W3C VC 1.1 or VC 2.0 model. To contribute:

1. Fork the repo
2. Create your schema in the appropriate folder
3. Add a `README.md`, `schema.json`, and `context.json`
4. Open a PR with a clear description

> Note: This repo is version-controlled by OriginVault, and all schemas must be reviewed and signed by a verified maintainer before deployment.

---

🔐 Built and maintained with trust, for creators and verifiers.

— The OriginVault Team