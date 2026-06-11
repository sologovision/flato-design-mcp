# Project Wiki Schema

Each wiki page should be short, sourced, and useful before editing.

## Required Fields

- `Status`: `current`, `historical`, `conflict`, `needs-verification`, or
  `raw`.
- `Last verified`: date of the most recent source check.
- `Sources`: current repository files that support the page.
- `What is true`: durable facts.
- `Working rules`: implementation or review guidance derived from those facts.
- `Update triggers`: when to revisit the page.

## Source Status

- `current`: verified against current repository files.
- `historical`: useful background but no longer authoritative.
- `conflict`: contradicts another source and needs resolution.
- `needs-verification`: plausible but not yet checked.
- `raw`: unstructured intake, not promoted.

## Entity Types

- `architecture`: ownership boundaries and system shape.
- `module`: repository packages or directories with stable responsibilities.
- `feature`: user-facing or platform-facing capability.
- `contract`: behavior that agents, users, or integrations depend on.
- `decision`: accepted tradeoff or policy.
- `method`: repeatable workflow for maintaining this project.
