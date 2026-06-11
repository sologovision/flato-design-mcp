# Tools And Permissions

Flato MCP tools can read project context and, after authorization, write to
editable Flato projects owned or accessible by the authenticated user.

Typical read tools include:

- `flato_whoami`
- `flato_get_project_status`
- `flato_get_design_context`
- `flato_get_state`
- `flato_get_style_info`
- `flato_get_canvas_fundamentals`

Typical write tools include:

- `flato_create_project`
- `flato_create_pages`
- `flato_update_pages`
- `flato_update_canvas`
- `flato_set_global_style`
- `flato_delete_block`
- `flato_page_operation`

Page-level interactions are authored through `interactiveScript` on
`flato_create_pages` and `flato_update_pages`. Agents should rely on current
tool schemas and `flato://canvas/fundamentals-v1` for the full interaction
contract. Supported inline events include click/input/change and desktop
hover/mouse events such as `onclick`, `onmouseover`, `onmouseout`,
`onmouseenter`, and `onmouseleave`.

Hover is supported for desktop experiences. Include click/tap behavior or a
visible fallback when mobile touch users matter.

Image generation or editing features may consume the authenticated Flato user's
credits when those tools are available and used.

A paid Flato subscription is not required to connect or start using Flato Design
MCP. If a tool is limited by plan, usage, export, workspace, or credit rules, the
MCP response should surface that specific limitation.
