# Authentication

Flato Design MCP uses browser OAuth. Users should authorize Flato in the browser
when their MCP client asks for authentication.

If needed, Flato asks you to sign in or create an account before authorization.

A paid Flato subscription is not required to install, connect, or start using
Flato Design MCP. Some features, exports, higher usage, team/workspace
capabilities, or paid image generation and editing may still depend on the
authenticated user's Flato plan or credits.

Agents and users should not copy or expose bearer tokens, refresh tokens, local
OAuth cache files, or passwords.

If authorization is revoked, future MCP requests should fail until the user
authorizes Flato again.
