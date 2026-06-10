# Tools And Permissions

Flato MCP tools can read project context and, after authorization, write to
editable Flato projects owned or accessible by the authenticated user.

Typical read tools include:

- `flato_whoami`
- `flato_get_project_status`
- `flato_get_design_context`
- `flato_get_state`
- `flato_get_style_info`

Typical write tools include:

- `flato_create_project`
- `flato_create_pages`
- `flato_update_pages`
- `flato_update_canvas`
- `flato_set_global_style`
- `flato_delete_block`
- `flato_page_operation`

Image generation or editing features may consume the authenticated Flato user's
credits when those tools are available and used.
