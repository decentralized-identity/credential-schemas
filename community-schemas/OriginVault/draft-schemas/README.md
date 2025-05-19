# OriginVault Draft Schemas

This directory contains draft schemas developed by OriginVault for various credential types.

## Available Schemas

### DID Assertion Credential

The **DID Assertion Credential** is a Verifiable Credential (VC) schema designed to assert, review, or validate claims about a decentralized identifier (DID). This can include claims such as **Trusted Creator**, **Verified Contributor**, or **Authentic Organization**.

For more details, see the [DID Assertion documentation](./didassertions/README.md).

## Schema Development Process

All schemas in this directory are in draft status and may undergo changes before final release.

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
