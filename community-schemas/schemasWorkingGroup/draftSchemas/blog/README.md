# Blog Schema

This schema defines a verifiable credential for representing blogs using schema.org vocabulary.

## Overview

The Blog credential allows for the representation of blog information including metadata, content structure, publishing details, and performance statistics. It extends the CreativeWork credential with blog-specific properties and follows the schema.org Blog type structure.

## Schema Structure

The credential includes the following key properties:

### Required Fields
- `id`: The unique identifier for the blog (typically a URI)
- `schema:name`: The name or title of the blog

### Optional Fields (inherited from CreativeWork)
- `schema:description`: Description of the blog
- `schema:url`: URL of the blog
- `schema:author`: The author of the blog (URI or object)
- `schema:creator`: The creator of the blog (URI or object)
- `schema:dateCreated`: Date and time when the blog was created
- `schema:datePublished`: Date and time when the blog was published
- `schema:dateModified`: Date and time when the blog was last modified
- `schema:genre`: Genre of the blog
- `schema:keywords`: Keywords or tags associated with the blog
- `schema:license`: License under which the blog is distributed
- `schema:copyrightHolder`: Copyright holder of the blog
- `schema:copyrightYear`: Year of copyright
- `schema:inLanguage`: Language of the blog (ISO 639-1 code)
- `schema:isAccessibleForFree`: Whether the blog is accessible for free
- `schema:thumbnailUrl`: URL of a thumbnail image for the blog
- `schema:image`: URL of an image representing the blog
- `schema:abstract`: Abstract or summary of the blog
- `schema:interactionStatistic`: Statistics about user interactions with the blog

### Blog-Specific Fields
- `schema:isPartOf`: URI of a larger website of which this blog is a part
- `schema:hasPart`: Array of URIs of blog posts that are parts of this blog
- `schema:mainEntity`: The main entity described on the blog
- `schema:about`: The subject matter of the blog
- `schema:breadcrumb`: A breadcrumb trail for the blog
- `schema:lastReviewed`: Date and time when the blog was last reviewed
- `schema:reviewedBy`: The reviewer of the blog
- `schema:significantLink`: Significant links on the blog
- `schema:specialty`: The specialty of the blog
- `schema:blogPost`: Array of URIs of blog posts in this blog
- `schema:blogPosts`: Array of URIs of blog posts in this blog (alternative to blogPost)
- `schema:issn`: The International Standard Serial Number (ISSN) of the blog
- `schema:issueNumber`: The issue number of the blog
- `schema:volumeNumber`: The volume number of the blog
- `schema:publisher`: The publisher of the blog
- `schema:editor`: The editor of the blog
- `schema:audience`: Information about the target audience
- `schema:wordCount`: Total number of words across all blog posts
- `schema:characterCount`: Total number of characters across all blog posts
- `schema:numberOfItems`: Number of blog posts in the blog
- `schema:isFamilyFriendly`: Whether the blog is family friendly
- `schema:dateLastReviewed`: Date and time when the blog was last reviewed
- `schema:mainContentOfPage`: The main content of the blog
- `schema:significantLinks`: The most significant URLs on the blog

## Audience Structure

The `schema:audience` property uses a nested structure:

```json
{
  "schema:audienceType": "Developers",
  "schema:geographicArea": "Global"
}
```

## Publisher/Editor Structure

The `schema:publisher` and `schema:editor` properties can be either a URI string or an object:

```json
{
  "id": "did:web:publisher.example.com",
  "schema:name": "Example Publisher"
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
    "schema:Blog"
  ],
  "credentialSubject": {
    "id": "https://example.com/blog",
    "schema:name": "Tech Insights Blog",
    "schema:description": "A comprehensive blog about technology trends and insights",
    "schema:url": "https://example.com/blog",
    "schema:author": {
      "id": "did:web:author.example.com",
      "schema:name": "Jane Smith"
    },
    "schema:dateCreated": "2024-01-15T10:30:00Z",
    "schema:datePublished": "2024-01-20T14:00:00Z",
    "schema:genre": "Technology",
    "schema:keywords": ["technology", "insights", "trends", "innovation"],
    "schema:license": "https://creativecommons.org/licenses/by/4.0/",
    "schema:inLanguage": "en",
    "schema:isAccessibleForFree": true,
    "schema:isPartOf": "https://example.com",
    "schema:mainEntity": "https://example.com/entity/tech-blog",
    "schema:about": "https://example.com/topic/technology",
    "schema:breadcrumb": "Home > Blog",
    "schema:lastReviewed": "2024-01-25T09:00:00Z",
    "schema:reviewedBy": {
      "id": "did:web:reviewer.example.com",
      "schema:name": "John Doe"
    },
    "schema:significantLink": [
      "https://example.com/blog/latest",
      "https://example.com/blog/popular"
    ],
    "schema:specialty": "Technology Trends",
    "schema:blogPost": [
      "https://example.com/blog/post-1",
      "https://example.com/blog/post-2",
      "https://example.com/blog/post-3"
    ],
    "schema:issn": "1234-5678",
    "schema:issueNumber": "1",
    "schema:volumeNumber": "2024",
    "schema:publisher": {
      "id": "did:web:publisher.example.com",
      "schema:name": "Example Publisher"
    },
    "schema:editor": {
      "id": "did:web:editor.example.com",
      "schema:name": "Editor Team"
    },
    "schema:audience": {
      "schema:audienceType": "Technology Professionals",
      "schema:geographicArea": "Global"
    },
    "schema:wordCount": 15000,
    "schema:characterCount": 85000,
    "schema:numberOfItems": 25,
    "schema:isFamilyFriendly": true,
    "schema:dateLastReviewed": "2024-01-25T09:00:00Z",
    "schema:mainContentOfPage": "Our blog provides insights into the latest technology trends...",
    "schema:significantLinks": [
      "https://example.com/blog/archive",
      "https://example.com/blog/subscribe",
      "https://example.com/blog/contact"
    ]
  },
  "issuer": "did:web:publisher.example.com",
  "issuanceDate": "2024-01-20T14:00:00Z"
}
```

## Files

- `schema.json`: JSON Schema definition for the Blog schema
- `context.json`: JSON-LD context file defining the vocabulary terms

## License

This project is licensed under the MIT License. 