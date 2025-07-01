# cheqd: Verifiable Credential Schemas

This directory contains JSON Schemas maintained by [cheqd](https://cheqd.io) for validating Verifiable Credentials that conform to the W3C Verifiable Credentials Data Model (VCDM v1.1).

cheqd is a decentralized identity and trust infrastructure network that enables the creation, exchange, and verification of trusted data such as Verifiable Credentials. These schemas support the standardization and validation of VCs issued on cheqd and other compatible systems.

## Available Schemas

### 🧾 Verifiable Attestation Schema

A generic schema for any Verifiable Credential asserting facts or attributes about an entity. This schema forms the base for more specific credential types, such as accreditations and authorisations.

- **DID URL** (JSONSchemaValidator2020):

`did:cheqd:mainnet:d938f973-49c2-4a0d-b4fd-99ab94b1979a?resourceName=VerifiableAttestation&resourceType=JSONSchemaValidator2020`

- **Resolvable URL**:

https://resolver.cheqd.net/1.0/identifiers/did:cheqd:mainnet:d938f973-49c2-4a0d-b4fd-99ab94b1979a?resourceName=VerifiableAttestation&resourceType=JSONSchemaValidator2020

- **Location in repo:**

`community-schemas/cheqd/draft-schemas/verifiable-attestation/schema.json`

### 🏛️ Verifiable Accreditation Schema

Extends the Verifiable Attestation schema. Used to assert that a subject (e.g., organisation or issuer) is accredited under a specific framework to issue certain types of credentials.

- **DID URL** (JSONSchemaValidator2020):

`did:cheqd:mainnet:d938f973-49c2-4a0d-b4fd-99ab94b1979a?resourceName=VerifiableAccreditation&resourceType=JSONSchemaValidator2020`

- **Resolvable URL**:

https://resolver.cheqd.net/1.0/identifiers/did:cheqd:mainnet:d938f973-49c2-4a0d-b4fd-99ab94b1979a?resourceName=VerifiableAccreditation&resourceType=JSONSchemaValidator2020

- **Location in repo:**

`community-schemas/cheqd/draft-schemas/verifiable-accreditation/schema.json`

## Usage

To use these schemas for validating Verifiable Credentials, include the `credentialSchema` property in the VC like so:

```json
"credentialSchema": {
"id": "did:cheqd:mainnet:d938f973-49c2-4a0d-b4fd-99ab94b1979a?resourceName=VerifiableAccreditation&resourceType=JSONSchemaValidator2020",
"type": "JsonSchemaValidator2020"
}
```

These schemas can also be resolved and dereferenced dynamically using DID URL dereferencing tools.

## License

Licensed under the Apache 2.0 License.