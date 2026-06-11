# Release Documentation Sync

Status: current

Last verified: 2026-06-11

Sources:

- `README.md`
- `registry/openai-review-notes.md`
- `registry/claude-directory-submission.md`
- `.agents/plugins/marketplace.json`
- `plugins/flato-design-mcp-codex/.codex-plugin/plugin.json`

## What Is True

Release-facing work spans README, registry metadata, marketplace metadata,
Codex plugin manifest, guide skill packages, and release asset names.

The README currently describes release assets named:

- `flato-design-mcp-guide-vX.Y.Z.zip`
- `flato-design-mcp-codex-vX.Y.Z.zip`

## Working Rules

1. Check git status before release edits.
2. Verify package version and release asset naming together.
3. Keep public claims in README, registry notes, and marketplace metadata
   aligned.
4. Verify the base skill and bundled plugin skill remain aligned.
5. Record durable release-process changes in this wiki page.

## Update Triggers

- Version bump.
- Release asset naming changes.
- Registry or marketplace submission requirements change.
- Plugin packaging changes.
