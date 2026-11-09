# Verifiable Endorsement

The **Verifiable Endorsement** is a schema designed to provide social proof, reviews, recommendations, and endorsements for various entities including people, organizations, products, services, and content. This schema allows for the creation of endorsement assertions that can be embedded in verifiable credentials to establish trust and reputation in digital spaces.

## Overview

This schema follows the DID Assertion pattern and focuses on the endorsement content itself, separate from the W3C Verifiable Credentials wrapper. It enables the creation of endorsement assertions that can be used to:

- Provide social proof and recommendations
- Share reviews and ratings for products, services, or content
- Endorse skills, expertise, and professional capabilities
- Verify ownership of social media handles and digital identities
- Build reputation networks and trust systems
- Support recommendation systems and discovery platforms

## Schema Structure

### Core Fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `@context` | String | Yes | URI reference to the JSON-LD context |
| `credentialSubject` | Object | Yes | Subject and endorsement claims being made |

### Credential Subject Fields

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `id` | URI | Yes | DID or URI of the endorsed entity |
| `@type` | String | No | Type of endorsed entity (Person, Organization, CreativeWork, Product, Service) |
| `name` | String | No | Name of the endorsed entity |
| `endorsedFor` | Array | Yes | Array of endorsement claims |

### Endorsement Types

The schema supports various types of endorsements:

- **socialMediaHandle**: Verification of social media account ownership
- **skill**: Endorsement of specific skills or competencies
- **expertise**: Professional expertise in a domain
- **product**: Product reviews and recommendations
- **service**: Service quality endorsements
- **content**: Content quality and authenticity
- **organization**: Organization reputation and trustworthiness
- **review**: General reviews and feedback
- **recommendation**: Personal recommendations

### Endorsement Claims Structure

Each item in the `endorsedFor` array contains:

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `endorsementType` | String | Yes | Type of endorsement (see above) |
| `endorsedValue` | String | Yes | The specific value being endorsed |
| `platform` | String | No | Platform or context where endorsement applies |
| `platformUrl` | URI | No | URL of the platform or context |
| `rating` | Object | No | Rating information using schema.org Rating |
| `reviewText` | String | No | Text of the review or endorsement |
| `reviewDate` | Date | No | Date when the review was written |
| `category` | String | No | Category or domain of the endorsement |
| `confidence` | String | No | Confidence level (high, medium, low) |
| `validFrom` | DateTime | No | When this endorsement becomes valid |
| `validUntil` | DateTime | No | When this endorsement expires |
| `limitJurisdiction` | URI/Array | No | Jurisdictions where the endorsement is valid |
| `evidence` | Array | No | Supporting evidence for the endorsement |

## Example Usage

### Social Media Verification

```json
{
  "@context": "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OpenVerifiable/draft-schemas/VerifiableEndorsement/context.json",
  "credentialSubject": {
    "id": "did:cheqd:user456",
    "@type": "Person",
    "name": "John Doe",
    "endorsedFor": [
      {
        "endorsementType": "socialMediaHandle",
        "endorsedValue": "@johndoe",
        "platform": "Twitter",
        "platformUrl": "https://twitter.com",
        "confidence": "high"
      }
    ]
  }
}
```

### Skill Endorsement

```json
{
  "@context": "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OpenVerifiable/draft-schemas/VerifiableEndorsement/context.json",
  "credentialSubject": {
    "id": "did:cheqd:user456",
    "@type": "Person",
    "name": "John Doe",
    "endorsedFor": [
      {
        "endorsementType": "skill",
        "endorsedValue": "JavaScript Development",
        "platform": "Professional",
        "category": "Technology",
        "rating": {
          "schema:ratingValue": 5,
          "schema:bestRating": 5,
          "schema:worstRating": 1
        },
        "reviewText": "Excellent JavaScript developer with strong problem-solving skills",
        "confidence": "high"
      }
    ]
  }
}
```

### Product Review

```json
{
  "@context": "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OpenVerifiable/draft-schemas/VerifiableEndorsement/context.json",
  "credentialSubject": {
    "id": "https://example.com/products/smartphone-x",
    "@type": "Product",
    "name": "Smartphone X",
    "endorsedFor": [
      {
        "endorsementType": "product",
        "endorsedValue": "Smartphone X",
        "platform": "TechReview",
        "platformUrl": "https://techreview.com",
        "category": "Electronics",
        "rating": {
          "schema:ratingValue": 4,
          "schema:bestRating": 5,
          "schema:worstRating": 1
        },
        "reviewText": "Excellent camera quality and battery life. Great value for money.",
        "reviewDate": "2025-01-25",
        "confidence": "high"
      }
    ]
  }
}
```

## Use Cases

1. **Social Media Verification**: Verify ownership of social media handles
2. **Professional Endorsements**: Endorse skills, expertise, and professional capabilities
3. **Product Reviews**: Share verified reviews and ratings for products
4. **Service Recommendations**: Recommend and rate services
5. **Content Quality**: Endorse the quality and authenticity of content
6. **Organization Trust**: Build trust and reputation for organizations
7. **Reputation Networks**: Create networks of trusted endorsements
8. **Discovery Platforms**: Support recommendation and discovery systems

## Implementation Notes

- The schema follows the DID Assertion pattern, focusing only on endorsement content
- W3C Verifiable Credentials wrapper properties (issuer, dates, status) are handled separately
- The schema supports schema.org vocabulary for enhanced interoperability
- Ratings use the standard schema.org Rating structure
- Confidence levels help establish the reliability of endorsements
- Jurisdiction support enables geographic scope limitations
- Evidence arrays allow for supporting documentation

## Integration with Verifiable Credentials

This endorsement assertion can be embedded within a W3C Verifiable Credential by:

1. Including the endorsement assertion in the `credentialSubject`
2. Adding standard VC properties (issuer, issuanceDate, etc.) at the credential level
3. Using the endorsement context alongside the W3C credentials context

Example VC wrapper:
```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OpenVerifiable/draft-schemas/VerifiableEndorsement/context.json"
  ],
  "type": ["VerifiableCredential", "VerifiableEndorsement"],
  "issuer": "did:cheqd:issuer123",
  "issuanceDate": "2025-01-15T00:00:00Z",
  "credentialSubject": {
    // Endorsement assertion content here
  }
}
```

## Related Schemas

- [DID Assertion Credential](../DIDAssertion/) - For asserting claims about DIDs
- [Forward Permissions Credential](../../../../cawg-endorsement-assertion/) - For delegating rights and permissions
- [Schema.org Review](https://schema.org/Review) - For review and rating structures

