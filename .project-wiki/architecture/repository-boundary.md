# Repository Boundary

Status: current

Last verified: 2026-06-11

Sources:

- `README.md`
- `skills/flato-design-mcp-guide/SKILL.md`
- `plugins/flato-design-mcp-codex/.codex-plugin/plugin.json`
- `docs/setup-codex.md`
- `registry/openai-review-notes.md`

## What Is True

Flato's product positioning is: Flato is the native canvas runtime for AI
design. Flato Design MCP connects AI agents to that editable visual canvas for
design work.

This repository is the public distribution package for Flato Design MCP setup
docs, the base guide skill, Codex plugin packaging, examples, screenshots, and
registry/review metadata.

It does not contain the hosted Flato MCP server source code.

The hosted MCP endpoint documented by this repository is:

```text
https://api.flato.ai/api/mcp/editor
```

## Working Rules

- Do not infer or document hosted server internals from this repo.
- Keep README positioning centered on Flato as the native canvas runtime for AI
  design, not a static output generator.
- Treat README, setup docs, skill files, plugin manifest, and registry metadata
  as public compatibility surfaces.
- When changing a public claim, use `.harness/checklists/doc-sync.md`.
- Preserve the distinction between install/connect guidance and live Flato
  project editing behavior.

## Update Triggers

- Hosted endpoint changes.
- Repository starts including server source.
- Package layout changes.
- Public install or release flow changes.
