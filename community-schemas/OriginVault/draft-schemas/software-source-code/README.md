# Software Source Code Credential (OriginVault)

A credential that describes software source code using Schema.org [SoftwareSourceCode](https://schema.org/SoftwareSourceCode) properties. It enables verifiable attestations about code repositories, languages, versions, and authors.

## Core Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | `uri` | Identifier of the source code (repository URL, DID, or URN) |
| `schema:codeRepository` | `uri` | Link to the code repository (GitHub, GitLab, etc.) |
| `schema:programmingLanguage` | `string` | Programming language used |
| `schema:runtimePlatform` | `string` | Runtime or interpreter dependency |
| `schema:softwareVersion` | `string` | Version of the software |
| `schema:dateCreated` | `dateTime` | When the code was first created |
| `schema:dateModified` | `dateTime` | Last modification timestamp |
| `schema:agent` | `Person/Organization` or `uri` | Author or maintainer |

## Example

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/software-source-code/context.json"
  ],
  "type": ["VerifiableCredential", "ov:SoftwareSourceCodeCredential"],
  "credentialSubject": {
    "id": "https://github.com/originvault/awesome-project",
    "schema:codeRepository": "https://github.com/originvault/awesome-project",
    "schema:programmingLanguage": "TypeScript",
    "schema:runtimePlatform": "Node.js 20",
    "schema:softwareVersion": "1.2.3",
    "schema:dateCreated": "2025-05-20T10:00:00Z",
    "schema:agent": {
      "@type": "Person",
      "schema:@id": "did:web:alice.example",
      "schema:name": "Alice Developer"
    }
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-05-21T09:00:00Z"
}
``` 