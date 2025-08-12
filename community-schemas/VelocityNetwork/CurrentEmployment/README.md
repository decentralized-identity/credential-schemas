# Current Employment Schema

This document provides an overview of the `Current Employment` schema. The schema is defined in the `CurrentEmploymentSchema.json` file and follows the JSONSchema standard.

## Overview
The `Current Employment` schema defines the structure for a verifiable credential that represents a person's current employment position. It includes the following main components:

- **CredentialSubject**: The actual content of the credential containing employment information:
  - `@context`: JSON-LD context for the credential
  - `type`: The type of credential (default: "Employment")
  - `legalEmployer`: Organization information including name, identifier, and place
  - `role`: The specific role or position title
  - `description`: Detailed description of the position
  - `employmentType`: Array of employment types (full-time, part-time, contract, etc.)
  - `place`: Workplace location information
  - `recipient`: Person name information (given name, family name, etc.)
  - `startDate`: The date when the employment began
  - `alignment`: Optional alignment to public resources or standards

## Schema Details

- **File**: `CurrentEmploymentSchema.json`
- **Standard**: JSON-Schema Draft 2020-12 (https://json-schema.org/draft/2020-12)
- **Purpose**: To verify and validate current employment credentials as part of the Velocity Network Foundation's employment verification system.
- **Version**: Based on Velocity Network Foundation schemas v1.1

## Key Features

- **Comprehensive Organization Data**: Includes detailed organization information with DID identifiers
- **Flexible Employment Types**: Supports various employment classifications (full-time, part-time, contract, permanent, temporary, internship)
- **Location Support**: Detailed place information following ISO standards for regions and countries
- **Alignment Support**: Optional alignment to external frameworks and standards
- **Date Validation**: Proper date format validation for employment start dates

## Example Usage

The schema supports employment credentials for various scenarios:
- Full-time permanent positions
- Contract and temporary work
- Internships and trainee positions
- Part-time employment
- Remote and on-site work arrangements

## TAGS
- employment
- verification
- velocity-network
- current-position
- workplace-credentials

## License

This schema is provided by the Velocity Network Foundation for use in employment verification systems.
