# Ownership Info Credential (OriginVault)

A credential that provides structured information about ownership of products or services, based on Schema.org [OwnershipInfo](https://schema.org/OwnershipInfo) type. This enables verifiable ownership tracking for digital and physical assets.

## Core Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | `uri` | Identifier for the ownership relationship |
| `schema:acquiredFrom` | `Person/Organization` or `uri` | Entity from which the product was acquired |
| `schema:ownedFrom` | `dateTime` | When ownership began (required) |
| `schema:ownedThrough` | `dateTime` | When ownership ended (if applicable) |
| `schema:typeOfGood` | `Product/Service` or `uri` | The product or service being owned |
| `schema:agent` | `Person/Organization` or `uri` | Current owner of the asset |

## Use Cases

- **Digital Asset Ownership**: NFTs, digital art, domain names
- **Physical Asset Tracking**: Real estate, vehicles, equipment
- **Intellectual Property**: Patents, trademarks, copyrights
- **Service Subscriptions**: Software licenses, memberships
- **Asset Transfers**: Purchase history, inheritance records
- **Compliance**: Regulatory ownership reporting

## Example

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/ownership-info/context.json"
  ],
  "type": ["VerifiableCredential", "ov:OwnershipInfoCredential"],
  "credentialSubject": {
    "id": "urn:uuid:ownership-1234-5678-9abc-def012345678",
    "schema:acquiredFrom": {
      "@type": "Organization",
      "schema:@id": "did:web:gallery.example",
      "schema:name": "Digital Art Gallery"
    },
    "schema:ownedFrom": "2025-06-15T10:00:00Z",
    "schema:typeOfGood": {
      "@type": "Product",
      "schema:@id": "ipfs://bafy...",
      "schema:name": "Digital Artwork #1234"
    },
    "schema:agent": {
      "@type": "Person",
      "schema:@id": "did:web:alice.example",
      "schema:name": "Alice Collector"
    },
    "schema:description": "Ownership of digital artwork purchased from gallery"
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-06-16T09:00:00Z"
}
```

## Schema.org Compliance

This credential leverages the Schema.org `OwnershipInfo` type which:
- Provides structured ownership information
- Tracks acquisition source and ownership timeline
- Supports both `Product` and `Service` types
- Enables ownership history and transfer tracking
- Derived from GoodRelations vocabulary for e-commerce 