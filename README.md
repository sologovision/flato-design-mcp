# Flato Design MCP

Official MCP package for connecting AI agents to Flato's editable design
canvas.

Flato Design MCP lets Codex, Claude Code, Cursor, and other MCP-capable agents
create, inspect, revise, export, and QA editable Flato design projects.

## What This Repo Contains

- `skills/flato-design-mcp-guide`: installable base guide skill for agents.
- `plugins/flato-design-mcp-codex`: Codex plugin package with MCP config and
  the guide skill.
- `docs/`: setup, OAuth, permissions, and troubleshooting notes.
- `registry/`: registry and platform review metadata drafts.
- `examples/prompts/`: first workflow prompts for testing the integration.

This repo does not contain the Flato MCP server source code. The hosted MCP
server is:

```text
https://api.flato.ai/api/mcp/editor
```

## Install Paths

### Codex

Install the Codex plugin package from:

```text
plugins/flato-design-mcp-codex
```

The plugin bundles:

- `.mcp.json`, pointing to the hosted Flato MCP server.
- `flato-design-mcp-guide`, the base workflow skill.
- Plugin metadata for Codex discovery and review.

See [Codex setup](docs/setup-codex.md).

### Claude Code

Add the hosted Flato MCP server, then use the guide skill in this repo:

```bash
claude mcp add --transport http flato-editor https://api.flato.ai/api/mcp/editor
```

See [Claude Code setup](docs/setup-claude-code.md).

### Cursor And Other MCP Clients

Use the hosted MCP server URL and follow the same operating rules from the guide
skill.

See [Cursor setup](docs/setup-cursor.md).

## First Workflow

After connecting Flato MCP, an agent should follow this sequence:

1. Call `flato_whoami`.
2. Create or select a project with `flato_create_project`,
   `flato_use_project`, or `flato_use_share_link`.
3. Open the live Flato editor when requested.
4. Poll `flato_get_project_status` until `canWrite=true`.
5. Call `flato_get_design_context` before any write.
6. Use concrete page and block ids returned by fresh context reads.
7. Inspect `mcpFeedback` after writes.
8. Export and visually QA important results.

## Safety Principles

- Do not ask users to paste passwords, bearer tokens, or local OAuth tokens.
- Do not inspect local OAuth or token stores.
- Do not guess `pageId` or `blockId`.
- Do not claim generated assets are placed until a design write uses the
  returned asset URL.
- Use backups before broad or risky edits.

## Related Flato Docs

- User docs: https://www.flato.ai/docs/mcp
- Agent-readable guide: https://www.flato.ai/docs/mcp.md
- Flato app: https://www.flato.ai

## Roadmap

This is the base package. Scenario-specific skills such as
`flato-presentation-skill` should build on this guide instead of duplicating the
connection, OAuth, targeting, and safety workflow.
