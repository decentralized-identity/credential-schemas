# OriginVault Draft Schemas

This directory contains draft schemas developed by OriginVault for various credential types. All schemas are designed with Schema.org compliance for maximum interoperability and web integration.

## Available Schemas

### 1. Content Registration
**Location**: `content-registration/`

A credential that registers digital content on OriginVault, anchoring its hash, registration date, and registrant. Aligns with [Schema.org RegisterAction](https://schema.org/RegisterAction) patterns.

**Key Features**:
- Content hash verification and storage
- Registrant identification (Person/Organization)
- Schema.org RegisterAction integration
- Perceptual hash support for duplicate detection
- Metadata preservation (filename, size, format)

**Core Properties**:
- `schema:identifier` - Structured content hash
- `schema:dateCreated` - Registration timestamp
- `schema:agent` - Entity that registered the content
- `schema:url` - Canonical content URL
- `ov:registrationAction` - Optional Schema.org action context

[View Schema Details](./content-registration/)

### 2. User Registration
**Location**: `user-registration/`

A credential that records user registration events using strictly Schema.org types and properties. Centers around `RegisterAction` and `Person` objects for maximum interoperability.

**Key Features**:
- Schema.org RegisterAction as primary action type
- Person objects for user representation
- Service/WebSite/SoftwareApplication for registration targets
- EntryPoint for registration endpoints
- Full Schema.org compliance

**Core Properties**:
- `schema:RegisterAction` - Complete registration action context
- `schema:agent` - Person performing registration
- `schema:object` - Service being registered for
- `schema:target` - Registration endpoint
- `schema:result` - Registered user as Person object

[View Schema Details](./user-registration/)

### 3. Proof of Presence
**Location**: `proof-of-presence/`

A credential proving that a subject (person or device) was present at a specific geographic location and time using Schema.org standards.

**Key Features**:
- Schema.org Place and GeoCoordinates objects
- Multiple verification methods (GPS, WiFi, NFC, etc.)
- Temporal presence tracking (start/end times)
- Agent identification (Person/Device)

**Core Properties**:
- `schema:location` - Place object with coordinates
- `schema:startDate` / `schema:endDate` - Presence timeframe
- `schema:measurementTechnique` - Verification method
- `schema:agent` - Person or device present

[View Schema Details](./proof-of-presence/)

### 4. Proof of Upload
**Location**: `proof-of-upload/`

A credential that attests that a piece of content was uploaded to a storage location at a given time using Schema.org standards.

**Key Features**:
- Upload hash verification
- Storage location tracking
- Uploader identification
- File metadata preservation
- Schema.org CreateAction integration

**Core Properties**:
- `schema:identifier` - Structured upload hash
- `schema:uploadDate` - Upload timestamp
- `schema:agent` - Entity that uploaded content
- `schema:contentUrl` - Storage location
- `schema:uploadAction` - Optional CreateAction context

[View Schema Details](./proof-of-upload/)

### 5. DID Assertion
**Location**: `did-assertion/`

A credential that asserts a claim about a subject using Schema.org review standards. Provides structured way to make and verify claims about entities.

**Key Features**:
- Schema.org review and rating patterns
- Multiple review events over time
- Audit trail of claim changes
- Structured claim validation

**Core Properties**:
- `schema:reviewAspect` - Description of claim being reviewed
- `schema:author` - URI of claim author
- `schema:reviewer` - Entity responsible for validation
- `schema:review` - Array of review events
- `schema:reviewRating` - Rating objects for evaluations

[View Schema Details](./did-assertion/)

### 6. Software Source Code
**Location**: `software-source-code/`

Describes software source code repositories, languages, platforms, and maintainers using `SoftwareSourceCode`.

[View Schema Details](./software-source-code/)

### 7. Software Application
**Location**: `software-application/`

Describes software applications, versions, and platforms using `SoftwareApplication`.

[View Schema Details](./software-application/)

### 8. Interaction Counter
**Location**: `interaction-counter/`

Counts user interactions such as likes, views, and downloads using `InteractionCounter`.

[View Schema Details](./interaction-counter/)

### 9. Action Access Specification
**Location**: `action-access-specification/`

Defines platform, time, region, and subscription prerequisites for actions using `ActionAccessSpecification`.

[View Schema Details](./action-access-specification/)

### 10. Contributor
**Location**: `contributor/`

Attests to secondary contributors to CreativeWorks or Events using Schema.org `contributor` property.

[View Schema Details](./contributor/)

### 11. Ownership Info
**Location**: `ownership-info/`

Provides structured ownership information for products and services using Schema.org `OwnershipInfo` type.

[View Schema Details](./ownership-info/)

## Schema.org Compliance

All OriginVault schemas follow Schema.org standards for maximum interoperability:

### Standard Schema.org Terms Used
- **Action Types**: `RegisterAction`, `CreateAction`
- **Entity Types**: `Person`, `Organization`, `Place`, `Service`, `WebSite`, `SoftwareApplication`
- **Properties**: `agent`, `object`, `target`, `startTime`, `endTime`, `actionStatus`, `result`
- **Review System**: `review`, `reviewRating`, `ratingValue`, `reviewAspect`, `author`, `reviewer`
- **Location**: `location`, `geo`, `latitude`, `longitude`, `address`
- **Identification**: `identifier`, `name`, `url`, `description`, `dateCreated`, `dateModified`

### Custom OriginVault Terms
- `ov:registrationAction` - Schema.org action context for registrations
- `ov:softPerceptualHash` - 8×8 perceptual hash
- `ov:mediumPerceptualHash` - 16×16 perceptual hash  
- `ov:precisePerceptualHash` - 24×24 perceptual hash
- `ov:path` - Storage path in object store
- `ov:status` - Processing status
- `ov:color` - Dominant color (hex)
- `ov:colorCode` - Color hash code
- `ov:mnemonicId` - Human-readable snowflake ID

## Naming Convention

All schemas follow the established naming convention:
- **Directories**: lowercase with hyphens (e.g., `content-registration`)
- **Files**: descriptive names with proper extensions
- **Context URLs**: Match directory structure
- **Schema IDs**: Follow GitHub raw URL pattern

## Example Usage

### Content Registration
```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OriginVault/draft-schemas/content-registration/context.json"
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
    }
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-01-10T12:35:01Z"
}
```

### User Registration
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
      "schema:actionStatus": "CompletedActionStatus"
    }
  },
  "issuer": "did:web:originvault.box",
  "issuanceDate": "2025-01-10T12:35:01Z"
}
```

## Schema Development Process

All schemas in this directory are in draft status and may undergo changes before final release. The development process follows:

1. **Schema.org Compliance**: All schemas prioritize Schema.org standards
2. **Interoperability**: Designed for maximum compatibility with web systems
3. **Extensibility**: Structured to support future enhancements
4. **Documentation**: Comprehensive README files for each schema
5. **Examples**: Practical usage examples for implementation

## Integration Benefits

- **Web Interoperability**: Can be consumed by any Schema.org-aware system
- **Search Engine Optimization**: Credentials can be indexed by search engines
- **Semantic Web Integration**: Works with RDF and linked data systems
- **Tool Compatibility**: Works with Schema.org validation tools
- **Future-Proof**: Based on established web standards

---

For detailed documentation on each schema, see the individual README files in each schema directory.
