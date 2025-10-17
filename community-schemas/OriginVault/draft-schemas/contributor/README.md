# Contributor Credential (OriginVault)

A credential that attests to a secondary contributor to a CreativeWork or Event, based on Schema.org [contributor](https://schema.org/contributor) property. This enables verifiable attribution for collaborative works and events.

## Core Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | `uri` | Identifier for the contribution relationship |
| `schema:contributor` | `Person/Organization` or `uri` | The secondary contributor |
| `schema:contributorRole` | `string` | Role of the contributor (Editor, Reviewer, etc.) |
| `schema:contributorType` | `string` | Type of contribution (Technical, Creative, etc.) |
| `schema:dateCreated` | `dateTime` | When the contribution was first recorded |
| `schema:dateModified` | `dateTime` | When the contribution was last updated |
| `schema:agent` | `Person/Organization` or `uri` | Entity that issued this credential |

## Use Cases

- **Content Collaboration**: Attesting contributors to articles, videos, artwork
- **Event Participation**: Recording speakers, organizers, volunteers
- **Software Development**: Crediting code reviewers, testers, documentation writers
- **Academic Works**: Citing co-authors, reviewers, research assistants
- **Creative Projects**: Acknowledging editors, translators, consultants

## Example

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/contributor/context.json"
  ],
  "type": ["VerifiableCredential", "ov:ContributorCredential"],
  "credentialSubject": {
    "id": "urn:uuid:contrib-1234-5678-9abc-def012345678",
    "schema:contributor": {
      "@type": "Person",
      "schema:@id": "did:web:bob.example",
      "schema:name": "Bob Smith",
      "schema:identifier": {
        "schema:propertyID": "did",
        "schema:value": "did:web:bob.example"
      }
    },
    "schema:contributorRole": "Technical Reviewer",
    "schema:contributorType": "Technical",
    "schema:dateCreated": "2025-06-15T10:00:00Z",
    "schema:dateModified": "2025-06-20T14:30:00Z",
    "schema:description": "Reviewed technical accuracy and provided feedback on API documentation"
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-06-21T09:00:00Z"
}
```

## Schema.org Compliance

This credential leverages the Schema.org `contributor` property which:
- Expects values of type `Organization` or `Person`
- Is used on `CreativeWork` and `Event` types
- Supports secondary contributor relationships
- Enables structured attribution for collaborative works 