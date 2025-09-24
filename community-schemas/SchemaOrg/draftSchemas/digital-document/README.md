# DigitalDocument Schema

This schema defines a verifiable credential for representing digital documents with comprehensive permission controls using schema.org vocabulary.

## Overview

The DigitalDocument credential allows for the representation of various types of digital documents including PDFs, Word documents, presentations, spreadsheets, and other digital files. It extends the CreativeWork credential with digital document-specific properties and includes comprehensive permission controls for managing access, usage, and distribution rights.

## Schema Structure

The credential includes the following key properties:

### Required Fields
- `id`: The unique identifier for the digital document (typically a URI)
- `schema:name`: The name or title of the digital document

### Digital Document-Specific Fields
- `schema:fileFormat`: The file format of the digital document (e.g., PDF, DOCX, PPTX)
- `schema:contentSize`: The size of the digital document content
- `schema:encodingFormat`: The encoding format of the digital document
- `schema:thumbnail`: Thumbnail image for the digital document

### Permission Control Fields
- `schema:hasDigitalDocumentPermission`: Array of digital document permissions associated with this document
- `schema:permissionType`: The type of permission granted (e.g., "read", "write", "share", "print")
- `schema:permissionScope`: The scope of the permission (e.g., "personal", "commercial", "educational")
- `schema:permissionDuration`: The duration of the permission
- `schema:permissionExpires`: When the permission expires
- `schema:permissionGrantedTo`: The entity to whom permission was granted
- `schema:permissionGrantedBy`: The entity that granted the permission
- `schema:permissionGrantedAt`: When the permission was granted
- `schema:permissionRevokedAt`: When the permission was revoked
- `schema:permissionRevokedBy`: The entity that revoked the permission
- `schema:permissionRevocationReason`: The reason for revoking the permission
- `schema:permissionConditions`: Conditions attached to the permission
- `schema:permissionRestrictions`: Restrictions on the permission
- `schema:permissionAllowedActions`: Actions allowed by the permission
- `schema:permissionDeniedActions`: Actions denied by the permission
- `schema:permissionGeographicScope`: Geographic scope of the permission
- `schema:permissionTimeScope`: Time scope of the permission
- `schema:permissionUsageLimit`: Usage limit for the permission
- `schema:permissionUsageCount`: Current usage count for the permission
- `schema:permissionWatermark`: Watermark applied to the document due to permission
- `schema:permissionEncryption`: Encryption applied to the document due to permission
- `schema:permissionAuditTrail`: Audit trail for permission usage

### Audit Trail Fields
- `schema:auditAction`: The action performed
- `schema:auditTimestamp`: When the action was performed
- `schema:auditActor`: The entity that performed the action
- `schema:auditDetails`: Details about the action performed

### Inherited Fields from CreativeWork
- `schema:description`: Description of the digital document
- `schema:url`: URL where the digital document can be accessed
- `schema:author`: The author of the digital document (URI or object)
- `schema:creator`: The creator of the digital document (URI or object)
- `schema:dateCreated`: Date and time when the digital document was created
- `schema:datePublished`: Date and time when the digital document was published
- `schema:dateModified`: Date and time when the digital document was last modified
- `schema:genre`: Genre of the digital document
- `schema:keywords`: Keywords or tags associated with the digital document
- `schema:license`: License under which the digital document is distributed
- `schema:copyrightHolder`: Copyright holder of the digital document (URI or object)
- `schema:copyrightYear`: Year of copyright
- `schema:inLanguage`: Language of the digital document (ISO 639-1 code)
- `schema:isAccessibleForFree`: Whether the digital document is accessible for free
- `schema:thumbnailUrl`: URL of a thumbnail image for the digital document
- `schema:image`: URL of an image representing the digital document
- `schema:isPartOf`: URI of a larger creative work of which this digital document is a part
- `schema:hasPart`: Array of URIs of creative works that are parts of this digital document
- `schema:citation`: Citations or references used in the digital document
- `schema:abstract`: Abstract or summary of the digital document
- `schema:wordCount`: Number of words in the digital document
- `schema:characterCount`: Number of characters in the digital document
- `schema:pageCount`: Number of pages in the digital document
- `schema:duration`: Duration of the digital document (for time-based media)
- `schema:interactionStatistic`: Statistics about user interactions with the digital document

### Accessibility Properties
- `schema:accessMode`: The human sensory perceptual system or cognitive faculty through which a person may process or perceive information
- `schema:accessModeSufficient`: A list of single or combined accessModes that are sufficient to understand all the intellectual content
- `schema:accessibilityAPI`: Indicates that the resource is compatible with the referenced accessibility API
- `schema:accessibilityControl`: Identifies input methods that are sufficient to fully control the described resource
- `schema:accessibilityFeature`: Content features of the resource, such as accessible media, alternatives and supported enhancements for accessibility
- `schema:accessibilityHazard`: A characteristic of the described resource that is physiologically dangerous to some users
- `schema:accessibilitySummary`: A human-readable summary of specific accessibility features or deficiencies

### Additional Properties
- `schema:about`: The subject matter of the content
- `schema:accountablePerson`: Specifies the Person that is legally accountable for the DigitalDocument
- `schema:aggregateRating`: The overall rating, based on a collection of reviews or ratings, of the item
- `schema:alternativeHeadline`: A secondary title of the DigitalDocument
- `schema:commentCount`: The number of comments this DigitalDocument has received
- `schema:contentLocation`: The location depicted or described in the content
- `schema:contentRating`: Official rating of a piece of content
- `schema:contributor`: A secondary contributor to the DigitalDocument
- `schema:copyrightNotice`: Text of a notice appropriate for describing the copyright aspects
- `schema:countryOfOrigin`: The country of origin of something, including products as well as creative works
- `schema:creativeWorkStatus`: The status of a creative work in terms of its stage in a lifecycle
- `schema:editor`: Specifies the Person who edited the DigitalDocument
- `schema:expires`: Date the content expires and is no longer useful or available
- `schema:headline`: Headline of the digital document
- `schema:isFamilyFriendly`: Indicates whether this content is family friendly
- `schema:locationCreated`: The location where the DigitalDocument was created
- `schema:mainEntity`: Indicates the primary entity described in some page or other CreativeWork
- `schema:producer`: The person or organization who produced the work
- `schema:publisher`: The publisher of the digital document
- `schema:review`: A review of the item
- `schema:text`: The textual content of this DigitalDocument
- `schema:timeRequired`: Approximate time it usually takes to work with the content
- `schema:typicalAgeRange`: The typical expected age range, e.g. '7-9', '11-'
- `schema:version`: The version of the DigitalDocument
- `schema:alternateName`: An alias for the item
- `schema:identifier`: Any kind of identifier for the digital document
- `schema:mainEntityOfPage`: Indicates a page (or other CreativeWork) for which this thing is the main entity being described
- `schema:sameAs`: URL of a reference Web page that unambiguously indicates the item's identity
- `schema:subjectOf`: A CreativeWork or Event about this Thing

## Permission Types

The schema supports various permission types:
- **Read**: Permission to view the document
- **Write**: Permission to edit the document
- **Share**: Permission to share the document with others
- **Print**: Permission to print the document
- **Download**: Permission to download the document
- **Copy**: Permission to copy content from the document
- **Distribute**: Permission to distribute the document
- **Commercial Use**: Permission to use the document for commercial purposes
- **Modify**: Permission to modify the document
- **Derivative Works**: Permission to create derivative works

## Permission Scopes

- **Personal**: For personal use only
- **Commercial**: For commercial use
- **Educational**: For educational purposes
- **Research**: For research purposes
- **Internal**: For internal organizational use
- **Public**: For public distribution

## Author/Creator Structure

The `schema:author`, `schema:creator`, `schema:contributor`, `schema:editor`, `schema:producer`, and `schema:publisher` properties can be either a URI string or an object:

```json
{
  "id": "did:web:example.com",
  "schema:name": "John Doe"
}
```

## Permission Structure

The `schema:hasDigitalDocumentPermission` property uses a nested structure:

```json
{
  "id": "https://example.com/permissions/123",
  "schema:permissionType": "read",
  "schema:permissionScope": "personal",
  "schema:permissionDuration": "P1Y",
  "schema:permissionExpires": "2025-01-20T14:00:00Z",
  "schema:permissionGrantedTo": {
    "id": "did:web:user.example.com",
    "schema:name": "Jane Smith"
  },
  "schema:permissionGrantedBy": {
    "id": "did:web:owner.example.com",
    "schema:name": "Document Owner"
  },
  "schema:permissionGrantedAt": "2024-01-20T14:00:00Z",
  "schema:permissionAllowedActions": ["view", "print"],
  "schema:permissionDeniedActions": ["edit", "share", "download"],
  "schema:permissionUsageLimit": 10,
  "schema:permissionUsageCount": 3
}
```

## Audit Trail Structure

The `schema:permissionAuditTrail` property uses a nested structure:

```json
{
  "id": "https://example.com/audit/456",
  "schema:auditAction": "document_viewed",
  "schema:auditTimestamp": "2024-01-20T15:30:00Z",
  "schema:auditActor": {
    "id": "did:web:user.example.com",
    "schema:name": "Jane Smith"
  },
  "schema:auditDetails": "Document accessed via web interface"
}
```

## Usage Example

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
    "id": "https://example.com/documents/confidential-report-2024",
    "schema:name": "Confidential Financial Report 2024",
    "schema:description": "Annual financial report with sensitive business information",
    "schema:url": "https://example.com/documents/confidential-report-2024.pdf",
    "schema:author": {
      "id": "did:web:author.example.com",
      "schema:name": "Financial Department"
    },
    "schema:dateCreated": "2024-01-15T10:30:00Z",
    "schema:datePublished": "2024-01-20T14:00:00Z",
    "schema:fileFormat": "application/pdf",
    "schema:contentSize": "2.5MB",
    "schema:encodingFormat": "UTF-8",
    "schema:genre": "Business Report",
    "schema:keywords": ["financial", "confidential", "annual report", "business"],
    "schema:license": "https://example.com/licenses/internal-use-only",
    "schema:copyrightHolder": {
      "id": "did:web:company.example.com",
      "schema:name": "Example Corporation"
    },
    "schema:copyrightYear": 2024,
    "schema:inLanguage": "en",
    "schema:isAccessibleForFree": false,
    "schema:wordCount": 15000,
    "schema:characterCount": 90000,
    "schema:pageCount": 45,
    "schema:abstract": "This confidential report contains detailed financial analysis...",
    "schema:accessibilityFeature": ["alternativeText", "highContrast"],
    "schema:isFamilyFriendly": true,
    "schema:typicalAgeRange": "18+",
    "schema:hasDigitalDocumentPermission": [
      {
        "id": "https://example.com/permissions/executive-access",
        "schema:permissionType": "read",
        "schema:permissionScope": "internal",
        "schema:permissionDuration": "P1Y",
        "schema:permissionExpires": "2025-01-20T14:00:00Z",
        "schema:permissionGrantedTo": {
          "id": "did:web:executive.example.com",
          "schema:name": "Executive Team"
        },
        "schema:permissionGrantedBy": {
          "id": "did:web:ceo.example.com",
          "schema:name": "CEO"
        },
        "schema:permissionGrantedAt": "2024-01-20T14:00:00Z",
        "schema:permissionAllowedActions": ["view", "print", "download"],
        "schema:permissionDeniedActions": ["edit", "share"],
        "schema:permissionGeographicScope": ["United States", "Canada"],
        "schema:permissionUsageLimit": 100,
        "schema:permissionUsageCount": 15,
        "schema:permissionWatermark": "CONFIDENTIAL - Executive Access Only",
        "schema:permissionEncryption": "AES-256",
        "schema:permissionAuditTrail": [
          {
            "id": "https://example.com/audit/exec-view-1",
            "schema:auditAction": "document_viewed",
            "schema:auditTimestamp": "2024-01-20T15:30:00Z",
            "schema:auditActor": {
              "id": "did:web:executive.example.com",
              "schema:name": "Executive Team"
            },
            "schema:auditDetails": "Document accessed via secure portal"
          }
        ]
      }
    ]
  },
  "issuer": "did:web:company.example.com",
  "issuanceDate": "2024-01-20T14:00:00Z"
}
```

## Files

- `schema.json`: JSON Schema definition for the DigitalDocument schema
- `context.json`: JSON-LD context file defining the vocabulary terms

## License

This project is licensed under the MIT License. 