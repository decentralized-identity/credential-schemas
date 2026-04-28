# WordPress (community schemas)

This folder contains **JSON Schema** and **JSON-LD** definitions for data shapes used by the [WordPress AI / AI plugin](https://github.com/WordPress/ai) ecosystem, contributed for public reuse. Schemas are **subject-only** (suitable for `credentialSubject`); the Verifiable Credential wrapper is applied at issuance time, not in these files.

- Each schema lives in its own subfolder with `schema.json` and `context.json`.
- Shared provenance concepts may `$ref` [OpenVerifiable](https://github.com/decentralized-identity/credential-schemas/tree/main/community-schemas/OpenVerifiable) subject schemas and extend them with WordPress-specific fields (e.g. attachment IDs, sidecar paths under `wp-content/uploads`).

See individual `schemas/*/README.md` files for details.
