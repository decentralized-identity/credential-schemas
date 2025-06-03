# cheqd Schemas for DIF Schema Registry

**cheqd** is a decentralized network purpose-built for **self-sovereign identity (SSI)** and **trusted data ecosystems**. It enables the creation, issuance, and exchange of **Verifiable Credentials** with built-in **payment and governance frameworks**, while preserving privacy and decentralization. cheqd offers a full standards-compliant, interoperable stack for digital identity.

This contribution adds two new JSON-LD schemas to the DIF Schema Registry:

- ✅ **Verifiable Accreditation**  
- ✅ **Verifiable Attestation**

These schemas are designed for use with [W3C Verifiable Credentials](https://www.w3.org/TR/vc-data-model/) and enable higher-trust use cases through structured accreditation and layered attestation models.

---

## 📘 Schema Details

### 1. Verifiable Accreditation

Used to express structured claims that an entity is accredited or authorized by a governance authority. Typical use cases include:

- Accreditation to issue a credential of a certain schema
- Authorized issuer status
- Certification of compliance with specific frameworks

**Schema path:**  
`/schemas/cheqd/verifiable-accreditation.json`

---

### 2. Verifiable Attestation

A generic schema to support structured endorsements or validations made by a third party. This enables composable trust models (e.g., endorsements of credentials, agent claims, or delegations).

**Schema path:**  
`/schemas/cheqd/verifiable-attestation.json`

---

## 📦 JSON-LD Contexts

The schemas reference custom JSON-LD `@context` definitions published on the cheqd Network:

<todo>

---

## ✅ JSON Schema Conformance

- Aligned with VC Data Model v1.1  
- Valid under JSON Schema Draft 2020-12  
- Enforces presence of `@context` and `type`  
- Extensible `credentialSubject` for flexible use cases

---

## 🏷️ Publisher Information

**cheqd**  
- 🌐 Website: [https://cheqd.io](https://cheqd.io)  
- 📄 Documentation: [https://docs.cheqd.io](https://docs.cheqd.io)  
- ✉️ Contact: [product@cheqd.io](mailto:prodoct@cheqd.io)  
- 🆔 DID method: [`did:cheqd`](https://docs.cheqd.io/product/architecture/adr-list/adr-001-cheqd-did-method)

---

_For more information on how these schemas are used within verifiable ecosystems and trust registries, please refer to the documentation above._