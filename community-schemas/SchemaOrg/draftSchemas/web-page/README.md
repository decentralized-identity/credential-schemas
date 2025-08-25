# WebPage Schema

This schema defines a comprehensive verifiable credential for representing web pages using Schema.org vocabulary. It supports all page types through a single unified schema.

- Canonical reference: [Schema.org WebPage](https://schema.org/WebPage)

## Overview

The WebPage credential models any type of web page with comprehensive metadata, accessibility features, and content metrics. It uses `schema:pageType` to distinguish between different page types while maintaining a unified structure.

## Supported Page Types

The schema supports all major Schema.org page types:

- **WebPage** - Generic web page (default)
- **AboutPage** - About/company information pages
- **CheckoutPage** - E-commerce checkout pages
- **CollectionPage** - Pages displaying collections of items
- **ContactPage** - Contact information pages
- **FAQPage** - Frequently asked questions pages
- **ItemPage** - Individual item/product pages
- **ProfilePage** - User profile pages
- **QAPage** - Question and answer pages
- **SearchResultsPage** - Search results pages

## Schema Structure

### Required Fields
- `id`: Unique identifier for the web page (URI)
- `schema:name`: Title of the web page

### Page Type Field
- `schema:pageType`: Specific type of web page (enum of supported types)

### Basic Fields
- `schema:description`: Summary of the web page
- `schema:url`: URL of the web page
- `schema:alternateName`: Alternative name/alias for the page
- `schema:identifier`: Various identifiers (ISBN, UUID, etc.)
- `schema:sameAs`: Reference to other pages with same identity

### Authorship & Creation
- `schema:author` / `schema:creator`: Author or creator (URI or object)
- `schema:editor`: Person who edited the work
- `schema:accountablePerson`: Person legally accountable for the work
- `schema:contributor`: Secondary contributors
- `schema:dateCreated` / `schema:datePublished` / `schema:dateModified`
- `schema:expires`: Date when content expires

### Content & Media
- `schema:abstract`: Abstract or summary
- `schema:text`: The textual content
- `schema:headline`: Headline of the article
- `schema:alternativeHeadline`: Secondary title
- `schema:image` / `schema:thumbnail` / `schema:thumbnailUrl`: Images
- `schema:primaryImageOfPage`: Main image on the page
- `schema:video`: Embedded video objects
- `schema:audio`: Embedded audio objects
- `schema:associatedMedia`: Media that encodes this work

### Classification & Metadata
- `schema:genre`: Genre of the web page
- `schema:keywords`: Keywords or tags
- `schema:license`: License under which content is distributed
- `schema:copyrightHolder` / `schema:copyrightYear`: Copyright information
- `schema:copyrightNotice`: Copyright notice text
- `schema:version`: Version of the creative work
- `schema:creativeWorkStatus`: Status (Draft, Published, etc.)

### Accessibility & Usability
- `schema:accessMode`: Human sensory system for processing information
- `schema:accessModeSufficient`: Sufficient access modes for understanding
- `schema:accessibilityAPI`: Compatible accessibility APIs
- `schema:accessibilityControl`: Sufficient input methods
- `schema:accessibilityFeature`: Content features for accessibility
- `schema:accessibilityHazard`: Physiologically dangerous characteristics
- `schema:accessibilitySummary`: Human-readable accessibility summary
- `schema:speakable`: Sections suitable for text-to-speech
  - `schema:cssSelector`: CSS selector for speakable content
  - `schema:xpath`: XPath for speakable content
- `schema:isFamilyFriendly`: Family-friendly content flag
- `schema:isAccessibleForFree`: Free access flag

### WebPage-Specific Fields
- `schema:isPartOf`: The Website this page belongs to
- `schema:mainEntity` / `schema:mainEntityOfPage`: Main entity described
- `schema:about`: Subject matter of the page
- `schema:breadcrumb`: Breadcrumb trail for navigation
- `schema:lastReviewed` / `schema:reviewedBy`: Review information
- `schema:significantLink` / `schema:relatedLink`: Important links
- `schema:mainContentOfPage`: Main content text
- `schema:specialty`: Domain specialty of the page

### Content Metrics & Statistics
- `schema:wordCount`, `schema:characterCount`
- `schema:pageStart`, `schema:pageEnd`, `schema:pagination`
- `schema:interactionStatistic`: User interaction metrics
- `schema:commentCount`: Number of comments
- `schema:aggregateRating`: Overall rating from reviews

### Educational & Learning
- `schema:educationalAlignment`: Alignment to educational frameworks
- `schema:educationalLevel`: Level in educational progression
- `schema:educationalUse`: Purpose in educational context
- `schema:learningResourceType`: Type of learning resource
- `schema:teaches`: Competencies this work helps learn
- `schema:assesses`: Competencies this work assesses
- `schema:interactivityType`: Predominant learning mode

### Publishing & Distribution
- `schema:publisher`: Publisher of the content
- `schema:publisherImprint`: Publishing division
- `schema:publishingPrinciples`: Editorial principles
- `schema:publication`: Publication event
- `schema:releasedEvent`: Release event
- `schema:acquireLicensePage`: Page for license acquisition
- `schema:usageInfo`: Information about usage

### Rights & Licensing
- `schema:license`: License document
- `schema:conditionsOfAccess`: Access conditions
- `schema:copyrightHolder`: Copyright holder
- `schema:copyrightYear`: Copyright year
- `schema:copyrightNotice`: Copyright notice

### Reviews & Ratings
- `schema:review`: Reviews of the item
- `schema:aggregateRating`: Overall rating
- `schema:contentRating`: Official content rating

### Location & Coverage
- `schema:contentLocation`: Location depicted in content
- `schema:locationCreated`: Location where work was created
- `schema:spatial`: Spatial characteristics
- `schema:spatialCoverage`: Geographic coverage
- `schema:temporal`: Temporal characteristics
- `schema:temporalCoverage`: Time period coverage
- `schema:contentReferenceTime`: Specific time described

### Relationships & References
- `schema:isBasedOn`: Work this is derived from
- `schema:exampleOfWork`: Work this is an example of
- `schema:workExample`: Examples of this work
- `schema:translationOfWork`: Work this is translated from
- `schema:workTranslation`: Translations of this work
- `schema:citation`: Citations and references
- `schema:mentions`: Referenced concepts

### Organizational & Legal
- `schema:sourceOrganization`: Organization creator worked for
- `schema:maintainer`: Person/organization maintaining the work
- `schema:provider`: Service provider
- `schema:producer`: Person/organization who produced the work
- `schema:funder`: Person/organization providing funding
- `schema:funding`: Grant providing funding
- `schema:sponsor`: Person/organization supporting the work
- `schema:countryOfOrigin`: Country of origin

### Technical & Format
- `schema:encoding`: Media object encoding this work
- `schema:encodingFormat`: Media type/MIME format
- `schema:digitalSourceType`: IPTC digital source type
- `schema:editEIDR`: Entertainment Identifier Registry
- `schema:schemaVersion`: Version of schema used
- `schema:sdDatePublished`: Date structured data was published
- `schema:sdLicense`: License for structured data
- `schema:sdPublisher`: Publisher of structured data

### Content Features
- `schema:material`: Material the work is made from
- `schema:materialExtent`: Quantity of materials
- `schema:pattern`: Pattern the work has
- `schema:size`: Standardized size
- `schema:typicalAgeRange`: Expected age range
- `schema:timeRequired`: Time to work through content

### Actions & Events
- `schema:potentialAction`: Potential actions involving this thing
- `schema:recordedAt`: Event where work was recorded
- `schema:discussionUrl`: Link to discussion page

## Usage Examples

### Generic WebPage with Full Properties
```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://w3id.org/security/suites/jws-2020/v1",
    { "schema": "https://schema.org/" }
  ],
  "type": ["VerifiableCredential", "schema:WebPage"],
  "credentialSubject": {
    "id": "https://example.com/page",
    "schema:name": "Comprehensive Example Page",
    "schema:pageType": "WebPage",
    "schema:description": "A comprehensive example with many properties",
    "schema:url": "https://example.com/page",
    "schema:author": {
      "id": "did:web:author.example.com",
      "schema:name": "Jane Smith"
    },
    "schema:datePublished": "2024-01-15T10:00:00Z",
    "schema:accessibilitySummary": "Screen reader compatible with proper heading structure",
    "schema:isFamilyFriendly": true,
    "schema:wordCount": 2500,
    "schema:commentCount": 15
  }
}
```

### ContactPage with Accessibility
```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://w3id.org/security/suites/jws-2020/v1",
    { "schema": "https://schema.org/" }
  ],
  "type": ["VerifiableCredential", "schema:WebPage"],
  "credentialSubject": {
    "id": "https://example.com/contact",
    "schema:name": "Contact Us",
    "schema:pageType": "ContactPage",
    "schema:description": "Get in touch with our team",
    "schema:url": "https://example.com/contact",
    "schema:breadcrumb": "Home > Contact",
    "schema:speakable": {
      "schema:cssSelector": ".contact-form, .contact-info"
    },
    "schema:accessibilityFeature": ["readingOrder", "structuralNavigation"],
    "schema:accessibilityAPI": "ARIA"
  }
}
```

### FAQPage with Educational Properties
```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://w3id.org/security/suites/jws-2020/v1",
    { "schema": "https://schema.org/" }
  ],
  "type": ["VerifiableCredential", "schema:WebPage"],
  "credentialSubject": {
    "id": "https://example.com/faq",
    "schema:name": "Frequently Asked Questions",
    "schema:pageType": "FAQPage",
    "schema:description": "Common questions and answers",
    "schema:url": "https://example.com/faq",
    "schema:keywords": ["faq", "help", "support", "questions"],
    "schema:educationalLevel": "beginner",
    "schema:learningResourceType": "reference",
    "schema:interactivityType": "expositive"
  }
}
```

## Benefits of Unified Approach

1. **Single Schema**: One comprehensive schema instead of 10+ separate schemas
2. **Consistent Structure**: All page types follow the same validation rules
3. **Easy Maintenance**: Changes only need to be made in one place
4. **Flexible Usage**: Can use for any page type with simple `pageType` field
5. **Better Interoperability**: Consistent structure across all page types
6. **Reduced Complexity**: Developers only need to learn one schema
7. **Comprehensive Coverage**: Includes all Schema.org WebPage and CreativeWork properties

## Files
- `schema.json`: JSON Schema for WebPage (supports all page types)
- `context.json`: JSON-LD context mapping terms

## License
MIT 