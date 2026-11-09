# Media Provenance Capture

**Subject-only** JSON Schema and JSON-LD context for a read-only **intake-time** capture of C2PA manifest presence and related file metadata. Use as the payload for `credentialSubject` when wrapping in a [W3C Verifiable Credential](https://www.w3.org/TR/vc-data-model/); do not embed credential envelope properties (`issuer`, `proof`, etc.) in this document.

- **JSON Schema:** [`schema.json`](./schema.json) — machine validation of the record shape.
- **JSON-LD context:** [`context.json`](./context.json) — maps field names to [Schema.org](https://schema.org/) and OpenVerifiable vocabulary where applicable.

**CMS-agnostic:** no WordPress- or host-specific IDs. For the WordPress plugin postmeta shape, see [`../../../WordPress/schemas/wpai-monitor-record/`](../../../WordPress/schemas/wpai-monitor-record/README.md).

## Consuming `errors`

Each `errors[]` item should be interpreted as `schema:CreateAction` / `schema:InformAction` style diagnostics; JSON-LD term definitions for per-item `stage` and `message` are left to the issuing profile when this record is placed in a VC.

## `$id` resolution

After merge to `main` on the DIF [credential-schemas](https://github.com/decentralized-identity/credential-schemas) repository, `schema.json` resolves at:

`https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/OpenVerifiable/schemas/media-provenance-capture/schema.json`
