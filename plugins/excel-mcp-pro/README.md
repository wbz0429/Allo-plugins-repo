# Excel MCP Pro

The most popular Excel MCP server on npm, supporting value and formula read/write, full per-cell style formatting, named tables, sheet copy, and (on Windows) live sheet screenshots.

## Command

`npx -y @negokaz/excel-mcp-server`

## Environment

- `EXCEL_MCP_PAGING_CELLS_LIMIT` (default `4000`) — maximum cells returned in a single read page. Lower this if a sheet is very wide and the agent is running out of context.

## Tools

- `excel_describe_sheets` — list all sheets in a workbook.
- `excel_read_sheet` — read a sheet (or a range) with pagination; optionally return formulas or cell styles.
- `excel_write_to_sheet` — write values or formulas; create a new sheet or overwrite an existing one.
- `excel_create_table` — create a named table over a range.
- `excel_copy_sheet` — duplicate a sheet inside the same workbook.
- `excel_format_range` — apply per-cell font, fill, border, number format, and decimal places.
- `excel_screen_capture` — screenshot a sheet range. **Windows only**; the call will fail on macOS/Linux.

## Permissions

- filesystem-read
- filesystem-write
- excel-read
- excel-write
- excel-formulas
- excel-formatting

## Safety

The npm tarball bundles a Python runtime + `openpyxl` (≈105MB unpacked). No separate Python install is required, but the first MCP launch is noticeably slower.

This server does **not** enforce a workspace path — every tool takes `fileAbsolutePath` directly from the agent. If you need to sandbox file access, install the `filesystem-tools` plugin and let Allo confine the workspace there, then instruct the agent to only operate on files inside `ALLO_WORKSPACE_PATH`.
