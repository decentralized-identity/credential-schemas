# WebPage Schema

This schema defines a verifiable credential for representing web pages using schema.org vocabulary.

## Overview

The WebPage credential allows for the representation of individual web page information including content, metadata, accessibility features, and performance statistics. It extends the CreativeWork credential with webpage-specific properties and follows the schema.org WebPage type structure.

## Schema Structure

The credential includes the following key properties:

### Required Fields
- `id`: The unique identifier for the web page (typically a URI)
- `schema:name`: The name or title of the web page

### Optional Fields (inherited from CreativeWork)
- `schema:description`: Description of the web page
- `schema:url`: URL of the web page
- `schema:author`: The author of the web page (URI or object)
- `schema:creator`: The creator of the web page (URI or object)
- `schema:dateCreated`: Date and time when the web page was created
- `schema:datePublished`: Date and time when the web page was published
- `schema:dateModified`: Date and time when the web page was last modified
- `schema:genre`: Genre of the web page
- `schema:keywords`: Keywords or tags associated with the web page
- `schema:license`: License under which the web page is distributed
- `schema:copyrightHolder`: Copyright holder of the web page
- `schema:copyrightYear`: Year of copyright
- `schema:inLanguage`: Language of the web page (ISO 639-1 code)
- `schema:isAccessibleForFree`: Whether the web page is accessible for free
- `schema:thumbnailUrl`: URL of a thumbnail image for the web page
- `schema:image`: URL of an image representing the web page
- `schema:abstract`: Abstract or summary of the web page
- `schema:interactionStatistic`: Statistics about user interactions with the web page

### WebPage-Specific Fields
- `schema:isPartOf`: URI of the website of which this page is a part
- `schema:mainEntity`: The main entity described on the web page
- `schema:about`: The subject matter of the web page
- `schema:breadcrumb`: A breadcrumb trail for the web page
- `schema:lastReviewed`: Date and time when the web page was last reviewed
- `schema:reviewedBy`: The reviewer of the web page
- `schema:significantLink`: Significant links on the web page
- `schema:specialty`: The specialty of the web page
- `schema:primaryImageOfPage`: The primary image of the web page
- `schema:relatedLink`: Related links on the web page
- `schema:speakable`: Information about speakable content on the page
- `schema:wordCount`: Number of words in the web page
- `schema:characterCount`: Number of characters in the web page
- `schema:pageStart`: The page on which the work starts
- `schema:pageEnd`: The page on which the work ends
- `schema:pagination`: Any description of pages that is not separated into pageStart and pageEnd
- `schema:isFamilyFriendly`: Whether the web page is family friendly
- `schema:dateLastReviewed`: Date and time when the web page was last reviewed
- `schema:mainContentOfPage`: The main content of the web page
- `schema:significantLinks`: The most significant URLs on the page

## Speakable Content Structure

The `schema:speakable` property uses a nested structure for accessibility:

```json
{
  "schema:cssSelector": ".speakable-content",
  "schema:xpath": "//div[@class='speakable']"
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
    "schema:WebPage"
  ],
  "credentialSubject": {
    "id": "https://example.com/about",
    "schema:name": "About Us",
    "schema:description": "Learn more about our company and mission",
    "schema:url": "https://example.com/about",
    "schema:author": {
      "id": "did:web:author.example.com",
      "schema:name": "Jane Smith"
    },
    "schema:dateCreated": "2024-01-15T10:30:00Z",
    "schema:datePublished": "2024-01-20T14:00:00Z",
    "schema:genre": "Informational",
    "schema:keywords": ["about", "company", "mission", "team"],
    "schema:license": "https://creativecommons.org/licenses/by/4.0/",
    "schema:inLanguage": "en",
    "schema:isAccessibleForFree": true,
    "schema:isPartOf": "https://example.com",
    "schema:mainEntity": "https://example.com/entity/company",
    "schema:about": "https://example.com/topic/company-information",
    "schema:breadcrumb": "Home > About",
    "schema:lastReviewed": "2024-01-25T09:00:00Z",
    "schema:reviewedBy": {
      "id": "did:web:reviewer.example.com",
      "schema:name": "John Doe"
    },
    "schema:significantLink": [
      "https://example.com/contact",
      "https://example.com/careers"
    ],
    "schema:specialty": "Company Information",
    "schema:primaryImageOfPage": "https://example.com/images/about-hero.jpg",
    "schema:relatedLink": [
      "https://example.com/team",
      "https://example.com/history"
    ],
    "schema:speakable": {
      "schema:cssSelector": ".main-content",
      "schema:xpath": "//div[@class='main-content']"
    },
    "schema:wordCount": 1500,
    "schema:characterCount": 8500,
    "schema:isFamilyFriendly": true,
    "schema:dateLastReviewed": "2024-01-25T09:00:00Z",
    "schema:mainContentOfPage": "Our company was founded in 2020 with a mission to...",
    "schema:significantLinks": [
      "https://example.com/contact",
      "https://example.com/careers",
      "https://example.com/press"
    ]
  },
  "issuer": "did:web:publisher.example.com",
  "issuanceDate": "2024-01-20T14:00:00Z"
}
```

## Files

- `schema.json`: JSON Schema definition for the WebPage schema
- `context.json`: JSON-LD context file defining the vocabulary terms

## License

This project is licensed under the MIT License. 