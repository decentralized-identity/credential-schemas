# Article Schema

This schema defines a verifiable credential for representing articles using schema.org vocabulary.

## Overview

The Article credential allows for the representation of various types of articles including news articles, scholarly articles, technical articles, reports, and other written content. It extends the CreativeWork credential with article-specific properties and follows the schema.org Article type structure.

## Schema Structure

The credential includes the following key properties:

### Required Fields
- `id`: The unique identifier for the article (typically a URI)
- `schema:name`: The name or title of the article

### Article-Specific Fields
- `schema:articleBody`: The actual body of the article
- `schema:articleSection`: Articles may belong to one or more 'sections' in a magazine or newspaper, such as Sports, Lifestyle, etc.
- `schema:backstory`: For an Article, typically a NewsArticle, the backstory property provides a textual summary giving a brief explanation of why and how an article was created
- `schema:pageEnd`: The page on which the work ends; for example '138' or 'xvi'
- `schema:pageStart`: The page on which the work starts; for example '135' or 'xiii'
- `schema:pagination`: Any description of pages that is not separated into pageStart and pageEnd
- `schema:sharedContent`: A CreativeWork such as an image, video, or audio clip shared as part of this posting
- `schema:speakable`: Indicates sections of a Web page that are particularly 'speakable' in the sense of being highlighted as being especially appropriate for text-to-speech conversion

### Inherited Fields from CreativeWork
- `schema:description`: Description of the article
- `schema:url`: URL where the article can be accessed
- `schema:author`: The author of the article (URI or object)
- `schema:creator`: The creator of the article (URI or object)
- `schema:dateCreated`: Date and time when the article was created
- `schema:datePublished`: Date and time when the article was published
- `schema:dateModified`: Date and time when the article was last modified
- `schema:genre`: Genre of the article
- `schema:keywords`: Keywords or tags associated with the article
- `schema:license`: License under which the article is distributed
- `schema:copyrightHolder`: Copyright holder of the article (URI or object)
- `schema:copyrightYear`: Year of copyright
- `schema:inLanguage`: Language of the article (ISO 639-1 code)
- `schema:isAccessibleForFree`: Whether the article is accessible for free
- `schema:thumbnailUrl`: URL of a thumbnail image for the article
- `schema:image`: URL of an image representing the article
- `schema:isPartOf`: URI of a larger creative work of which this article is a part
- `schema:hasPart`: Array of URIs of creative works that are parts of this article
- `schema:citation`: Citations or references used in the article
- `schema:abstract`: Abstract or summary of the article
- `schema:wordCount`: Number of words in the article
- `schema:characterCount`: Number of characters in the article
- `schema:pageCount`: Number of pages in the article
- `schema:duration`: Duration of the article (for time-based media)
- `schema:interactionStatistic`: Statistics about user interactions with the article

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
- `schema:accountablePerson`: Specifies the Person that is legally accountable for the Article
- `schema:aggregateRating`: The overall rating, based on a collection of reviews or ratings, of the item
- `schema:alternativeHeadline`: A secondary title of the Article
- `schema:commentCount`: The number of comments this Article has received
- `schema:contentLocation`: The location depicted or described in the content
- `schema:contentRating`: Official rating of a piece of content
- `schema:contributor`: A secondary contributor to the Article
- `schema:copyrightNotice`: Text of a notice appropriate for describing the copyright aspects
- `schema:countryOfOrigin`: The country of origin of something, including products as well as creative works
- `schema:creativeWorkStatus`: The status of a creative work in terms of its stage in a lifecycle
- `schema:editor`: Specifies the Person who edited the Article
- `schema:expires`: Date the content expires and is no longer useful or available
- `schema:headline`: Headline of the article
- `schema:isFamilyFriendly`: Indicates whether this content is family friendly
- `schema:locationCreated`: The location where the Article was created
- `schema:mainEntity`: Indicates the primary entity described in some page or other CreativeWork
- `schema:producer`: The person or organization who produced the work
- `schema:publisher`: The publisher of the article
- `schema:review`: A review of the item
- `schema:text`: The textual content of this Article
- `schema:timeRequired`: Approximate time it usually takes to work with the content
- `schema:typicalAgeRange`: The typical expected age range, e.g. '7-9', '11-'
- `schema:version`: The version of the Article
- `schema:alternateName`: An alias for the item
- `schema:identifier`: Any kind of identifier for the article
- `schema:mainEntityOfPage`: Indicates a page (or other CreativeWork) for which this thing is the main entity being described
- `schema:sameAs`: URL of a reference Web page that unambiguously indicates the item's identity
- `schema:subjectOf`: A CreativeWork or Event about this Thing

## Article Types

The schema supports various article types:
- **NewsArticle**: News and current events articles
- **ScholarlyArticle**: Academic and research articles
- **TechArticle**: Technical documentation and articles
- **Report**: Investigative and analytical reports
- **SatiricalArticle**: Satirical and humorous articles
- **SocialMediaPosting**: Social media content
- **BlogPosting**: Blog posts and online articles

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
    "schema:Article"
  ],
  "credentialSubject": {
    "id": "https://example.com/articles/verifiable-credentials-guide",
    "schema:name": "A Comprehensive Guide to Verifiable Credentials",
    "schema:description": "An in-depth exploration of verifiable credentials and their applications in digital identity",
    "schema:url": "https://example.com/articles/verifiable-credentials-guide",
    "schema:author": {
      "id": "did:web:author.example.com",
      "schema:name": "Dr. Jane Smith"
    },
    "schema:dateCreated": "2024-01-15T10:30:00Z",
    "schema:datePublished": "2024-01-20T14:00:00Z",
    "schema:articleSection": "Technology",
    "schema:articleBody": "Verifiable credentials represent a fundamental shift in how we think about digital identity...",
    "schema:genre": "Educational",
    "schema:keywords": ["verifiable credentials", "digital identity", "blockchain", "privacy"],
    "schema:license": "https://creativecommons.org/licenses/by/4.0/",
    "schema:copyrightHolder": {
      "id": "did:web:publisher.example.com",
      "schema:name": "Tech Publications Inc."
    },
    "schema:copyrightYear": 2024,
    "schema:inLanguage": "en",
    "schema:isAccessibleForFree": true,
    "schema:wordCount": 3500,
    "schema:characterCount": 21000,
    "schema:pageStart": 1,
    "schema:pageEnd": 8,
    "schema:abstract": "This article provides a comprehensive overview of verifiable credentials...",
    "schema:headline": "A Comprehensive Guide to Verifiable Credentials",
    "schema:accessibilityFeature": ["alternativeText", "highContrast", "screenReaderOptimized"],
    "schema:isFamilyFriendly": true,
    "schema:typicalAgeRange": "18+",
    "schema:aggregateRating": {
      "schema:ratingValue": 4.8,
      "schema:reviewCount": 42
    },
    "schema:interactionStatistic": [
      {
        "schema:interactionType": "https://schema.org/ViewAction",
        "schema:userInteractionCount": 2500
      },
      {
        "schema:interactionType": "https://schema.org/LikeAction",
        "schema:userInteractionCount": 180
      }
    ],
    "schema:backstory": "This article was written based on extensive research and interviews with industry experts in the field of digital identity and verifiable credentials."
  },
  "issuer": "did:web:publisher.example.com",
  "issuanceDate": "2024-01-20T14:00:00Z"
}
```

## Files

- `schema.json`: JSON Schema definition for the Article schema
- `context.json`: JSON-LD context file defining the vocabulary terms

## License

This project is licensed under the MIT License. 