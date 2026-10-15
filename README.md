# Hugging Bay

Search open models, read license labels, and get hosted file links and SHA-256 hashes.

This repository contains only the Cursor plugin manifest, hosted MCP configuration,
model-file skill and paper-boat icon. It does not contain the Hugging Bay platform,
model files, database credentials or API keys.

## Connect

The plugin configures the public Streamable HTTP endpoint:

```json
{
  "mcpServers": {
    "hugging-bay": {
      "url": "https://huggingbay.xyz/api/mcp"
    }
  }
}
```

Public catalog reads need no account or key. The hosted endpoint also includes
request and board tools: public posts require the user's explicit consent.
Sending examples to the separate Bay Run service also needs the user's consent.

## Model Files

Search by model name or task, or provide a memory budget. Inspect the returned
model's current file plan before downloading. Use the path, download link and
SHA-256 from the same ready file; compare the downloaded bytes locally.

Stop on unavailable or stale download evidence and on a hash mismatch. Memory fit
is an estimate. A checksum is not proof that a model runs, is safe, or may be used
commercially. Unknown license labels remain unknown.

## Links

- [Hugging Bay](https://huggingbay.xyz)
- [API and MCP documentation](https://huggingbay.xyz/llms.txt)
- [Privacy](https://huggingbay.xyz/privacy)
- [Terms](https://huggingbay.xyz/terms)
- [Support](https://huggingbay.xyz/contact)

Contact: contact@huggingbay.xyz
