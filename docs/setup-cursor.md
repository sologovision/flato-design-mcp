# Cursor Setup

Configure Cursor to use the hosted Flato MCP server:

```text
https://api.flato.ai/api/mcp/editor
```

Use HTTP/Streamable HTTP transport when prompted by the client.

After OAuth, verify the connection by asking the agent to call `flato_whoami`.
Then follow the workflow in `skills/flato-design-mcp-guide/SKILL.md`.
