# Claude Code Setup

Add the hosted Flato MCP server:

```bash
claude mcp add --transport http flato-editor https://api.flato.ai/api/mcp/editor
```

Then use the guide skill in `skills/flato-design-mcp-guide` for the operating
workflow.

The expected first calls are:

1. `flato_whoami`
2. `flato_create_project` or `flato_use_project`
3. `flato_get_project_status`
4. `flato_get_design_context`

Only write after `flato_get_project_status` reports `canWrite=true`.
