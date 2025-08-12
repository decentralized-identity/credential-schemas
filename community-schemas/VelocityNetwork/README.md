# Velocity Network Foundation Schemas

This document provides an overview of the schemas submitted by the Velocity Network Foundation. The schemas follow the JSONSchema standard and are designed for employment and career-related verifiable credentials.

## Overview
The Velocity Network Foundation schemas define structures for verifiable credentials related to employment, career history, and professional qualifications. These schemas are part of the Velocity Network ecosystem for secure and verifiable career credentials.

## Available Schemas

### Current Employment
- **File**: `CurrentEmployment/CurrentEmploymentSchema.json`
- **Purpose**: Represents a person's current employment position
- **Key Components**:
  - Legal employer information with DID identifiers
  - Role and position details
  - Employment type classifications
  - Workplace location information
  - Employment start date
  - Recipient (employee) details

### Past Employment
- **File**: `PastEmployment/PastEmploymentSchema.json`
- **Purpose**: Represents historical employment records
- **Key Components**:
  - Legal employer information with DID identifiers
  - Role and position details
  - Employment type classifications
  - Workplace location information
  - Employment start date and end date
  - Recipient (employee) details
  - Complete employment history tracking

## Schema Details

- **Standard**: JSON-Schema Draft 2020-12 (https://json-schema.org/draft/2020-12)
- **Context**: Uses Velocity Network Foundation's JSON-LD context
- **Version**: Based on v1.1 of the Velocity Network schemas
- **Organization**: Velocity Network Foundation

## Key Features

- **DID-based Identifiers**: Uses decentralized identifiers for organizations
- **ISO Standard Compliance**: Location data follows ISO 3166 standards
- **Flexible Employment Types**: Supports various employment classifications
- **Alignment Support**: Optional alignment to external frameworks and standards
- **Comprehensive Person Data**: Detailed name structures with prefixes and suffixes
- **Date Validation**: Proper date format validation for employment periods
- **Employment History**: Complete tracking of both current and past employment

## Differences Between Schemas

- **Current Employment**: Includes only `startDate` for ongoing employment
- **Past Employment**: Includes both `startDate` and `endDate` for completed employment records

## TAGS

- `employment`
- `career-credentials`
- `velocity-network`
- `professional-verification`
- `workforce-identity`
- `employment-history`

## License

These schemas are provided by the Velocity Network Foundation for use in employment verification and career credential systems.

