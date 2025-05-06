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
│   ├── DIDAttestation/
│       ├── v1.1/
│           ├── schema.json
│           ├── context.json
│           ├── README.md
│       ├── v2.0/
│           ├── schema.json
│           ├── context.json
│           ├── README.md
│   ├── README.md
│   └── ...
```

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