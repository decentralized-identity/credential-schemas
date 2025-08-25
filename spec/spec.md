# credential-schemas 1.0 Working Group Approved Spec

**Specification Status:** Working Group Approved Spec (August 2025)

**Latest Draft:**
[identity.foundation/credential-schemas](https://identity.foundation/credential-schemas)

**Ratified Versions:**

**Editors:**
~ Otto Mora - @ottomorac (Privado ID)
~ Adrian Field (One ID)
~ Kim Hamilton Duffy (DIF)
~ Valerio Massimo Camaiani - @vmc-crossmint (Crossmint)

<!-- -->

**Participate:**
~ [GitHub repo](https://github.com/decentralized-identity/credential-schemas)
~ [File a bug](https://github.com/decentralized-identity/credential-schemas/issues)
~ [Commit history](https://github.com/decentralized-identity/credential-schemas/commits/main)

Except where otherwise noted, this work by the [Decentralized Identity Foundation](https://identity.foundation/) is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0).

## Abstract

This specification defines multiple standards for common use case verifiable credentials including KYC (verified person), proof of age, AML, among others.

## Contribute your own schemas!

If you would like to contribute your own schemas to DIF's public repository please see our [community schemas repo](https://github.com/decentralized-identity/credential-schemas/tree/main/community-schemas). Your organization can contribute any credential schemas and the working group; we will periodically evaluate which schemas can be selected for standardization into this more formal specification.

## Status of This Document

This is a draft specification being developed within the
[Decentralized Identity Foundation](https://identity.foundation) (DIF). Design
work is ongoing, and participants are
encouraged to open issues or otherwise contribute at [the DIF-hosted github
repository](https://github.com/decentralized-identity/credential-schemas),
whether as input to stable versions or as recommendations for future versions.

## Terminology

[[def:Decentralized Identifiers, Decentralized Identifier, DID]]
~ Unique ID URI string and PKI metadata document format for describing the
cryptographic keys and other fundamental PKI values linked to a unique,
user-controlled, self-sovereign identifier in a target system (i.e. blockchain,
distributed ledger).

[[def:Claim, Claims]]
~ An assertion made about a [[ref:Subject]]. Used as an umbrella term for
Credential, Assertion, Attestation, etc.

## Structure of this Document

## Abstract Data Models

_Abstract data model_ is a “Data template” that specifies which attributes a credential should contain. It includes the field names and types, as well as an indication of their interpretation and use.
Abstract data model are fundamental in ensuring consistency and interoperability across differing verifiable credential formats in the market.

![Abstract data model table representation](images/abstract-data-model.png "abstract data model table")

### Formatting conventions: 

Field names use "camelCase" and only the minimal fields are required, however required fields will be dependent on the implementer and use case.

Country codes use the ISO 3166-1 alpha-3 codes (e.g. FRA, USA, CRC), this allows to accomodate use cases in which some countries are not fully recognized by the UN (example: Kosovo or Palestine) are represented with 3 letter codes in some standards such as [ICAO Doc 9303](https://www.icao.int/publications/Documents/9303_p3_cons_en.pdf).

#### Enumerations

Given that the enumeration fields (for example in the "Verified Person" schema for fields such as name type, identifier type, address type, contactChannel type) may not accommodate all possible values, implementers are allowed to substitute or expands these enumeration strings with an object that includes the value and a "enumDefinition" field which points to a custom enumeration. If the field value is just a string then the default enumeration is assumed.

Please see below for an example of both possibilities.

Enumeration field where the default enumeration is assumed:

::: example Identifier with default enum
  type: "passport"
:::

Enumeration field where a custom enumeration is used:

::: example Identifier with custom enum
  type: {
      value: "digitalPassport",
      enumDefinition: https://example.com/myPassportTypes
   }
:::
