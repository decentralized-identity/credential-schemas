# Interaction Counter Credential (OriginVault)

Captures the number of specific user interactions (views, likes, downloads) on a digital item using Schema.org [InteractionCounter](https://schema.org/InteractionCounter).

## Core Properties

| Property | Type | Description |
|----------|------|-------------|
| `id` | `uri` | Identifier of the target item (content, app, etc.) |
| `schema:interactionType` | `uri` | Type of interaction (e.g., LikeAction, DownloadAction) |
| `schema:userInteractionCount` | `integer` | Count of interactions |
| `schema:dateCreated` | `dateTime` | When counting began |
| `schema:dateModified` | `dateTime` | Last update timestamp |

## Example

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/interaction-counter/context.json"
  ],
  "type": ["VerifiableCredential", "ov:InteractionCounterCredential"],
  "credentialSubject": {
    "id": "ipfs://bafy...", 
    "schema:interactionType": "https://schema.org/LikeAction",
    "schema:userInteractionCount": 1250,
    "schema:dateCreated": "2025-06-01T00:00:00Z",
    "schema:dateModified": "2025-06-10T12:00:00Z"
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-06-11T09:00:00Z"
}
``` 