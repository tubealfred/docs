# TubeAlfred documentation

This private repository is the source of truth for future TubeAlfred Mintlify documentation edits: `https://github.com/raakesh/tubealfred-docs`. It contains only the six hand-authored MDX pages and `docs.json`; the remote production OpenAPI document generates the API reference.

The original application draft remains a migration reference. Do not create two-way synchronization or make future documentation edits in both repositories. Mintlify is not connected to this repository, and publication is still pending explicit approval.

## Local validation

Run from the repository root without adding Mintlify as a dependency:

```bash
PUPPETEER_SKIP_DOWNLOAD=true npx --yes mintlify@latest validate
PUPPETEER_SKIP_DOWNLOAD=true npx --yes mintlify@latest broken-links
PUPPETEER_SKIP_DOWNLOAD=true npx --yes mintlify@latest dev --open=false
```

Use an isolated npm cache when the CLI is not already cached. Local search requires Mintlify CLI login.

## Remote OpenAPI updates

Mintlify reads `https://tubealfred.com/openapi.json`, but a remote specification change does not trigger an automatic documentation deployment. On the current free plan, deploy and verify the application OpenAPI change, then use **Activity → Manual update** in Mintlify after explicit rebuild approval. Verify the affected generated endpoint page when the rebuild finishes.

Mintlify connection, publishing, rebuilds, and hosting changes require explicit approval.
