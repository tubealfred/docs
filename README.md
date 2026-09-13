# TubeAlfred Docs

Source for the [TubeAlfred](https://tubealfred.com) developer documentation, covering the REST API, hosted MCP server, and command-line interface. The documentation is built with Mintlify from the repository root.

## Documentation map

- [`index.mdx`](./index.mdx) — product and interface overview
- [`quickstart.mdx`](./quickstart.mdx) — first authenticated REST request
- [`video.mdx`](./video.mdx), [`channel.mdx`](./channel.mdx), [`discovery.mdx`](./discovery.mdx), [`playlist.mdx`](./playlist.mdx), and [`utility-batch.mdx`](./utility-batch.mdx) — legacy-compatible API overview routes
- [`guides/authentication.mdx`](./guides/authentication.mdx) — API keys and MCP OAuth
- [`guides/api-concepts.mdx`](./guides/api-concepts.mdx) — envelopes, pagination, errors, idempotency, billing, and versioning
- [`guides/mcp.mdx`](./guides/mcp.mdx) — hosted MCP setup
- [`guides/cli.mdx`](./guides/cli.mdx) — CLI installation and workflows
- [`docs.json`](./docs.json) — Mintlify theme, navigation, and API-reference configuration

The canonical API description is [TubeAlfred's public OpenAPI document](https://tubealfred.com/openapi.json). Mintlify uses it to generate the endpoint reference, so this repository does not maintain a duplicate operation catalog.

## Local development

Clone the public repository:

```bash
git clone https://github.com/tubealfred/docs.git
cd docs
```

Run the official Mintlify CLI from the repository root without adding it as a project dependency:

```bash
PUPPETEER_SKIP_DOWNLOAD=true npx --yes mintlify@latest validate
PUPPETEER_SKIP_DOWNLOAD=true npx --yes mintlify@latest broken-links
PUPPETEER_SKIP_DOWNLOAD=true npx --yes mintlify@latest dev --open=false
```

Use an isolated npm cache when the CLI is not already cached. Local search requires Mintlify CLI login.

## Contributing

This repository is the source of truth for documentation changes. Make and review documentation edits here rather than synchronizing changes in both this repository and the TubeAlfred application repository.

Changes to the remote OpenAPI document are made in the application that generates it. After an OpenAPI change is deployed and verified, the current free-plan workflow requires **Activity → Manual update** in the Mintlify dashboard to rebuild the generated reference.

Social previews use Mintlify's generated, page-specific cards with a light background, Figtree, and the TubeAlfred logo configured in `docs.json`. The logo wordmarks are SVG outlines so they do not depend on a viewer's installed fonts. After publishing branding changes, verify `og:image` and `twitter:image` on a guide and an API reference page; social platforms may retain previously cached previews.

## Hosting status

The guides, landing, legacy-compatible overview pages, and generated reference are live through Mintlify under `https://tubealfred.com/docs` after the Forge routing cutover. Laravel continues to serve the explicitly preserved machine-readable documentation routes. The overview pages retain legacy paths and endpoint bookmarks.
