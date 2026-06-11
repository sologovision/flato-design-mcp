# OAuth And Subscription Guidance

Status: current

Last verified: 2026-06-11

Sources:

- `README.md`
- `docs/authentication.md`
- `docs/tools-and-permissions.md`
- `skills/flato-design-mcp-guide/SKILL.md`

## What Is True

Flato Design MCP uses browser OAuth. A Flato account is required for OAuth.

A paid Flato subscription is not required to install, connect, or start using
Flato Design MCP.

Some features, exports, higher usage, team/workspace capabilities, or paid
image generation and editing may depend on the authenticated user's Flato plan
or credits.

Agents and docs must not ask users to paste passwords, bearer tokens, refresh
tokens, or local OAuth cache contents.

## Working Rules

- Phrase plan limitations as conditional MCP responses, not as a precondition
  for connecting.
- If authorization fails or is revoked, tell users to re-authorize in the
  browser.
- Do not inspect local OAuth token stores while troubleshooting.

## Update Triggers

- OAuth provider or login flow changes.
- Account requirement changes.
- Subscription policy changes.
- Security guidance changes.
