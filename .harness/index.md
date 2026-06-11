# Harness Index

This is the AI development harness entry for the Flato Design MCP distribution
repository.

## Read Order

1. Read the root agent entry file.
2. Read this file.
3. Use `.harness/catalog.md` to route the task.
4. Read relevant `.project-wiki/` entities.
5. Inspect current repository files that are listed as sources of truth.
6. Choose the smallest workflow that fits the task.

## Responsibility Split

- `.harness/` owns process, routing, checklists, and verification habits.
- `.project-wiki/` owns durable project knowledge that has been checked against
  current repository files.
- Root entry files are launchers only.
- `raw/` preserves unstructured notes before they are promoted into wiki pages.

## Default Workflow

Use `.harness/workflows/small-change.md` for narrow documentation, packaging,
metadata, or skill edits.

Use `.harness/workflows/large-change.md` when a task changes install commands,
OAuth behavior, MCP tool contracts, package layout, release metadata, or public
agent guidance across multiple surfaces.

## Knowledge Gate

When a task changes durable behavior, contracts, decisions, repeated failure
modes, installation steps, or agent workflow rules, update `.project-wiki/` or
record why no wiki change is needed.
