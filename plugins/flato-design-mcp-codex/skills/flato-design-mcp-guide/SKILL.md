---
name: flato-design-mcp-guide
description: Use when creating, editing, inspecting, exporting, or troubleshooting Flato designs through Flato Design MCP tools such as flato_whoami, flato_get_design_context, flato_create_pages, flato_update_pages, flato_update_canvas, and flato_export_to_png.
---

# Flato Design MCP Guide

Use this skill whenever the user wants an AI agent to operate a Flato design
through MCP.

Flato is an editable visual design canvas. The MCP server gives agents tools,
resources, prompts, project targeting, image capabilities, and feedback. It is
not a hidden one-shot design agent. The agent must read current Flato context
explicitly and then call concrete MCP tools.

## Account And Plan Boundaries

A Flato account is required for OAuth. A paid Flato subscription is not required
to install, connect, or start using Flato Design MCP.

Do not tell users they must subscribe before connecting. If an MCP response says
a feature is limited by plan, usage, export, workspace, or credits, report that
specific limitation and suggest the next available path.

## Required Bootstrap

Before any design write:

1. Read Flato MCP resources when the host exposes resource reading.
2. Read `flato://canvas/fundamentals-v1`, or call
   `flato_get_canvas_fundamentals` as a fallback.
3. Call `flato_whoami`.
4. Establish a target project:
   - New design: call `flato_create_project`.
   - Existing editor/project URL: call `flato_use_project`.
   - Share URL: call `flato_use_share_link` to create an editable copy.
5. If the response says the live editor is needed, open `editorUrl` when the
   host supports URL opening. Otherwise ask the user to open it.
6. Poll `flato_get_project_status` until `canWrite=true`.
7. Call `flato_get_design_context` before each create or edit sequence.

Do not call write tools until `canWrite=true`.

## Targeting Rules

- Prefer `projectId` for saved projects.
- Use `clientId` only when targeting a specific live editor tab.
- Use `draftId` for an unsaved `/editor` canvas.
- Never guess `pageId` or `blockId`.
- Use ids returned by a fresh `flato_get_design_context` or `flato_get_state`.
- Selection is only a call-time snapshot. Re-read context before a
  selection-dependent edit.

## Write Rules

- Create pages with `flato_create_pages`.
- Update existing pages or blocks with `flato_update_pages`.
- Use `updateBlocks[].blockId` for existing blocks and `createBlocks` for new
  blocks.
- Change canvas size, grid, padding, page/global background defaults, or scope
  with `flato_update_canvas`.
- Set reusable project CSS with `flato_set_global_style`. CSS must be scoped
  under `.Canvas`.
- Delete blocks with `flato_delete_block`.
- Switch, duplicate, delete, or move pages with `flato_page_operation`.
- Use `flato_make_backup` before risky broad edits.

## Resource Policy

Do not rely only on tool descriptions for design work. MCP resources and prompts
are part of the operating contract.

Expected resources include:

- `flato://canvas/fundamentals-v1`
- `flato://prompt-skills`
- `flato://prompt-skills/general-design-default`
- `flato://prompt-skills/presentation-cover`
- `flato://prompt-skills/social-visual`
- `flato://prompt-skills/brand-system`
- `flato://brand-kits`

Read brand-kit resources when the user asks for branded, marketing, sales,
presentation, or customer-facing output.

## Interaction Rules

Page-level interactions are authored through `interactiveScript` on
`flato_create_pages` and `flato_update_pages`.

Rely on current MCP tool schemas and `flato://canvas/fundamentals-v1` for the
full interaction contract. Do not duplicate or guess unsupported schema fields.

Supported inline events include click/input/change and desktop hover/mouse
events such as `onclick`, `onchange`, `oninput`, `onmouseover`, `onmouseout`,
`onmouseenter`, and `onmouseleave`.

Hover is supported for desktop experiences. Include click/tap behavior or a
visible fallback when mobile touch users matter.

## Asset Rules

Asset tools such as image search, generation, editing, and understanding do not
mutate the design unless a specific write tool places the returned URL into a
page or block.

Do not claim an image is in the design until it has been explicitly written into
the canvas.

Paid image generation or editing may consume the authenticated Flato user's
credits.

## Feedback And QA

After a write:

1. Inspect `mcpFeedback` when present.
2. Re-read `flato_get_design_context`.
3. Use `layoutIssueSummary` as the compact layout QA signal.
4. Fix only reported page or block ids when possible.
5. For important output, call `flato_export_to_png` and then
   `flato_understand_image` for visual QA.

## Safety

- Do not ask users for passwords or bearer tokens.
- Do not inspect local OAuth or token stores.
- Do not invent project, page, block, brand-kit, or prompt-skill ids.
- Do not rebuild a whole design when a targeted fix is enough.
- If a command times out after a write, re-read context before retrying.

## Final Report

When done, report:

- target `projectId`
- affected page ids and important block ids
- whether a backup was created
- final `mcpFeedback.status` when available
- final `layoutIssueSummary`
- exported PNG / visual QA result when performed
