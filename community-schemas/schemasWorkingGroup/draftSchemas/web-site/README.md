# WebSite Schema

This schema defines a verifiable credential for representing websites using schema.org vocabulary.

## Overview

The WebSite credential allows for the representation of website information including metadata, content structure, audience targeting, and performance statistics. It extends the CreativeWork credential with website-specific properties and follows the schema.org WebSite type structure.

## Schema Structure

The credential includes the following key properties:

### Required Fields
- `id`: The unique identifier for the website (typically a URI)
- `schema:name`: The name or title of the website

### Optional Fields (inherited from CreativeWork)
- `schema:description`: Description of the website
- `schema:url`: URL of the website
- `schema:author`: The author of the website (URI or object)
- `schema:creator`: The creator of the website (URI or object)
- `schema:dateCreated`: Date and time when the website was created
- `schema:datePublished`: Date and time when the website was published
- `schema:dateModified`: Date and time when the website was last modified
- `schema:genre`: Genre of the website
- `schema:keywords`: Keywords or tags associated with the website
- `schema:license`: License under which the website is distributed
- `schema:copyrightHolder`: Copyright holder of the website
- `schema:copyrightYear`: Year of copyright
- `schema:inLanguage`: Language of the website (ISO 639-1 code)
- `schema:isAccessibleForFree`: Whether the website is accessible for free
- `schema:thumbnailUrl`: URL of a thumbnail image for the website
- `schema:image`: URL of an image representing the website
- `schema:abstract`: Abstract or summary of the website
- `schema:interactionStatistic`: Statistics about user interactions with the website

### WebSite-Specific Fields
- `schema:hasPart`: Array of URIs of web pages that are parts of this website
- `schema:isPartOf`: URI of a larger website of which this is a part
- `schema:mainEntity`: The main entity described on the website
- `schema:about`: The subject matter of the website
- `schema:audience`: Information about the target audience
- `schema:breadcrumb`: A breadcrumb trail for the website
- `schema:lastReviewed`: Date and time when the website was last reviewed
- `schema:reviewedBy`: The reviewer of the website
- `schema:significantLink`: Significant links on the website
- `schema:specialty`: The specialty of the website

## Audience Structure

The `schema:audience` property uses a nested structure:

```json
{
  "schema:audienceType": "Researchers",
  "schema:geographicArea": "Global"
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
    "schema:WebSite"
  ],
  "credentialSubject": {
    "id": "https://example.com",
    "schema:name": "Example Website",
    "schema:description": "A comprehensive website about verifiable credentials",
    "schema:url": "https://example.com",
    "schema:author": {
      "id": "did:web:author.example.com",
      "schema:name": "Jane Smith"
    },
    "schema:dateCreated": "2024-01-15T10:30:00Z",
    "schema:datePublished": "2024-01-20T14:00:00Z",
    "schema:genre": "Educational",
    "schema:keywords": ["verifiable credentials", "identity", "blockchain"],
    "schema:license": "https://creativecommons.org/licenses/by/4.0/",
    "schema:inLanguage": "en",
    "schema:isAccessibleForFree": true,
    "schema:hasPart": [
      "https://example.com/about",
      "https://example.com/contact",
      "https://example.com/blog"
    ],
    "schema:mainEntity": "https://example.com/entity/123",
    "schema:about": "https://example.com/topic/verifiable-credentials",
    "schema:audience": {
      "schema:audienceType": "Developers",
      "schema:geographicArea": "Global"
    },
    "schema:breadcrumb": "Home > About > Contact",
    "schema:lastReviewed": "2024-01-25T09:00:00Z",
    "schema:reviewedBy": {
      "id": "did:web:reviewer.example.com",
      "schema:name": "John Doe"
    },
    "schema:significantLink": [
      "https://example.com/important-page",
      "https://example.com/resources"
    ],
    "schema:specialty": "Digital Identity"
  },
  "issuer": "did:web:publisher.example.com",
  "issuanceDate": "2024-01-20T14:00:00Z"
}
```

## Files

- `schema.json`: JSON Schema definition for the WebSite schema
- `context.json`: JSON-LD context file defining the vocabulary terms

## License

This project is licensed under the MIT License. 