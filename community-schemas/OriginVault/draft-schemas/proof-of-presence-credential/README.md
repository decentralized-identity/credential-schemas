# Proof Of Presence Credential (OriginVault)

Proves that a subject (person or device) was present at a specific geographic location and time using Schema.org standards.

## Core Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | `uri` | Identifier of the subject |
| `schema:location` | `Place` object | Geographic location with coordinates |
| `schema:startDate` | `dateTime` | When presence was recorded |
| `schema:endDate` | `dateTime` | When presence ended (if applicable) |
| `schema:measurementTechnique` | `string` | How presence was verified (GPS, WiFi, NFC, etc.) |
| `schema:agent` | `Person/Device` or `uri` | The person or device that was present |

### Location Object Structure
| Field | Type | Description |
|-------|------|-------------|
| `@type` | `Place` | Schema.org Place type |
| `schema:geo` | `GeoCoordinates` object | Geographic coordinates |
| `schema:latitude` | `number` | Latitude in decimal degrees |
| `schema:longitude` | `number` | Longitude in decimal degrees |
| `schema:geoRadius` | `number` | Optional radius in meters |
| `schema:name` | `string` | Name of the location |
| `schema:address` | `PostalAddress` object | Optional address details |

## Example
```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/proof-of-presence-credential/context.json"
  ],
  "type": ["VerifiableCredential", "ov:ProofOfPresenceCredential"],
  "credentialSubject": {
    "id": "did:web:device.example",
    "schema:location": {
      "@type": "Place",
      "schema:geo": {
        "@type": "GeoCoordinates",
        "schema:latitude": 37.7749,
        "schema:longitude": -122.4194,
        "schema:geoRadius": 20
      },
      "schema:name": "San Francisco, CA"
    },
    "schema:startDate": "2025-03-03T09:30:00Z",
    "schema:measurementTechnique": "GPS",
    "schema:agent": {
      "@type": "Person",
      "schema:@id": "did:web:alice.example",
      "schema:name": "Alice Johnson"
    }
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-03-03T09:31:00Z"
}
``` 