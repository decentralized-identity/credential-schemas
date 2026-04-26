# WPAI C2PA Monitor record

JSON Schema and JSON-LD **subject** shape for the C2PA Monitor experiment in the WordPress AI plugin: the value stored as a JSON string in post meta key `_wpai_monitor_record`.

- **JSON Schema:** [`schema.json`](./schema.json) — `allOf` the [OpenVerifiable `media-provenance-capture`](../../../OpenVerifiable/schemas/media-provenance-capture/schema.json) subject plus `schema_version`, `duration_ms`, and `source.attachment_id`.
- **JSON-LD context:** [`context.json`](./context.json) — same logical fields; WordPress-specific terms use the `ov` vocabulary (see [OpenVerifiable](https://openverifiable.ai)).

**Not** a Verifiable Credential — do not add `issuer`, `proof`, or `credentialSubject` to these files. Wrap at issuance time if needed.

## Resolution

`https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/WordPress/schemas/wpai-monitor-record/schema.json`

`https://raw.githubusercontent.com/decentralized-identity/credential-schemas/main/community-schemas/WordPress/schemas/wpai-monitor-record/context.json`

Refer to this schema from plugin PHP docblocks and READMEs as the canonical postmeta contract.
