# CreativeWork Schema

This schema defines a verifiable credential for representing creative works using schema.org vocabulary.

## Overview

The CreativeWork credential allows for the representation of various types of creative content including articles, books, videos, music, software, and other intellectual works. It follows the schema.org CreativeWork type structure and is designed to be interoperable with existing schema.org implementations.

## Schema Structure

The credential includes the following key properties:

### Required Fields
- `id`: The unique identifier for the creative work (typically a URI)
- `schema:name`: The name or title of the creative work

### Basic Properties
- `schema:description`: Description of the creative work
- `schema:url`: URL where the creative work can be accessed
- `schema:alternateName`: An alias for the item
- `schema:identifier`: Any kind of identifier for the creative work
- `schema:sameAs`: URL of a reference Web page that unambiguously indicates the item's identity

### Content Properties
- `schema:abstract`: Abstract or summary of the creative work
- `schema:text`: The textual content of this CreativeWork
- `schema:headline`: Headline of the article
- `schema:alternativeHeadline`: A secondary title of the CreativeWork
- `schema:wordCount`: Number of words in the creative work
- `schema:characterCount`: Number of characters in the creative work
- `schema:pageCount`: Number of pages in the creative work
- `schema:duration`: Duration of the creative work (for time-based media)
- `schema:timeRequired`: Approximate time it usually takes to work with the content
- `schema:version`: The version of the CreativeWork

### Authorship and Contributors
- `schema:author`: The author of the creative work (URI or object)
- `schema:creator`: The creator of the creative work (URI or object)
- `schema:contributor`: A secondary contributor to the CreativeWork (URI or object)
- `schema:editor`: The person who edited the CreativeWork (URI or object)
- `schema:producer`: The person or organization who produced the work (URI or object)
- `schema:publisher`: The publisher of the creative work (URI or object)
- `schema:accountablePerson`: The person legally accountable for the CreativeWork (URI or object)

### Dates and Timeline
- `schema:dateCreated`: Date and time when the creative work was created
- `schema:datePublished`: Date and time when the creative work was published
- `schema:dateModified`: Date and time when the creative work was last modified
- `schema:expires`: Date the content expires and is no longer useful or available
- `schema:contentReferenceTime`: The specific time described by a creative work

### Classification and Metadata
- `schema:genre`: Genre of the creative work
- `schema:keywords`: Keywords or tags associated with the creative work
- `schema:creativeWorkStatus`: The status of a creative work in terms of its stage in a lifecycle
- `schema:inLanguage`: Language of the creative work (ISO 639-1 code)
- `schema:typicalAgeRange`: The typical expected age range, e.g. '7-9', '11-'

### Rights and Licensing
- `schema:license`: License under which the creative work is distributed
- `schema:copyrightHolder`: Copyright holder of the creative work (URI or object)
- `schema:copyrightYear`: Year of copyright
- `schema:copyrightNotice`: Text of a notice appropriate for describing the copyright aspects

### Accessibility Properties
- `schema:accessMode`: The human sensory perceptual system or cognitive faculty through which a person may process or perceive information
- `schema:accessModeSufficient`: A list of single or combined accessModes that are sufficient to understand all the intellectual content
- `schema:accessibilityAPI`: Indicates that the resource is compatible with the referenced accessibility API
- `schema:accessibilityControl`: Identifies input methods that are sufficient to fully control the described resource
- `schema:accessibilityFeature`: Content features of the resource, such as accessible media, alternatives and supported enhancements for accessibility
- `schema:accessibilityHazard`: A characteristic of the described resource that is physiologically dangerous to some users
- `schema:accessibilitySummary`: A human-readable summary of specific accessibility features or deficiencies

### Media and Encoding
- `schema:fileFormat`: File format of the creative work
- `schema:contentSize`: Size of the creative work content
- `schema:encodingFormat`: Encoding format of the creative work
- `schema:thumbnailUrl`: URL of a thumbnail image for the creative work
- `schema:image`: URL of an image representing the creative work
- `schema:thumbnail`: Thumbnail image for an image or video

### Location and Coverage
- `schema:contentLocation`: The location depicted or described in the content
- `schema:locationCreated`: The location where the CreativeWork was created
- `schema:spatial`: The "spatial" property can be used in cases when more specific properties are not known to be appropriate
- `schema:spatialCoverage`: The spatialCoverage of a CreativeWork indicates the place(s) which are the focus of the content
- `schema:countryOfOrigin`: The country of origin of something, including products as well as creative works
- `schema:temporal`: The "temporal" property can be used in cases where more specific properties are not known to be appropriate
- `schema:temporalCoverage`: The temporalCoverage of a CreativeWork indicates the period that the content applies to

### Relationships and Structure
- `schema:isPartOf`: URI of a larger creative work of which this is a part
- `schema:hasPart`: Array of URIs of creative works that are parts of this work
- `schema:mainEntity`: Indicates the primary entity described in some page or other CreativeWork
- `schema:mainEntityOfPage`: Indicates a page (or other CreativeWork) for which this thing is the main entity being described
- `schema:about`: The subject matter of the content
- `schema:subjectOf`: A CreativeWork or Event about this Thing

### Reviews and Ratings
- `schema:review`: A review of the item (array of URIs or objects)
- `schema:aggregateRating`: The overall rating, based on a collection of reviews or ratings, of the item
- `schema:contentRating`: Official rating of a piece of content
- `schema:commentCount`: The number of comments this CreativeWork has received

### Educational Properties
- `schema:educationalLevel`: The level in terms of progression through an educational or training context
- `schema:educationalUse`: The purpose of a work in the context of education
- `schema:learningResourceType`: The predominant type or kind characterizing the learning resource
- `schema:teaches`: The item being described is intended to help a person learn the competency or learning outcome
- `schema:assesses`: The item being described is intended to assess the competency or learning outcome

### Interaction and Engagement
- `schema:interactionStatistic`: Statistics about user interactions with the creative work
- `schema:interactionType`: The type of interaction being measured
- `schema:userInteractionCount`: The number of user interactions
- `schema:interactivityType`: The predominant mode of learning supported by the learning resource

### Family and Safety
- `schema:isAccessibleForFree`: Whether the creative work is accessible for free
- `schema:isFamilyFriendly`: Indicates whether this content is family friendly

### Additional Properties
- `schema:citation`: Citations or references used in the creative work
- `schema:pattern`: A pattern that something has, for example 'polka dot', 'striped'
- `schema:position`: The position of an item in a series or sequence of items
- `schema:creditText`: Text that can be used to credit person(s) and/or organization(s) associated with a published Creative Work
- `schema:usageInfo`: Information about the usage of the creative work

## Author/Creator Structure

The `schema:author`, `schema:creator`, `schema:contributor`, `schema:editor`, `schema:producer`, and `schema:publisher` properties can be either a URI string or an object:

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

## Aggregate Rating Structure

The `schema:aggregateRating` property can be either a URI or an object:

```json
{
  "schema:ratingValue": 4.5,
  "schema:reviewCount": 25
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
    "schema:abstract": "This work provides a comprehensive overview of verifiable credentials...",
    "schema:accessibilityFeature": ["alternativeText", "highContrast"],
    "schema:isFamilyFriendly": true,
    "schema:typicalAgeRange": "18+",
    "schema:educationalLevel": "Intermediate",
    "schema:aggregateRating": {
      "schema:ratingValue": 4.8,
      "schema:reviewCount": 42
    },
    "schema:interactionStatistic": [
      {
        "schema:interactionType": "https://schema.org/ViewAction",
        "schema:userInteractionCount": 1500
      }
    ]
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