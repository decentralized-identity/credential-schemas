# Software Application Credential (OriginVault)

A credential that describes software applications using Schema.org [SoftwareApplication](https://schema.org/SoftwareApplication) properties. It provides verifiable metadata about app categories, platforms, versions, and publishers.

## Core Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | `uri` | Identifier of the application (product page URL, DID, etc.) |
| `schema:applicationCategory` | `string` | Category of the application (Game, Productivity, etc.) |
| `schema:operatingSystem` | `string` | Operating systems supported |
| `schema:softwareVersion` | `string` | Current version of the application |
| `schema:downloadUrl` | `uri` | URL to download or install the application |
| `schema:agent` | `Person/Organization` or `uri` | Publisher or developer |
| `schema:dateCreated` | `dateTime` | Initial release date |
| `schema:dateModified` | `dateTime` | Last update date |

## Example

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/software-application/context.json"
  ],
  "type": ["VerifiableCredential", "ov:SoftwareApplicationCredential"],
  "credentialSubject": {
    "id": "https://apps.apple.com/app/originvault",
    "schema:applicationCategory": "Productivity",
    "schema:operatingSystem": "iOS 17",
    "schema:softwareVersion": "3.4.0",
    "schema:downloadUrl": "https://apps.apple.com/app/originvault",
    "schema:agent": {
      "@type": "Organization",
      "schema:@id": "did:web:originvault.io",
      "schema:name": "OriginVault Inc."
    },
    "schema:dateCreated": "2025-04-01T00:00:00Z",
    "schema:dateModified": "2025-05-15T12:00:00Z"
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-05-16T09:00:00Z"
}
``` 