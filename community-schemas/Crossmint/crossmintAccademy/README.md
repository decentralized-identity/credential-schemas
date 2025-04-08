# Course Completion Certificate Schema

This document provides an overview of the `Course Completion Certificate` schema. The schema is defined in the `course-completion-certificate.schema.json` file and follows the JSONSchema standard.

## Overview
The `Course Completion Certificate` schema defines the structure for a verifiable credential that certifies the completion of a course in the Crossmint Academy internal employee program. It includes the following main components:

- **CredentialSubject**: The actual content of the credential:
  - `id`: A string representing the unique identifier of the subject.
  - `course`: A string representing the name of the completed course.
  - `grade`: A string representing the grade achieved in the course.

## Schema Details

- **File**: `course-completion-certificate.schema.json`
- **Standard**: JSON-Schema Draft 2020-12 (https://json-schema.org/draft/2020-12)
- **Purpose**: To verify and validate course completion credentials for Crossmint Academy's internal employee program.

## TAGS
- education
- internal training
- employee development

## License

This project is licensed under the MIT License.

