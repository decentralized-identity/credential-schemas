# Proof of Upload (OriginVault)

Attests that a piece of content was uploaded to a storage location at a given time using Schema.org standards.

## Core Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | `uri` | Identifier of the uploaded content |
| `schema:identifier` | `object` | Structured identifier containing the upload hash |
| `schema:uploadDate` | `dateTime` | Time of upload |
| `schema:agent` | `Person/Organization` or `uri` | Entity that uploaded the content |
| `schema:contentUrl` | `uri` | Storage location where content resides |
| `schema:encodingFormat` | `string` | MIME type of the uploaded file |
| `schema:contentSize` | `string` | Size of the file (human readable) |
| `schema:name` | `string` | Name of the uploaded file |
| `schema:description` | `string` | Description of the uploaded content |
| `schema:dateCreated` | `dateTime` | When the content was originally created |
| `schema:dateModified` | `dateTime` | When the content was last modified before upload |
| `schema:uploadAction` | `CreateAction` object | Optional Schema.org action context |

## Example
```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/proof-of-upload/context.json"
  ],
  "type": ["VerifiableCredential", "ov:ProofOfUploadCredential"],
  "credentialSubject": {
    "id": "ipfs://bafk...",
    "schema:identifier": {
      "schema:propertyID": "uploadHash",
      "schema:value": "zQm..."
    },
    "schema:uploadDate": "2025-02-02T10:00:00Z",
    "schema:agent": {
      "@type": "Person",
      "schema:@id": "did:web:uploader.example",
      "schema:name": "Alice Uploader"
    },
    "schema:contentUrl": "ar://abc123...",
    "schema:encodingFormat": "image/jpeg",
    "schema:contentSize": "2.4 MB",
    "schema:name": "artwork.jpg"
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-02-02T10:01:00Z"
}
``` 