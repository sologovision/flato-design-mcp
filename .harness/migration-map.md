# Migration Map

This map classifies existing project sources for future AI agents.

## Current Sources

These files are current public surfaces and should be checked before related
changes:

- `README.md`: primary project overview, install commands, safety principles,
  screenshots, release asset naming, and roadmap.
- `docs/setup-codex.md`: Codex installation path.
- `docs/setup-claude-code.md`: Claude Code installation path.
- `docs/setup-cursor.md`: Cursor and generic MCP client setup.
- `docs/authentication.md`: OAuth and account guidance.
- `docs/tools-and-permissions.md`: MCP tool capability summary and permission
  expectations.
- `docs/troubleshooting.md`: current troubleshooting guidance.
- `skills/flato-design-mcp-guide/SKILL.md`: base installable agent guide.
- `plugins/flato-design-mcp-codex/skills/flato-design-mcp-guide/SKILL.md`:
  Codex plugin bundled copy of the guide.
- `plugins/flato-design-mcp-codex/.codex-plugin/plugin.json`: plugin manifest.
- `plugins/flato-design-mcp-codex/.mcp.json`: plugin MCP server config.
- `.agents/plugins/marketplace.json`: Codex marketplace descriptor.
- `registry/mcp-server.json`: registry metadata draft.
- `registry/openai-review-notes.md`: OpenAI review context.
- `registry/claude-directory-submission.md`: Claude directory submission
  context.
- `examples/prompts/`: user-facing prompt examples for integration testing.

## Historical Or Review Context

These files can contain current facts, but review them against README, docs,
plugin metadata, and skill files before promoting claims:

- `registry/openai-review-notes.md`
- `registry/claude-directory-submission.md`
- Screenshots under `assets/screenshots/`

## Conflict Watchlist

Resolved during initialization follow-up:

- `skills/flato-design-mcp-guide/SKILL.md` and
  `plugins/flato-design-mcp-codex/skills/flato-design-mcp-guide/SKILL.md`
  should remain byte-for-byte synchronized. The bundled plugin guide was synced
  to the base guide locally on 2026-06-11.

Watch for drift between:

- README setup commands and `docs/setup-*.md`.
- Plugin manifest version and release asset naming.
- Account/subscription guidance across README, auth docs, and skill files.
- Interaction support wording across README, tool docs, and skill files.

## Needs Verification

Before changing release claims, verify:

- Whether the current tag/version and plugin manifest version should match.
- Whether release assets exist for the version being documented.
- Whether marketplace or registry submission requirements have changed.
