# ExampleEntity Schema

This document provides an overview of the `ExampleEntity` schema. The schema is defined in the `exampleEIP712Schema.json` file and follows the EIP-712 standard for structured data hashing and signing.

## Overview
The `ExampleEntity` schema defines the structure for a verifiable credential. It includes the following main components:

- **CredentialSubject**: The actual content of the credential:
  - `id`: A string representing the unique identifier of the subject.
  - `name`: A string representing the name of the subject.

- **VerifiableCredential**: This is the primary type that wraps the credential claim:
  - `@context`: An array of strings representing the context.
  - `type`: An array of strings representing the type.
  - `id`: A string representing the unique identifier.
  - `issuer`: An object of type `Issuer` representing the entity that issued the credential.
  - `credentialSubject`: An object of type `CredentialSubject` representing the content of the credential.
  - `validFrom`: A string representing the date from which the credential is valid.
  - `nft`: An object of type `Nft` representing the associated NFT.

- **Issuer**: This type includes the following field:
  - `id`: A string representing the unique identifier of the issuer.

- **Nft**: This type includes the following fields:
  - `tokenId`: A string representing the token ID of the NFT.
  - `contractAddress`: A string representing the contract address of the NFT.
  - `chain`: A string representing the blockchain chain of the NFT.

## Schema Details

- **File**: `exampleEIP712Schema.json`
- **Standard**: EIP-712
- **Purpose**: To define a sample for future schemas.

- **File**: `exampleJSONSchema.json`
- **Standard**: JSON-Schama
- **Purpose**: To define a sample for future schemas.


## TAGS

- `ExampleTag`

## License

This project is licensed under the MIT License.

