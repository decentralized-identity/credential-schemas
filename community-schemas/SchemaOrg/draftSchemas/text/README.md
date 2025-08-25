# Text Schema

This schema defines a verifiable credential for representing textual content using schema.org vocabulary.

## Overview

The Text credential allows for the representation of textual content including documents, articles, notes, and other text-based materials. It extends the CreativeWork credential with text-specific properties and follows the [schema.org Text](https://schema.org/Text) data type structure.

## Schema Structure

The credential includes the following key properties:

### Required Fields
- `id`: The unique identifier for the text content (typically a URI)
- `schema:name`: The name or title of the text content

### Optional Fields (inherited from CreativeWork)
- `schema:description`: Description of the text content
- `schema:url`: URL where the text content can be accessed
- `schema:author`: The author of the text content (URI or object)
- `schema:creator`: The creator of the text content (URI or object)
- `schema:dateCreated`: Date and time when the text content was created
- `schema:datePublished`: Date and time when the text content was published
- `schema:dateModified`: Date and time when the text content was last modified
- `schema:genre`: Genre of the text content
- `schema:keywords`: Keywords or tags associated with the text content
- `schema:license`: License under which the text content is distributed
- `schema:copyrightHolder`: Copyright holder of the text content
- `schema:copyrightYear`: Year of copyright
- `schema:inLanguage`: Language of the text content (ISO 639-1 code)
- `schema:isAccessibleForFree`: Whether the text content is accessible for free
- `schema:thumbnailUrl`: URL of a thumbnail image for the text content
- `schema:image`: URL of an image representing the text content
- `schema:abstract`: Abstract or summary of the text content
- `schema:interactionStatistic`: Statistics about user interactions with the text content

### Text-Specific Fields
- `schema:isPartOf`: URI of a larger creative work of which this text is a part
- `schema:hasPart`: Array of URIs of text segments that are parts of this text
- `schema:citation`: Citations or references used in the text content
- `schema:wordCount`: Number of words in the text content
- `schema:characterCount`: Number of characters in the text content
- `schema:pageCount`: Number of pages in the text content
- `schema:duration`: Duration of the text content (for time-based media)
- `schema:text`: The actual text content
- `schema:textFormat`: The format of the text content (e.g., plain text, HTML, Markdown)
- `schema:encodingFormat`: The encoding format of the text content
- `schema:fileFormat`: The file format of the text content
- `schema:contentSize`: The size of the text content
- `schema:isFamilyFriendly`: Whether the text content is family friendly
- `schema:dateLastReviewed`: Date and time when the text content was last reviewed
- `schema:mainContentOfPage`: The main content of the text
- `schema:significantLinks`: The most significant URLs in the text content

### Accessibility Fields
- `schema:accessMode`: The human sensory perceptual system or cognitive faculty through which a person may process or perceive information
- `schema:accessibilityAPI`: Indicates that the resource is compatible with the referenced accessibility API
- `schema:accessibilityControl`: Identifies input methods that are sufficient to fully control the described resource
- `schema:accessibilityFeature`: Content features of the resource, such as accessible media, alternatives and supported enhancements for accessibility
- `schema:accessibilityHazard`: A characteristic of the described resource that is physiologically dangerous to some users
- `schema:accessibilitySummary`: A human-readable summary of specific accessibility features or deficiencies

## Text Content Structure

The `schema:text` property contains the actual textual content:

```json
{
  "schema:text": "This is the actual text content of the document...",
  "schema:textFormat": "plain/text",
  "schema:encodingFormat": "UTF-8"
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
    "schema:Text"
  ],
  "credentialSubject": {
    "id": "https://example.com/text/123",
    "schema:name": "Introduction to Verifiable Credentials",
    "schema:description": "A comprehensive guide to understanding verifiable credentials",
    "schema:url": "https://example.com/text/123",
    "schema:author": {
      "id": "did:web:author.example.com",
      "schema:name": "Jane Smith"
    },
    "schema:dateCreated": "2024-01-15T10:30:00Z",
    "schema:datePublished": "2024-01-20T14:00:00Z",
    "schema:genre": "Educational",
    "schema:keywords": ["verifiable credentials", "identity", "blockchain"],
    "schema:license": "https://creativecommons.org/licenses/by/4.0/",
    "schema:copyrightHolder": {
      "id": "did:web:publisher.example.com",
      "schema:name": "Example Publisher"
    },
    "schema:copyrightYear": 2024,
    "schema:inLanguage": "en",
    "schema:isAccessibleForFree": true,
    "schema:text": "Verifiable credentials are digital credentials that can be cryptographically verified...",
    "schema:textFormat": "text/plain",
    "schema:encodingFormat": "UTF-8",
    "schema:fileFormat": "text/plain",
    "schema:wordCount": 2500,
    "schema:characterCount": 15000,
    "schema:isFamilyFriendly": true,
    "schema:accessMode": "textual",
    "schema:accessibilityAPI": "ARIA",
    "schema:accessibilityFeature": "readingOrder",
    "schema:accessibilitySummary": "This document is screen reader compatible and includes proper heading structure."
  },
  "issuer": "did:web:publisher.example.com",
  "issuanceDate": "2024-01-20T14:00:00Z"
}
```

## Files

- `schema.json`: JSON Schema definition for the Text schema
- `context.json`: JSON-LD context file defining the vocabulary terms

## License

This project is licensed under the MIT License. 