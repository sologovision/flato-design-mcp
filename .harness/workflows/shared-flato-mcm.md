# Shared Flato MCM Workflow

Use this workflow when a Flato Design MCP distribution task touches public
market cognition: positioning, README or registry copy, installation narrative,
agent-facing skill guidance, examples, docs, sales/marketing language, or
customer-facing MCP descriptions.

## Before Writing

1. Read the shared MCM project `flato.marketing`.
2. Read the current Flato agent operating contract when the change affects
   agent behavior or public MCP expectations.
3. Verify public claims against current docs, registry metadata, product pages,
   demos, or proof URLs before using them.
4. Keep tool contracts, OAuth mechanics, package layout, release mechanics, and
   internal maintenance knowledge in `.project-wiki/`, not MCM.

## Update Rules

- Use explicit `project_id: flato.marketing` for every MCM operation.
- Do not create a repo-scoped marketing cognition project for this repository.
- Write to MCM only for durable public/runtime knowledge that should be shared
  with other Flato repositories.
- Prefer deterministic patches for small MCM updates.
- Run `mcm_check` after MCM writes.

## Failure Modes

- Letting README, registry, and skill copy drift from shared Flato positioning.
- Copying private MCP implementation details into public/runtime cognition.
- Creating a local MCM project that drifts from `flato.marketing`.
