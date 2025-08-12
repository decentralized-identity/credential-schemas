# Past Employment Schema

This document provides an overview of the `Past Employment` schema. The schema is defined in the `PastEmploymentSchema.json` file and follows the JSONSchema standard.

## Overview
The `Past Employment` schema defines the structure for a verifiable credential that represents a person's past employment position. It includes the following main components:

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
  - `endDate`: The date when the employment ended
  - `alignment`: Optional alignment to public resources or standards

## Schema Details

- **File**: `PastEmploymentSchema.json`
- **Standard**: JSON-Schema Draft 2020-12 (https://json-schema.org/draft/2020-12)
- **Purpose**: To verify and validate past employment credentials as part of the Velocity Network Foundation's employment verification system.
- **Version**: Based on Velocity Network Foundation schemas v1.1

## Key Features

- **Complete Employment History**: Includes both start and end dates for employment periods
- **Comprehensive Organization Data**: Includes detailed organization information with DID identifiers
- **Flexible Employment Types**: Supports various employment classifications (full-time, part-time, contract, permanent, temporary, internship)
- **Location Support**: Detailed place information following ISO standards for regions and countries
- **Alignment Support**: Optional alignment to external frameworks and standards
- **Date Validation**: Proper date format validation for both employment start and end dates

## Difference from Current Employment

The key difference between this schema and the Current Employment schema is:
- **Required End Date**: Past employment records must include an `endDate` field indicating when the employment ended
- **Historical Context**: Designed for completed employment relationships rather than ongoing positions

## Example Usage

The schema supports past employment credentials for various scenarios:
- Previous full-time positions
- Completed contracts and temporary work
- Finished internships and trainee positions
- Former part-time employment
- Career history documentation

## TAGS
- employment
- employment-history
- past-employment
- velocity-network
- career-credentials
- workplace-verification

## License

This schema is provided by the Velocity Network Foundation for use in employment verification systems.
