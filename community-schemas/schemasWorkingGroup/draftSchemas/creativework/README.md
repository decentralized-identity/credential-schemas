# CreativeWork Schema

This schema defines a verifiable credential for representing creative works using schema.org vocabulary.

## Overview

The CreativeWork credential allows for the representation of various types of creative content including articles, books, videos, music, software, and other intellectual works. It follows the schema.org CreativeWork type structure and is designed to be interoperable with existing schema.org implementations.

## Schema Structure

The credential includes the following key properties:

### Required Fields
- `id`: The unique identifier for the creative work (typically a URI)
- `schema:name`: The name or title of the creative work

### Optional Fields
- `schema:description`: Description of the creative work
- `schema:url`: URL where the creative work can be accessed
- `schema:author`: The author of the creative work (URI or object)
- `schema:creator`: The creator of the creative work (URI or object)
- `schema:dateCreated`: Date and time when the creative work was created
- `schema:datePublished`: Date and time when the creative work was published
- `schema:dateModified`: Date and time when the creative work was last modified
- `schema:genre`: Genre of the creative work
- `schema:keywords`: Keywords or tags associated with the creative work
- `schema:license`: License under which the creative work is distributed
- `schema:copyrightHolder`: Copyright holder of the creative work
- `schema:copyrightYear`: Year of copyright
- `schema:inLanguage`: Language of the creative work (ISO 639-1 code)
- `schema:isAccessibleForFree`: Whether the creative work is accessible for free
- `schema:fileFormat`: File format of the creative work
- `schema:contentSize`: Size of the creative work content
- `schema:encodingFormat`: Encoding format of the creative work
- `schema:thumbnailUrl`: URL of a thumbnail image for the creative work
- `schema:image`: URL of an image representing the creative work
- `schema:isPartOf`: URI of a larger creative work of which this is a part
- `schema:hasPart`: Array of URIs of creative works that are parts of this work
- `schema:citation`: Citations or references used in the creative work
- `schema:abstract`: Abstract or summary of the creative work
- `schema:wordCount`: Number of words in the creative work
- `schema:characterCount`: Number of characters in the creative work
- `schema:pageCount`: Number of pages in the creative work
- `schema:duration`: Duration of the creative work (for time-based media)
- `schema:interactionStatistic`: Statistics about user interactions with the creative work

## Author/Creator Structure

The `schema:author` and `schema:creator` properties can be either a URI string or an object:

```json
{
  "id": "did:web:example.com",
  "schema:name": "John Doe"
}
```

## Interaction Statistics Structure

The `schema:interactionStatistic` property uses a nested structure:

```json
{
  "schema:interactionType": "https://schema.org/LikeAction",
  "schema:userInteractionCount": 150
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
    "schema:CreativeWork"
  ],
  "credentialSubject": {
    "id": "https://example.com/creative-work/123",
    "schema:name": "Introduction to Verifiable Credentials",
    "schema:description": "A comprehensive guide to understanding verifiable credentials",
    "schema:url": "https://example.com/creative-work/123",
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
    "schema:fileFormat": "text/html",
    "schema:wordCount": 2500,
    "schema:characterCount": 15000,
    "schema:abstract": "This work provides a comprehensive overview of verifiable credentials..."
  },
  "issuer": "did:web:publisher.example.com",
  "issuanceDate": "2024-01-20T14:00:00Z"
}
```

## Files

- `schema.json`: JSON Schema definition for the CreativeWork schema
- `context.json`: JSON-LD context file defining the vocabulary terms

## License

This project is licensed under the MIT License. 