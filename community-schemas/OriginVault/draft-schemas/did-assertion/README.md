# DID Assertion Credential (OriginVault)

A credential that asserts a claim about a subject using Schema.org review standards. This credential provides a structured way to make and verify claims about entities using Schema.org review patterns.

## Core Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | `uri` | Identifier of the subject being asserted about |
| `schema:reviewAspect` | `string` | Description of the claim being reviewed |
| `schema:author` | `uri` | URI of the author who made the claim |
| `schema:reviewer` | `string` | Entity responsible for interpreting the claim |
| `schema:review` | `array` | Array of review events for this claim |
| `schema:dateCreated` | `dateTime` | When the claim first appeared |
| `schema:dateModified` | `dateTime` | When the claim was last modified |
| `schema:identifier` | `object` | Structured identifier for the assertion |

### Review Object Structure
| Field | Type | Description |
|-------|------|-------------|
| `schema:dateCreated` | `dateTime` | When this review occurred |
| `schema:reviewRating` | `Rating` object | Rating of the claim |
| `schema:ratingValue` | `string` | Status: "Verified", "Disputed", "Revoked" |
| `schema:bestRating` | `string` | Best possible rating ("Verified") |
| `schema:worstRating` | `string` | Worst possible rating ("Revoked") |
| `schema:text` | `string` | Additional details about the review |

## Example

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/did-assertion/context.json"
  ],
  "type": ["VerifiableCredential", "ov:DIDAssertion"],
  "credentialSubject": {
    "id": "did:web:alice.example",
    "schema:reviewAspect": "Alice claims to be a verified artist on OriginVault",
    "schema:author": "did:web:alice.example",
    "schema:reviewer": "OriginVault Verification System",
    "schema:review": [
      {
        "schema:dateCreated": "2025-01-10T12:00:00Z",
        "schema:reviewRating": {
          "@type": "Rating",
          "schema:ratingValue": "Verified",
          "schema:bestRating": "Verified",
          "schema:worstRating": "Revoked"
        },
        "schema:text": "Artist verification completed based on portfolio review and community feedback."
      }
    ],
    "schema:dateCreated": "2025-01-10T12:00:00Z",
    "schema:dateModified": "2025-01-10T12:00:00Z",
    "schema:identifier": {
      "schema:propertyID": "assertionId",
      "schema:value": "assert_12345"
    }
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-01-10T12:00:00Z"
}
```

## Use Cases

- **Identity Verification**: Asserting verified identity claims
- **Skill Endorsements**: Claiming specific skills or qualifications
- **Reputation Scores**: Rating-based reputation systems
- **Compliance Claims**: Asserting regulatory compliance
- **Membership Verification**: Proving membership in organizations

## Schema.org Compliance

This credential leverages Schema.org review patterns:
- Uses `Rating` objects for structured evaluations
- Follows Schema.org review lifecycle patterns
- Supports multiple review events over time
- Maintains audit trail of claim changes 