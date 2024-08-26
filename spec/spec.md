# credential-schemas 0.1 Editor's Draft

**Specification Status:** Pre-Draft

**Latest Draft:**
[identity.foundation/credential-schemas](https://identity.foundation/credential-schemas)

**Ratified Versions:**

**Editors:**
~

<!-- -->

**Participate:**
~ [GitHub repo](https://github.com/decentralized-identity/credential-schemas)
~ [File a bug](https://github.com/decentralized-identity/credential-schemas/issues)
~ [Commit history](https://github.com/decentralized-identity/credential-schemas/commits/main)

Except where otherwise noted, this work by the [Decentralized Identity Foundation](https://identity.foundation/) is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0).

## Abstract

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

::: todo add diagram
  Need to add diagram explaining abstract data model
:::


_Credential Manifests_ are a resource format that defines preconditional
requirements, Issuer style preferences, and other facets User Agents utilize to
help articulate and select the inputs necessary for processing and issuance of a
specified credential.
