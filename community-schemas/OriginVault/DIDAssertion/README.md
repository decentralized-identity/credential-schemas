# DID Assertion Credential

The **DID Assertion Credential** is a Verifiable Credential (VC) schema designed to assert, review, or validate claims about a decentralized identifier (DID). This can include claims such as **Trusted Creator**, **Verified Contributor**, or **Authentic Organization**.

It is compatible with:
- VC Data Model 1.1  
- VC Data Model 2.0 (with validFrom / validUntil upgrade)

---

## 📖 Schema Overview

| Field             | Type       | Description                                                                 |
|-------------------|------------|-----------------------------------------------------------------------------|
| `@context`       | array      | Context URIs, includes W3C and OriginVault namespaces                      |
| `id`             | URI        | Unique identifier for the credential                                        |
| `type`           | array      | Credential type (e.g., `["VerifiableCredential", "DIDAssertionCredential"]`) |
| `issuer`        | object     | Entity issuing the credential (with `id` as DID)                           |
| `issuanceDate`   | date-time  | Date the credential was issued                                              |
| `expirationDate` / `validUntil` | date-time | Expiration date (v1.1) or validity end (v2.0)                          |
| `credentialSubject` | object  | The DID subject and related claims                                          |

---

## 🏷 CredentialSubject Fields

| Field             | Type       | Description                                                                 |
|-------------------|------------|-----------------------------------------------------------------------------|
| `id`             | URI        | DID that this credential is about                                           |
| `claimReviewed`  | string     | Main claim (e.g., "Trusted Creator")                                        |
| `author`         | URI        | DID of the claim author (typically same as issuer)                          |
| `claimInterpreter` | string    | Entity or system validating the claim (e.g., OV verification node)          |
| `reviewAspect`   | string     | Specific area reviewed (e.g., "Content Authenticity")                       |
| `firstAppearance` | date-time | When the claim first appeared                                               |
| `appearance`     | array      | History of revalidations, including timestamp and reviewStatus             |

---

## ✅ Example Usage

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://schemas.originvault.box/context/did-assertion-v1.json"
  ],
  "id": "urn:uuid:1234-5678-90ab-cdef",
  "type": ["VerifiableCredential", "DIDAssertionCredential"],
  "issuer": {
    "id": "did:cheqd:issuer123"
  },
  "issuanceDate": "2025-05-05T00:00:00Z",
  "expirationDate": "2026-05-05T00:00:00Z",
  "credentialSubject": {
    "id": "did:cheqd:user456",
    "claimReviewed": "Trusted Creator",
    "author": "did:cheqd:issuer123",
    "claimInterpreter": "OriginVault Verification Node",
    "reviewAspect": "Content Authenticity",
    "firstAppearance": "2025-05-01T00:00:00Z",
    "appearance": [
      {
        "timestamp": "2025-05-02T00:00:00Z",
        "reviewStatus": "Verified"
      }
    ]
  }
}
