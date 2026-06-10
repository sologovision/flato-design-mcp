---
name: flato-design-mcp-guide
description: Use when creating, editing, inspecting, exporting, or troubleshooting Flato designs through Flato Design MCP tools such as flato_whoami, flato_get_design_context, flato_create_pages, flato_update_pages, flato_update_canvas, and flato_export_to_png.
---

# Flato Design MCP Guide

Use this skill whenever the user wants Codex to operate a Flato design through
MCP.

A Flato account is required for OAuth. A paid Flato subscription is not required
to install, connect, or start using Flato Design MCP. If MCP reports a plan,
usage, export, workspace, or credit limit, explain that specific limitation
instead of asking users to subscribe in advance.

Before any design write:

1. Read Flato MCP resources when available.
2. Read `flato://protocol/creative-v1`, or call
   `flato_get_creative_protocol` as a fallback.
3. Call `flato_whoami`.
4. Create or select a project with `flato_create_project`,
   `flato_use_project`, or `flato_use_share_link`.
5. Open the live editor URL if requested.
6. Poll `flato_get_project_status` until `canWrite=true`.
7. Call `flato_get_design_context` before writing.

Do not guess `pageId` or `blockId`. Use ids returned by fresh context reads.

Use `flato_create_pages` for new pages and `flato_update_pages` for existing
pages or blocks. Use `createBlocks` for new blocks and `updateBlocks[].blockId`
for existing blocks.

Inspect `mcpFeedback` after writes. Re-read design context after writes. For
important output, export PNG and run visual QA.

Do not ask users for passwords, bearer tokens, or local OAuth token contents.
Do not inspect local OAuth or token stores.
