# SchemaOrg Verifiable Credentials

This folder contains verifiable credential schemas based on [Schema.org](https://schema.org/) vocabulary, providing standardized representations for various types of digital content and creative works.

## Overview

The SchemaOrg schemas extend the W3C Verifiable Credentials standard with Schema.org vocabulary, enabling rich, semantic representation of digital content while maintaining interoperability with existing Schema.org implementations. These schemas are designed for use in decentralized identity systems and digital content management.

## Available Schemas

### Core Content Schemas

#### [Article Schema](./draftSchemas/article/)
Represents various types of articles including news articles, scholarly articles, technical articles, reports, and other written content.

- **Schema**: `schema:Article`
- **Extends**: CreativeWork
- **Key Features**: Article-specific properties, accessibility metadata, interaction statistics
- **Use Cases**: News articles, academic papers, technical documentation, reports

#### [Blog Schema](./draftSchemas/blog/)
Represents blog information including metadata, content structure, publishing details, and performance statistics.

- **Schema**: `schema:Blog`
- **Extends**: CreativeWork
- **Key Features**: Blog-specific properties, audience targeting, content aggregation
- **Use Cases**: Blog platforms, content management systems, publishing workflows

#### [BlogPosting Schema](./draftSchemas/blog-posting/)
Represents individual blog posts with article-specific properties and blog context.

- **Schema**: `schema:BlogPosting`
- **Extends**: Article
- **Key Features**: Blog post metadata, content relationships, interaction tracking
- **Use Cases**: Blog posts, social media content, online articles

#### [CreativeWork Schema](./draftSchemas/creative-work/)
Base schema for representing creative works including articles, books, videos, music, software, and other intellectual works.

- **Schema**: `schema:CreativeWork`
- **Base Schema**: Foundation for all creative content
- **Key Features**: Comprehensive metadata, authorship, licensing, accessibility
- **Use Cases**: All types of creative content, digital assets, intellectual property

### Digital Document Schemas

#### [DigitalDocument Schema](./draftSchemas/digital-document/)
Represents digital documents with comprehensive permission controls and access management.

- **Schema**: `schema:DigitalDocument`
- **Extends**: CreativeWork
- **Key Features**: Permission controls, audit trails, access management, document security
- **Use Cases**: Secure document sharing, digital rights management, confidential content

### Media Schemas

#### [MediaObject Schema](./draftSchemas/media-object/)
Represents media objects such as images, videos, audio files, and text objects with rich metadata.

- **Schema**: `schema:MediaObject`
- **Extends**: CreativeWork
- **Key Features**: Media-specific properties, encoding information, access controls
- **Use Cases**: Media libraries, content delivery, digital asset management

#### [Text Schema](./draftSchemas/text/)
Represents text-based content with semantic markup and structural information.

- **Schema**: `schema:Text`
- **Extends**: CreativeWork
- **Key Features**: Text-specific properties, semantic markup, content structure
- **Use Cases**: Text content, documents, structured text data

### Web Content Schemas

#### [WebPage Schema](./draftSchemas/web-page/)
Represents individual web pages with navigation, content, and metadata.

- **Schema**: `schema:WebPage`
- **Extends**: CreativeWork
- **Key Features**: Page-specific properties, navigation, content relationships
- **Use Cases**: Web pages, online content, digital publications

#### [WebSite Schema](./draftSchemas/web-site/)
Represents websites with site-wide metadata, structure, and organizational information.

- **Schema**: `schema:WebSite`
- **Extends**: CreativeWork
- **Key Features**: Site-wide properties, navigation structure, organizational metadata
- **Use Cases**: Websites, web applications, online platforms

## Schema Structure

Each schema follows a consistent structure:

```
schema-folder/
├── schema.json          # JSON Schema definition
├── context.json         # JSON-LD context file
└── README.md           # Schema documentation
```

### Common Properties

All schemas include these core properties:

- **Required Fields**: `id`, `schema:name`
- **Basic Metadata**: `schema:description`, `schema:url`, `schema:keywords`
- **Authorship**: `schema:author`, `schema:creator`, `schema:publisher`
- **Timeline**: `schema:dateCreated`, `schema:datePublished`, `schema:dateModified`
- **Rights**: `schema:license`, `schema:copyrightHolder`, `schema:copyrightYear`
- **Accessibility**: `schema:accessibilityFeature`, `schema:accessibilitySummary`
- **Interactions**: `schema:interactionStatistic`, `schema:aggregateRating`

## Usage Examples

### Basic Article Credential

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://w3id.org/security/suites/jws-2020/v1",
    {
      "schema": "https://schema.org/"
    }
  ],
  "type": [
    "VerifiableCredential",
    "schema:Article"
  ],
  "credentialSubject": {
    "id": "https://example.com/articles/verifiable-credentials-guide",
    "schema:name": "A Comprehensive Guide to Verifiable Credentials",
    "schema:description": "An in-depth exploration of verifiable credentials",
    "schema:author": {
      "id": "did:web:author.example.com",
      "schema:name": "Dr. Jane Smith"
    },
    "schema:datePublished": "2024-01-20T14:00:00Z",
    "schema:license": "https://creativecommons.org/licenses/by/4.0/"
  },
  "issuer": "did:web:publisher.example.com",
  "issuanceDate": "2024-01-20T14:00:00Z"
}
```

### Digital Document with Permissions

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://w3id.org/security/suites/jws-2020/v1",
    {
      "schema": "https://schema.org/"
    }
  ],
  "type": [
    "VerifiableCredential",
    "schema:DigitalDocument"
  ],
  "credentialSubject": {
    "id": "https://example.com/documents/confidential-report",
    "schema:name": "Confidential Financial Report 2024",
    "schema:fileFormat": "application/pdf",
    "schema:hasDigitalDocumentPermission": [
      {
        "id": "https://example.com/permissions/executive-access",
        "schema:permissionType": "read",
        "schema:permissionGrantedTo": {
          "id": "did:web:executive.example.com",
          "schema:name": "Executive Team"
        },
        "schema:permissionGrantedBy": {
          "id": "did:web:ceo.example.com",
          "schema:name": "CEO"
        }
      }
    ]
  }
}
```

## Benefits

### Interoperability
- **Schema.org Compatible**: Full alignment with Schema.org vocabulary
- **W3C Standards**: Based on W3C Verifiable Credentials standard
- **Semantic Web**: Rich semantic markup for machine-readable content

### Rich Metadata
- **Comprehensive Properties**: Extensive metadata for all content types
- **Accessibility Focus**: Built-in accessibility features and metadata
- **Rights Management**: Copyright, licensing, and permission controls

### Flexibility
- **Extensible**: Easy to extend for specific use cases
- **Modular**: Use individual schemas or combine them
- **Backward Compatible**: Works with existing Schema.org implementations

### Security & Trust
- **Verifiable**: Cryptographic proof of authenticity
- **Audit Trails**: Track content usage and modifications
- **Permission Controls**: Granular access and usage permissions

## Implementation Guidelines

### 1. Choose the Right Schema
- Use the most specific schema for your content type
- Extend base schemas for custom requirements
- Consider content relationships and hierarchies

### 2. Provide Required Fields
- Always include `id` and `schema:name`
- Use stable, resolvable URIs for identifiers
- Ensure names are descriptive and meaningful

### 3. Add Rich Metadata
- Include descriptive information in `schema:description`
- Add relevant keywords and tags
- Specify authors, creators, and publishers

### 4. Handle Permissions
- Use `schema:hasDigitalDocumentPermission` for access control
- Specify clear permission types and scopes
- Include audit trails for sensitive content

### 5. Consider Accessibility
- Add accessibility features and summaries
- Include alternative formats where possible
- Specify access modes and requirements

## Contributing

### Adding New Schemas
1. Create a new folder in `draftSchemas/`
2. Include `schema.json`, `context.json`, and `README.md`
3. Follow the existing schema structure and patterns
4. Update this README with schema documentation

### Schema Requirements
- Must extend appropriate base schema
- Include comprehensive documentation
- Provide usage examples
- Follow JSON Schema best practices

### Testing
- Validate against JSON Schema specification
- Test with JSON-LD processors
- Verify Schema.org compatibility
- Check accessibility compliance

## References

- [Schema.org](https://schema.org/) - Core vocabulary and documentation
- [W3C Verifiable Credentials](https://www.w3.org/TR/vc-data-model/) - Credential standard
- [JSON Schema](https://json-schema.org/) - Schema validation
- [JSON-LD](https://json-ld.org/) - Linked data format

## License

This project is licensed under the MIT License. See the [LICENSE.md](../../LICENSE.md) file for details.

## Support

For questions, issues, or contributions:
- Create an issue in the repository
- Review existing documentation and examples
- Check Schema.org documentation for vocabulary details
- Consult W3C specifications for credential standards
