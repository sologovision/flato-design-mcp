# Knowledge Sync Workflow

Use when current docs, registry notes, examples, or skills disagree.

1. Find every occurrence of the disputed claim with `rg`.
2. Classify each source as current, historical, conflict, needs-verification,
   or raw.
3. Resolve from current repository files and explicit user instruction.
4. Update public docs or skill guidance only where needed.
5. Promote the verified durable fact into `.project-wiki/`.
6. Record the sync in `.harness/update-log.md`.
