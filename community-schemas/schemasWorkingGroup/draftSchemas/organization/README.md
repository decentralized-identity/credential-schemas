# Organization Schema

This schema defines a verifiable credential for representing organizational information using schema.org vocabulary.

## Overview

The Organization credential allows for the representation of organizational data including legal name, contact information, address, tax identifiers, and other relevant organizational details. It follows the schema.org Organization type structure and is designed to be interoperable with existing schema.org implementations.

## Schema Structure

The credential includes the following key properties:

### Required Fields
- `id`: The unique identifier for the organization (typically a DID or URI)
- `schema:legalName`: The legal name of the organization

### Optional Fields
- `schema:telephone`: Organization's telephone number
- `schema:email`: Organization's email address
- `schema:vatID`: VAT identification number
- `schema:taxID`: Tax identification number
- `schema:location`: Postal address information
- `schema:url`: Organization's website URL
- `schema:description`: Description of the organization
- `schema:foundingDate`: Organization's founding date
- `schema:numberOfEmployees`: Number of employees
- `schema:industry`: Industry sector
- `schema:leiCode`: Legal Entity Identifier (LEI) code
- `schema:duns`: D-U-N-S number

## Address Structure

The `schema:location` property uses a nested structure for postal addresses:

```json
{
  "type": "schema:PostalAddress",
  "schema:streetAddress": "Am Wall 174",
  "schema:addressLocality": "Bremen",
  "schema:addressRegion": "Bremen",
  "schema:postalCode": "28195",
  "schema:addressCountry": "DE"
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
    "schema:Organization"
  ],
  "credentialSubject": {
    "id": "did:web:identinet.io",
    "schema:telephone": "+49 1522 9772744",
    "schema:vatID": "DE360224533",
    "schema:legalName": "identinet GmbH",
    "schema:email": "support@identinet.io",
    "schema:taxID": "60 118 18003",
    "schema:location": {
      "schema:addressCountry": "DE",
      "schema:addressLocality": "Bremen",
      "schema:addressRegion": "Bremen",
      "schema:postalCode": "28195",
      "schema:streetAddress": "Am Wall 174",
      "type": "schema:PostalAddress"
    }
  },
  "issuer": "did:web:identinet.io",
  "issuanceDate": "2025-05-16T16:22:51Z"
}
```

## Files

- `schema.json`: JSON Schema definition for the Organization schema
- `context.json`: JSON-LD context file defining the vocabulary terms

## License

This project is licensed under the MIT License. 