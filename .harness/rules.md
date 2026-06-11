# Harness Rules

## Source Of Truth Order

1. Current repository files.
2. Explicit user instruction.
3. Harness rules.
4. Project wiki.
5. Historical docs, review notes, and raw notes.

## Repository Boundary

This repository distributes setup docs, guide skills, Codex plugin packaging,
examples, screenshots, and registry/review metadata for Flato Design MCP. It is
not the hosted Flato MCP server source.

Do not document server internals unless the current repo contains the relevant
source or the user provides a verified source.

## Compatibility Priorities

Protect these surfaces first:

- Public install commands in `README.md` and `docs/setup-*.md`.
- Agent operating contract in `skills/flato-design-mcp-guide/SKILL.md`.
- Codex plugin manifest and MCP config in `plugins/flato-design-mcp-codex/`.
- Registry and marketplace metadata in `registry/` and `.agents/plugins/`.

## Safety Rules

- Do not ask users to paste passwords, bearer tokens, refresh tokens, or local
  OAuth cache contents.
- Do not inspect local OAuth token stores.
- Do not guess Flato project, page, block, brand-kit, or prompt-skill ids in
  docs or examples.
- If a write timeout is discussed, instruct agents to re-read design context
  before retrying.

## Minimalism

Reuse existing wording, files, and project structure when they fit. Avoid new
abstractions, generated boilerplate, or broad rewrites unless they reduce real
maintenance risk.

## Verification

Prefer mechanical checks when available. For this repository, useful checks are
mostly file inspection, duplicate guidance checks, package manifest checks, and
git state checks.
