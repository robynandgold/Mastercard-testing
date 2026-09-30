# Mastercard testing

Workspace for exploring Mastercard Developers APIs with Claude Code through the
public Mastercard Developers MCP server (`@mastercard/developers-mcp`).

## MCP server

`.mcp.json` registers the server as `mastercard-developers`, pinned to v0.1.7.
`.claude/settings.json` pre-approves it, so its tools load automatically when a
Claude Code session opens this repo.

The server is read-only. It reads public documentation and API specifications
from the Mastercard Developers platform and needs no credentials.

| Tool | Purpose |
| --- | --- |
| `get-services-list` | List all Mastercard Developers products and services |
| `get-documentation` | Documentation overview for one service |
| `get-documentation-section-content` | Content of one documentation section |
| `get-documentation-page` | Full content of one documentation page |
| `get-oauth10a-integration-guide` | OAuth 1.0a integration guide |
| `get-oauth20-integration-guide` | OAuth 2.0 integration guide |
| `get-openfinance-integration-guide` | Open Finance integration guide |
| `get-api-operation-list` | All operations in an API specification |
| `get-api-operation-details` | Parameters and schemas for one operation |

## Network requirements

The server fetches content at runtime, so the environment must allow outbound
HTTPS to:

- `developer.mastercard.com`
- `static.developer.mastercard.com`
- `registry.npmjs.org` (to install the package)

In Claude Code on the web, add the first two hosts under the environment's
Network access settings.
