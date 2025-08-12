# BlogPosting Schema

This schema defines a verifiable credential for representing individual blog posts using Schema.org vocabulary.

- Canonical reference: [Schema.org BlogPosting](https://schema.org/BlogPosting)

## Overview

The BlogPosting credential models a single post within a blog. It builds on Article/CreativeWork and adds blog-post–specific properties like `schema:headline` and `schema:articleBody`.

## Schema Structure

### Required Fields
- `id`: Unique identifier for the blog post (URI)
- `schema:name`: Title of the blog post

### Common Fields
- `schema:headline`: Headline for the post
- `schema:description`: Summary of the post
- `schema:url`: Canonical URL of the post
- `schema:author` / `schema:creator`: Author or creator (URI or object)
- `schema:dateCreated` / `schema:datePublished` / `schema:dateModified`
- `schema:genre`, `schema:keywords`
- `schema:license`
- `schema:inLanguage`, `schema:isAccessibleForFree`
- `schema:thumbnailUrl`, `schema:image`

### Article-Specific Fields
- `schema:articleBody`: The body content of the post
- `schema:articleSection`: Section/category the post belongs to
- `schema:pageStart`, `schema:pageEnd`, `schema:pagination`
- `schema:wordCount`, `schema:characterCount`

### Linking/Context Fields
- `schema:isPartOf`: The Blog or Website this post belongs to
- `schema:mainEntityOfPage`: Page where this post is the main entity
- `schema:mainEntity`, `schema:about`
- `schema:sharedContent`: Linked media shared as part of the post
- `schema:commentCount`: Number of comments
- `schema:interactionStatistic`: Interaction metrics

## Usage Example

```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://w3id.org/security/suites/jws-2020/v1",
    { "schema": "https://schema.org/" }
  ],
  "type": [
    "VerifiableCredential",
    "schema:BlogPosting"
  ],
  "credentialSubject": {
    "id": "https://example.com/blog/my-first-post",
    "schema:name": "My First Post",
    "schema:headline": "My First Post",
    "schema:description": "Kicking off the blog with a short introduction.",
    "schema:url": "https://example.com/blog/my-first-post",
    "schema:author": {
      "id": "did:web:author.example.com",
      "schema:name": "Jane Smith"
    },
    "schema:datePublished": "2024-02-01T12:00:00Z",
    "schema:articleSection": "Announcements",
    "schema:articleBody": "Welcome to the blog...",
    "schema:isPartOf": "https://example.com/blog",
    "schema:mainEntityOfPage": "https://example.com/blog/my-first-post",
    "schema:keywords": ["intro", "announcements"],
    "schema:wordCount": 420,
    "schema:commentCount": 3,
    "schema:image": "https://example.com/assets/cover.png"
  },
  "issuer": "did:web:publisher.example.com",
  "issuanceDate": "2024-02-01T12:00:00Z"
}
```

## Files
- `schema.json`: JSON Schema for BlogPosting
- `context.json`: JSON-LD context mapping terms

## License
MIT 