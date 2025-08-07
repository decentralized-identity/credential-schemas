# Content Registration Credential (OriginVault)

This credential registers a piece of digital content on OriginVault, anchoring its hash, registration date, and registrant. The schema aligns with [Schema.org RegisterAction](https://schema.org/RegisterAction) patterns for enhanced interoperability.

## Core Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | `uri` | Identifier of the content item (e.g., CID, URI) |
| `schema:identifier` | `object` | Structured identifier containing the content hash |
| `schema:dateCreated` | `dateTime` | Timestamp when the content was registered |
| `schema:agent` | `uri` or `Person/Organization` object | Entity that registered the content |
| `ov:registrationAction` | `RegisterAction` object | Optional Schema.org action context |
| `schema:url` | `uri` | Canonical URL where the content can be accessed |
| `ov:softPerceptualHash` | `string` | 8×8 perceptual hash of the content |
| `ov:mediumPerceptualHash` | `string` | 16×16 perceptual hash of the content |
| `ov:precisePerceptualHash` | `string` | 24×24 perceptual hash of the content |
| `schema:accountId` | `string` | Username (if publicly published) |
| `schema:name` | `string` | Original filename |
| `ov:path` | `string` | Storage path in object store |
| `ov:status` | `string` | Processing status (`pending`, `verified`, `published`) |
| `ov:color` | `string` | Dominant colour (hex) |
| `ov:colorCode` | `string` | Colour hash code |
| `ov:mnemonicId` | `string` | Human-readable snowflake ID |
| `schema:encodingFormat` | `string` | MIME type of the content (e.g., image/jpeg) |
| `schema:contentSize` | `string` | Size of the content (e.g., 2.4 MB) |
| `schema:uploadDate` | `dateTime` | Alias of registration date (schema.org compatibility) |

## Enhanced Registrant Structure

The `schema:agent` property supports both simple URIs and structured objects:

```json
// Simple URI format
"schema:agent": "did:web:creator.example"

// Structured object format (Schema.org compatible)
"schema:agent": {
  "@type": "Person",
  "schema:@id": "did:web:creator.example",
  "schema:name": "Alice Creator",
  "schema:identifier": {
    "schema:propertyID": "did",
    "schema:value": "did:web:creator.example"
  }
}
```

## Schema.org RegisterAction Integration

The optional `ov:registrationAction` property provides Schema.org action context:

```json
"ov:registrationAction": {
  "@type": "RegisterAction",
  "schema:agent": "did:web:creator.example",
  "schema:object": "ipfs://bafy...",
  "schema:target": "https://originvault.box/register",
  "schema:startTime": "2025-01-10T12:34:56Z",
  "schema:endTime": "2025-01-10T12:35:01Z",
  "schema:actionStatus": "CompletedActionStatus",
  "schema:result": {
    "@type": "CreativeWork",
    "schema:@id": "ipfs://bafy...",
    "schema:identifier": {
      "schema:propertyID": "contentHash",
      "schema:value": "zQm..."
    }
  }
}
```

## Examples

### Basic Example

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/content-registration-credential/context.json"
  ],
  "type": ["VerifiableCredential", "ov:ContentRegistrationCredential"],
  "credentialSubject": {
    "id": "ipfs://bafy...",
    "schema:identifier": {
      "schema:propertyID": "contentHash",
      "schema:value": "zQm..."
    },
    "schema:dateCreated": "2025-01-10T12:34:56Z",
    "schema:agent": "did:web:creator.example",
    "schema:url": "https://example.com/artwork.png"
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-01-10T12:35:01Z"
}
```

### Enhanced Example with Schema.org Integration

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/content-registration-credential/context.json"
  ],
  "type": ["VerifiableCredential", "ov:ContentRegistrationCredential"],
  "credentialSubject": {
    "id": "ipfs://bafy...",
    "schema:identifier": {
      "schema:propertyID": "contentHash",
      "schema:value": "zQm..."
    },
    "schema:dateCreated": "2025-01-10T12:34:56Z",
    "schema:agent": {
      "@type": "Person",
      "schema:@id": "did:web:creator.example",
      "schema:name": "Alice Creator"
    },
    "ov:registrationAction": {
      "@type": "RegisterAction",
      "schema:agent": "did:web:creator.example",
      "schema:object": "ipfs://bafy...",
      "schema:target": "https://originvault.box/register",
      "schema:startTime": "2025-01-10T12:34:56Z",
      "schema:endTime": "2025-01-10T12:35:01Z",
      "schema:actionStatus": "CompletedActionStatus"
    }
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-01-10T12:35:01Z"
}
``` 