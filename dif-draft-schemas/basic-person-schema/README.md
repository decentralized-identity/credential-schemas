# Basic Person Schema

This document provides an overview of the `BasicPersonSchema`. The schema is defined in the `BasicPerson.schema.json` file and follows the JSON Schema standard.

## Overview
The `BasicPersonSchema` defines the structure for a verifiable credential used for KYC purposes. It includes the following main components:

- **CredentialSubject**: The actual content of the credential:
  - `id`: A string representing the unique identifier of the subject.
  - `issuanceDate`: A string representing the issuance date of the credential.
  - `expirationDate`: A string representing the expiration date of the credential.
  - `names`: An array of name objects representing the names of the credential subject.
  - `dateOfBirth`: A string representing the date of birth of the credential subject.
  - `addresses`: An array of address objects associated with the credential subject.
  - `sex`: A string representing the biological sex of the individual at birth.
  - `gender`: A string representing the gender the credential subject identifies as.
  - `nationalities`: An array of strings representing the subject's nationalities.
  - `identifiers`: An array of identifier objects for the credential subject.
  - `contactChannels`: An array of contact channel objects for the credential subject.
  - `customFields`: A free-form array to capture additional fields not covered by the main schema.

## Specification Status
- **Status**: Working Group Draft (October 2024)
- **Latest Draft**: [identity.foundation/credential-schemas/#basic-person-schema](https://identity.foundation/credential-schemas/#basic-person-schema)
- **Ratified Versions**: None


## TAGS

- `KYC`
- `AML`
- `Identity`
- `Person`
- `ID`

## License
Except where otherwise noted, this work by the Decentralized Identity Foundation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

## Abstract
This specification defines multiple standards for common use case verifiable credentials including KYC (basic person), AML, among others.

## Status of This Document
This is a draft specification being developed within the Decentralized Identity Foundation (DIF). Design work is ongoing, and participants are encouraged to open issues or otherwise contribute at the DIF-hosted GitHub repository, whether as input to stable versions or as recommendations for future versions.

## Terminology
- **Decentralized Identifiers**: Unique ID URI string and PKI metadata document format for describing the cryptographic keys and other fundamental PKI values linked to a unique, user-controlled, self-sovereign identifier in a target system (i.e., blockchain, distributed ledger).
- **Claim**: An assertion made about a Subject. Used as an umbrella term for Credential, Assertion, Attestation, etc.

## Schema Details
- **File**: `BasicPerson.schema.json`
- **Standard**: JSON-Schema Draft 2020-12 (https://json-schema.org/draft/2020-12)
- **Purpose**: To define the fields required to identify an individual at a basic level for KYC purposes.
- **Use cases**: Mainly for financial services, but also applicable in telecommunications and any sector requiring identity verification.

## Sample implementations
- Privado ID (JSON-LD): basic person
- Oasis Lightweight Verifiable Credential Schema & Process


## Patent Policy
The Decentralized Identity Foundation has adopted the W3C Patent Policy (2004).
