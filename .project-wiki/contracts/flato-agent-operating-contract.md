# Flato Agent Operating Contract

Status: current

Last verified: 2026-06-11

Sources:

- `skills/flato-design-mcp-guide/SKILL.md`
- `plugins/flato-design-mcp-codex/skills/flato-design-mcp-guide/SKILL.md`
- `README.md`
- `docs/tools-and-permissions.md`
- `docs/troubleshooting.md`

## What Is True

Agents using Flato Design MCP must read current Flato context explicitly and
target concrete project, page, and block ids returned by the MCP server.

Before design writes, the guide requires agents to read canvas fundamentals,
call `flato_whoami`, establish a target project, wait until
`canWrite=true`, and call `flato_get_design_context`.

The base guide and bundled Codex plugin guide should remain byte-for-byte
synchronized so Codex plugin users receive the same operating contract.

Page-level interactions are authored through `interactiveScript` on
`flato_create_pages` and `flato_update_pages`. Agents should rely on current
MCP tool schemas and `flato://canvas/fundamentals-v1` for the full interaction
contract.

Asset tools do not mutate a design unless a write tool places the returned URL
into a page or block.

## Working Rules

- Never guess `pageId`, `blockId`, project ids, brand-kit ids, or prompt-skill
  ids.
- Re-read design context after writes and after command timeouts.
- Inspect `mcpFeedback` and `layoutIssueSummary` when present.
- Use backups before broad or risky edits.
- Keep README, tool docs, troubleshooting, and both skill copies synchronized
  when this contract changes.

## Update Triggers

- Tool names or required bootstrap steps change.
- Interaction event support changes.
- Asset mutation behavior changes.
- Feedback or QA fields change.
- New safety requirement is discovered.
