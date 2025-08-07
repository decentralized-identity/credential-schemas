# Action Access Specification Credential (OriginVault)

Specifies platform, availability, regional, and subscription requirements for performing a given action. Based on Schema.org [ActionAccessSpecification](http://schema.org/ActionAccessSpecification).

## Core Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | `uri` | Identifier for the action/service |
| `schema:actionPlatform` | `uri` | Platform(s) where action is supported |
| `schema:availabilityStarts` / `schema:availabilityEnds` | `dateTime` | Time window of availability |
| `schema:category` | `string` | Category or class of action |
| `schema:eligibleRegion` | `uri` | Geographical region eligible |
| `schema:requiresSubscription` | `uri` | Subscription/payment requirement |

## Example

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/action-access-specification/context.json"
  ],
  "type": ["VerifiableCredential", "ov:ActionAccessSpecificationCredential"],
  "credentialSubject": {
    "id": "https://originvault.box/action/download",
    "schema:actionPlatform": "https://schema.org/OnlinePlatform",
    "schema:availabilityStarts": "2025-07-01T00:00:00Z",
    "schema:availabilityEnds": "2025-07-31T23:59:59Z",
    "schema:category": "PromoDownload",
    "schema:eligibleRegion": "https://sws.geonames.org/6252001/", 
    "schema:requiresSubscription": "https://example.com/subscriptions/pro"
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-06-15T09:00:00Z"
}
``` 