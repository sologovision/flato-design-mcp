# Installation Surfaces

Status: current

Last verified: 2026-06-11

Sources:

- `README.md`
- `docs/setup-codex.md`
- `docs/setup-claude-code.md`
- `docs/setup-cursor.md`
- `docs/authentication.md`
- `registry/mcp-server.json`
- `.agents/plugins/marketplace.json`

## What Is True

README is also the primary positioning surface for Flato Design MCP. It should
state that Flato is the native canvas runtime for AI design before diving into
MCP installation details.

The repository documents setup for Codex, Claude Code, Cursor, and other
MCP-capable clients.

The Codex path uses this repository as a plugin marketplace, installs
`flato-design-mcp-codex`, then runs MCP login for `flato-editor`.

Claude Code and Cursor setup point to the hosted MCP server URL.

Flato Design MCP uses browser OAuth. Users should not paste passwords, bearer
tokens, refresh tokens, or local OAuth cache contents into agent conversations.

## Working Rules

- Keep install commands exact and consistent across README and setup docs.
- Installation docs should not say a paid Flato subscription is required to
  connect or start using Flato Design MCP.
- If a feature is limited by plan, usage, export, workspace, or credits, docs
  should tell agents to report the specific MCP limitation.
- Any public setup change should be checked against registry and marketplace
  metadata.

## Update Triggers

- MCP endpoint changes.
- OAuth flow changes.
- Codex plugin installation commands change.
- Claude Code or Cursor setup changes.
- Account or subscription policy changes.
