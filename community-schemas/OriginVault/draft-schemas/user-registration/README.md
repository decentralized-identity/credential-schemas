# User Registration (OriginVault)

This credential records user registration events using strictly Schema.org types and properties for maximum interoperability. It leverages [Schema.org RegisterAction](https://schema.org/RegisterAction) as the core action type and [Schema.org Person](https://schema.org/Person) for user representation.

## Schema.org Compliance

This credential is designed to be fully compliant with Schema.org standards by:

- Using `RegisterAction` as the primary action type
- Representing users as `Person` objects
- Using `Service`, `WebSite`, or `SoftwareApplication` for the registration target
- Leveraging `EntryPoint` for registration endpoints
- Following Schema.org property naming conventions

## Core Structure

The credential centers around a `schema:RegisterAction` object that contains:

| Property | Type | Description |
|----------|------|-------------|
| `schema:agent` | `Person` or `uri` | The person performing the registration |
| `schema:object` | `Service/WebSite/SoftwareApplication` | The service being registered for |
| `schema:target` | `EntryPoint` | The registration endpoint |
| `schema:startTime` | `dateTime` | When registration began |
| `schema:endTime` | `dateTime` | When registration completed |
| `schema:actionStatus` | `ActionStatusType` | Status of the registration |
| `schema:result` | `Person` | The registered user |
| `schema:error` | `Thing` | Error information (if failed) |
| `schema:instrument` | `SoftwareApplication/WebSite` | Tool used for registration |
| `schema:location` | `Place/PostalAddress` | Geographic location |

## Schema.org Person Properties

The `schema:agent` and `schema:result` properties use Schema.org Person with:

- `schema:@id`: Unique identifier (DID, URI)
- `schema:name`: Full name
- `schema:email`: Email address
- `schema:identifier`: Structured identifiers
- `schema:address`: Geographic address
- `schema:accountId`: Account identifier
- `schema:username`: Chosen username

## Examples

### Basic User Registration

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/user-registration/context.json"
  ],
  "type": ["VerifiableCredential", "ov:UserRegistrationCredential"],
  "credentialSubject": {
    "id": "urn:uuid:12345678-1234-1234-1234-123456789abc",
    "schema:RegisterAction": {
      "@type": "RegisterAction",
      "schema:agent": {
        "@type": "Person",
        "schema:@id": "did:web:alice.example",
        "schema:name": "Alice Johnson",
        "schema:email": "alice@example.com"
      },
      "schema:object": {
        "@type": "Service",
        "schema:name": "OriginVault",
        "schema:url": "https://originvault.box"
      },
      "schema:target": {
        "@type": "EntryPoint",
        "schema:urlTemplate": "https://originvault.box/register",
        "schema:name": "Registration Endpoint"
      },
      "schema:startTime": "2025-01-10T12:34:56Z",
      "schema:endTime": "2025-01-10T12:35:01Z",
      "schema:actionStatus": "CompletedActionStatus",
      "schema:result": {
        "@type": "Person",
        "schema:@id": "did:web:alice.example",
        "schema:name": "Alice Johnson",
        "schema:email": "alice@example.com",
        "schema:accountId": "user_12345",
        "schema:username": "alice_creator"
      }
    }
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-01-10T12:35:01Z"
}
```

### Enhanced Registration with Location and Instrument

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/user-registration/context.json"
  ],
  "type": ["VerifiableCredential", "ov:UserRegistrationCredential"],
  "credentialSubject": {
    "id": "urn:uuid:87654321-4321-4321-4321-cba987654321",
    "schema:RegisterAction": {
      "@type": "RegisterAction",
      "schema:agent": {
        "@type": "Person",
        "schema:@id": "did:web:bob.example",
        "schema:name": "Bob Smith",
        "schema:email": "bob@example.com",
        "schema:identifier": {
          "schema:propertyID": "did",
          "schema:value": "did:web:bob.example"
        },
        "schema:address": {
          "schema:addressCountry": "US",
          "schema:addressLocality": "San Francisco",
          "schema:addressRegion": "CA"
        }
      },
      "schema:object": {
        "@type": "SoftwareApplication",
        "schema:name": "OriginVault Mobile App",
        "schema:url": "https://originvault.box/app"
      },
      "schema:target": {
        "@type": "EntryPoint",
        "schema:urlTemplate": "https://originvault.box/api/register",
        "schema:name": "API Registration Endpoint"
      },
      "schema:startTime": "2025-01-10T14:20:00Z",
      "schema:endTime": "2025-01-10T14:20:30Z",
      "schema:actionStatus": "CompletedActionStatus",
      "schema:result": {
        "@type": "Person",
        "schema:@id": "did:web:bob.example",
        "schema:name": "Bob Smith",
        "schema:email": "bob@example.com",
        "schema:accountId": "user_67890",
        "schema:username": "bob_artist"
      },
      "schema:instrument": {
        "@type": "SoftwareApplication",
        "schema:name": "OriginVault iOS App",
        "schema:url": "https://apps.apple.com/app/originvault"
      },
      "schema:location": {
        "@type": "Place",
        "schema:addressCountry": "US",
        "schema:addressLocality": "San Francisco",
        "schema:addressRegion": "CA"
      }
    }
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-01-10T14:20:30Z"
}
```

### Failed Registration Example

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/user-registration/context.json"
  ],
  "type": ["VerifiableCredential", "ov:UserRegistrationCredential"],
  "credentialSubject": {
    "id": "urn:uuid:failed-reg-1234-5678-9abc-def012345678",
    "schema:RegisterAction": {
      "@type": "RegisterAction",
      "schema:agent": {
        "@type": "Person",
        "schema:@id": "did:web:charlie.example",
        "schema:name": "Charlie Brown",
        "schema:email": "charlie@example.com"
      },
      "schema:object": {
        "@type": "Service",
        "schema:name": "OriginVault",
        "schema:url": "https://originvault.box"
      },
      "schema:target": {
        "@type": "EntryPoint",
        "schema:urlTemplate": "https://originvault.box/register",
        "schema:name": "Registration Endpoint"
      },
      "schema:startTime": "2025-01-10T15:00:00Z",
      "schema:endTime": "2025-01-10T15:00:05Z",
      "schema:actionStatus": "FailedActionStatus",
      "schema:error": {
        "@type": "Thing",
        "schema:name": "EmailAlreadyExists",
        "schema:description": "Email address is already registered"
      }
    }
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-01-10T15:00:05Z"
}
```

## Benefits of Schema.org Compliance

1. **Web Interoperability**: Can be consumed by any Schema.org-aware system
2. **Search Engine Optimization**: Registration events can be indexed by search engines
3. **Semantic Web Integration**: Works with RDF and linked data systems
4. **Standard Compliance**: Follows established web standards
5. **Tool Compatibility**: Works with Schema.org validation tools

## Schema.org Action Status Types

- `ActiveActionStatus`: Registration is in progress
- `CompletedActionStatus`: Registration completed successfully
- `FailedActionStatus`: Registration failed
- `PotentialActionStatus`: Registration is planned but not yet started

## Integration with Web Standards

This credential can be embedded in HTML as JSON-LD:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "RegisterAction",
  "agent": {
    "@type": "Person",
    "name": "Alice Johnson",
    "email": "alice@example.com"
  },
  "object": {
    "@type": "Service",
    "name": "OriginVault"
  },
  "actionStatus": "CompletedActionStatus"
}
</script>
``` 