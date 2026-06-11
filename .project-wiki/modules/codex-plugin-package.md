# Codex Plugin Package

Status: current

Last verified: 2026-06-11

Sources:

- `plugins/flato-design-mcp-codex/.codex-plugin/plugin.json`
- `plugins/flato-design-mcp-codex/.mcp.json`
- `plugins/flato-design-mcp-codex/skills/flato-design-mcp-guide/SKILL.md`
- `.agents/plugins/marketplace.json`
- `README.md`

## What Is True

The Codex plugin package lives at `plugins/flato-design-mcp-codex/`.

The plugin manifest declares:

- plugin name: `flato-design-mcp-codex`
- version: `0.1.0`
- skills directory: `./skills/`
- MCP server config: `./.mcp.json`
- display name: `Flato Design MCP`

The package bundles the guide skill and MCP server configuration so Codex can
install the Flato MCP integration from this repository's marketplace metadata.

The bundled plugin guide is expected to stay byte-for-byte synchronized with
the base guide at `skills/flato-design-mcp-guide/SKILL.md`.

## Working Rules

- Keep the bundled plugin skill byte-for-byte synchronized with
  `skills/flato-design-mcp-guide/SKILL.md` when changing agent behavior or
  preparing a release.
- If manifest metadata changes, check README, marketplace metadata, registry
  notes, and release asset naming.
- Do not change the plugin's public capability claims without verifying the MCP
  config and guide skill still support them.

## Update Triggers

- Plugin version bumps.
- Manifest shape changes.
- MCP server config changes.
- Skill path or package layout changes.
- Marketplace metadata changes.
