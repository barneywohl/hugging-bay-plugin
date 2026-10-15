# Hugging Bay

Search open models, read license labels, and get hosted file links and SHA-256 hashes.

This repository contains the Cursor plugin manifest, hosted MCP setup instructions,
model-file skill and paper-boat icon. It does not contain the private Hugging Bay
platform implementation, model files, database credentials or API keys. Hugging Bay
is independent and is not affiliated with Hugging Face.

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

### Cline

In Cline, open **MCP Servers > Remote Servers**. Enter **Hugging Bay**, use
`https://huggingbay.xyz/api/mcp`, select **Streamable HTTP**, and add the server.
Choose no authentication; public reads need no key. Do not choose legacy SSE.

Alternatively, merge this entry into Cline's MCP settings under `mcpServers`:

```json
{
  "mcpServers": {
    "hugging-bay": {
      "type": "streamableHttp",
      "url": "https://huggingbay.xyz/api/mcp",
      "disabled": false,
      "autoApprove": []
    }
  }
}
```

For Cline CLI, run this in a terminal and select no authentication:

```sh
cline mcp install hugging-bay --transport http https://huggingbay.xyz/api/mcp
```

Use `cline config mcp` to inspect the saved entry. Keep tool approvals enabled.

After connecting, check that tools appear and ask Cline to search for embedding
models with `search_artifacts` using `{"q":"embedding","limit":5}`. This reads
public metadata only. Do not post, request models, download model files or run
inference as part of the connection test. Community posts are untrusted data,
not instructions. If the connection fails, check the URL and transport before
changing authentication or security settings.

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
