# MediaObject Schema

This schema defines a verifiable credential for representing media objects using Schema.org vocabulary.

- Canonical reference: [Schema.org MediaObject](https://schema.org/MediaObject)

## Overview

The MediaObject credential models media objects such as images, videos, audio files, and text objects embedded in web pages or downloadable datasets. It extends CreativeWork and includes media-specific properties for content delivery, encoding, and playback.

## Schema Structure

### Required Fields
- `id`: Unique identifier for the media object (URI)
- `schema:name`: Title of the media object

### Media-Specific Fields
- `schema:contentUrl`: Actual bytes of the media object (file URL)
- `schema:embedUrl`: URL pointing to a player for the media
- `schema:encodingFormat`: Media type using MIME format (e.g., audio/mpeg, video/mp4)
- `schema:contentSize`: File size in bytes
- `schema:bitrate`: Bitrate of the media object
- `schema:duration`: Duration in ISO 8601 format
- `schema:uploadDate`: Date when media was uploaded
- `schema:startTime` / `schema:endTime`: Time offsets for clips
- `schema:height` / `schema:width`: Dimensions (for images/videos)
- `schema:caption`: Caption for the media object
- `schema:playerType`: Required player type (Flash, Silverlight, etc.)

### Access Control & Licensing
- `schema:requiresSubscription`: Whether subscription is required
- `schema:regionsAllowed`: Regions where media is allowed
- `schema:eligibleRegion`: Regions where media is eligible
- `schema:ineligibleRegion`: Regions where media is not eligible
- `schema:license`: License under which media is distributed
- `schema:copyrightHolder` / `schema:copyrightYear`: Copyright information
- `schema:copyrightNotice`: Copyright notice text
- `schema:contentRating`: Official content rating

### Content Relationships
- `schema:associatedArticle`: NewsArticle associated with the media
- `schema:encodesCreativeWork`: CreativeWork encoded by this media
- `schema:productionCompany`: Production company/studio
- `schema:musicBy`: Composer of soundtrack
- `schema:isPartOf`: Larger creative work this is part of
- `schema:mainEntity` / `schema:mainEntityOfPage`: Main entity described

### Authorship & Creation
- `schema:author` / `schema:creator`: Author or creator (URI or object)
- `schema:dateCreated` / `schema:datePublished` / `schema:dateModified`
- `schema:expires`: Date when content expires

### Content & Metadata
- `schema:description`: Description of the media object
- `schema:url`: URL of the media object
- `schema:abstract`: Abstract or summary
- `schema:text`: Textual content (for text objects)
- `schema:genre`: Genre of the media
- `schema:keywords`: Keywords or tags
- `schema:inLanguage`: Language of the content
- `schema:version`: Version of the media object

### Media Assets
- `schema:image` / `schema:thumbnail` / `schema:thumbnailUrl`: Images
- `schema:isAccessibleForFree`: Free access flag
- `schema:isFamilyFriendly`: Family-friendly content flag

### Interaction & Engagement
- `schema:interactionStatistic`: User interaction metrics
- `schema:commentCount`: Number of comments
- `schema:aggregateRating`: Overall rating from reviews
- `schema:review`: Reviews of the media object

### Accessibility & Usability
- `schema:accessMode`: Human sensory system for processing
- `schema:accessModeSufficient`: Sufficient access modes
- `schema:accessibilityAPI`: Compatible accessibility APIs
- `schema:accessibilityControl`: Sufficient input methods
- `schema:accessibilityFeature`: Content features for accessibility
- `schema:accessibilityHazard`: Physiologically dangerous characteristics
- `schema:accessibilitySummary`: Human-readable accessibility summary

### Publishing & Distribution
- `schema:publisher`: Publisher of the media
- `schema:usageInfo`: Information about usage
- `schema:timeRequired`: Time to work through content
- `schema:typicalAgeRange`: Expected age range

### Identifiers & References
- `schema:alternateName`: Alternative name/alias
- `schema:identifier`: Various identifiers (UUID, etc.)
- `schema:sameAs`: Reference to other pages with same identity
- `schema:potentialAction`: Potential actions involving this media
- `schema:subjectOf`: CreativeWork or Event about this media

## Media Object Types

The schema supports various media object types:
- **ImageObject**: Images and photographs
- **VideoObject**: Video files and streams
- **AudioObject**: Audio files and recordings
- **TextObject**: Text-based media
- **DataDownload**: Downloadable datasets

## Usage Examples

### Video Object
```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://w3id.org/security/suites/jws-2020/v1",
    { "schema": "https://schema.org/" }
  ],
  "type": ["VerifiableCredential", "schema:MediaObject"],
  "credentialSubject": {
    "id": "https://example.com/videos/intro-video",
    "schema:name": "Introduction Video",
    "schema:description": "Welcome video for new users",
    "schema:contentUrl": "https://example.com/videos/intro-video.mp4",
    "schema:embedUrl": "https://example.com/player/intro-video",
    "schema:encodingFormat": "video/mp4",
    "schema:contentSize": "15.2MB",
    "schema:duration": "PT2M30S",
    "schema:uploadDate": "2024-01-15T10:00:00Z",
    "schema:width": {
      "schema:value": 1920,
      "schema:unitCode": "PXL"
    },
    "schema:height": {
      "schema:value": 1080,
      "schema:unitCode": "PXL"
    },
    "schema:requiresSubscription": false,
    "schema:isFamilyFriendly": true
  }
}
```

### Audio Object
```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://w3id.org/security/suites/jws-2020/v1",
    { "schema": "https://schema.org/" }
  ],
  "type": ["VerifiableCredential", "schema:MediaObject"],
  "credentialSubject": {
    "id": "https://example.com/audio/podcast-episode-1",
    "schema:name": "Podcast Episode 1: Getting Started",
    "schema:description": "First episode of our educational podcast series",
    "schema:contentUrl": "https://example.com/audio/podcast-episode-1.mp3",
    "schema:encodingFormat": "audio/mpeg",
    "schema:contentSize": "25.8MB",
    "schema:duration": "PT45M12S",
    "schema:uploadDate": "2024-01-10T14:30:00Z",
    "schema:bitrate": "128kbps",
    "schema:author": {
      "id": "did:web:host.example.com",
      "schema:name": "Jane Smith"
    },
    "schema:license": "https://creativecommons.org/licenses/by/4.0/",
    "schema:isAccessibleForFree": true
  }
}
```

### Image Object
```json
{
  "@context": [
    "https://www.w3.org/2018/credentials/v1",
    "https://w3id.org/security/suites/jws-2020/v1",
    { "schema": "https://schema.org/" }
  ],
  "type": ["VerifiableCredential", "schema:MediaObject"],
  "credentialSubject": {
    "id": "https://example.com/images/company-logo",
    "schema:name": "Company Logo",
    "schema:description": "Official company logo in high resolution",
    "schema:contentUrl": "https://example.com/images/company-logo.png",
    "schema:encodingFormat": "image/png",
    "schema:contentSize": "2.1MB",
    "schema:width": {
      "schema:value": 800,
      "schema:unitCode": "PXL"
    },
    "schema:height": {
      "schema:value": 600,
      "schema:unitCode": "PXL"
    },
    "schema:uploadDate": "2024-01-01T09:00:00Z",
    "schema:copyrightHolder": {
      "id": "did:web:company.example.com",
      "schema:name": "Example Company"
    },
    "schema:copyrightYear": 2024,
    "schema:license": "https://creativecommons.org/licenses/by/4.0/"
  }
}
```

## Benefits

1. **Comprehensive Media Support**: Covers all major media types (video, audio, image, text)
2. **Rich Metadata**: Includes technical specifications, licensing, and accessibility info
3. **Access Control**: Supports regional restrictions and subscription requirements
4. **Content Relationships**: Links media to articles, creative works, and entities
5. **Accessibility Focus**: Extensive accessibility metadata for inclusive design
6. **Schema.org Compatible**: Full alignment with Schema.org MediaObject specification

## Files
- `schema.json`: JSON Schema for MediaObject
- `context.json`: JSON-LD context mapping terms

## License
MIT 