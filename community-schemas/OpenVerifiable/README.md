Here’s a draft **README.md** tailored for the **`openverifiable` community schemas folder** in the DIF [`credential-schemas`](https://github.com/decentralized-identity/credential-schemas) repo. It frames OpenVerifiable in the right context (as a community-driven layer for apps and content registries) while keeping it clear and lightweight for developers browsing schemas:

---

# OpenVerifiable Community Schemas

The **OpenVerifiable** folder contains schemas contributed by the [OpenVerifiable project](https://openverifiable.ai), an open-source initiative focused on **making trust infrastructure usable for real apps and content platforms**.

## Purpose

OpenVerifiable extends the DIF community schema library with schemas that support:

* **Web & App Developers** → drop verifiable credentials into apps with predictable formats and developer-friendly codegen.
* **Content Authenticity** → register digital content on-ledger with proofs of origin, presence, and reuse.
* **User Transactions** → support everyday use cases (e.g. identity checks, endorsements, forward permissions) that power online interactions.

All schemas here follow the [W3C Verifiable Credentials Data Model](https://www.w3.org/TR/vc-data-model/) and are anchored in **JSON Schema / JSONValidation2020** for validation.

## How OpenVerifiable Uses These Schemas

* **Schema Registry:** every schema published here is automatically anchored as a DID-Linked Resource on [Cheqd](https://cheqd.io) for immutability and global discoverability.
* **Developer Types:** schemas are extended into **TypeScript types, overlays, and code declarations** so developers can integrate them directly into apps.
* **Content Registry:** content-related credentials (e.g. `ProofOfUpload`, `ContentRegistration`) are issued and signed on-chain to establish provenance of digital assets.

## Example Schema Categories

* **Identity & Personhood**

  * Verified Person Credential
  * Basic Personhood / Proof-of-Age Credentials
* **Content Provenance**

  * Proof of Upload Credential
  * Proof of Presence Credential
  * Content Registration Credential
* **Trust & Permissions**

  * Forward Permissions Credential
  * Endorsement Credential

## Relationship to Other Folders

* **`/originvault`** → schemas specific to OriginVault’s apps and vault ecosystem (user-facing content & monetization tools).
* **`/cheqd`** → schemas directly maintained by Cheqd for identity infrastructure.
* **`/openverifiable`** → schemas that serve as **building blocks for developers and apps**, contributed back to DIF for reuse beyond OriginVault or Cheqd.

## Contributing

We welcome contributions of schemas that:

* Are aligned with open standards (W3C VCDM, DIF, CAWG, C2PA).
* Have clear developer or content-authenticity use cases.
* Can be validated with JSON Schema and extended into app frameworks.

Please open a PR or discussion in the DIF repo if you’d like to contribute.
