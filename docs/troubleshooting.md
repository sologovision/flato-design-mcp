# Troubleshooting

## Tools Are Not Visible

Restart the MCP client or open a new agent conversation after installing the
plugin or adding the MCP server.

## Project Is Not Writable

Call `flato_get_project_status` and follow its next action. The user may need to
open the live Flato editor URL before writes can run.

## Command Timeout After A Write

A browser write may apply even if the MCP client reports a timeout. Do not
recreate the page. Re-read `flato_get_design_context` and continue from the
actual page and block ids.

## OAuth Problems

Re-authorize Flato in the browser. Do not inspect local OAuth token stores.
