# Authentication

Flato Design MCP uses browser OAuth. Users should authorize Flato in the browser
when their MCP client asks for authentication.

If needed, Flato asks you to sign in or create an account before authorization.

Agents and users should not copy or expose bearer tokens, refresh tokens, local
OAuth cache files, or passwords.

If authorization is revoked, future MCP requests should fail until the user
authorizes Flato again.
