# Excel MCP

Node.js MCP server for reading, writing, and formatting `.xlsx` / `.xls` spreadsheets. Built on top of `exceljs` and `@modelcontextprotocol/sdk`.

## Command

`npx -y @itkmoon/excel-mcp`

## Environment

- `EXCEL_ALLOW_WRITE=true` — enables write/format/sheet-management tools (default is read-only).
- `WORK_DIR=$ALLO_WORKSPACE_PATH` — confines all file operations to the current Allo workspace.

## Tools

- `read_excel` — read a worksheet or a specific range (e.g. `A1:C100`); optionally include formulas and formatting.
- `write_excel` — write data in `overwrite`, `append`, or `update` mode.
- `format_excel` — apply font, fill, border, alignment, and number format to a range.
- `manage_sheets` — list, create, rename, copy, or delete worksheets.
- `get_file_info` — get workbook size, sheet list, row/column counts, and modified time.

## Permissions

- filesystem-read
- filesystem-write
- excel-read
- excel-write
- workspace-only

## Safety

`WORK_DIR` is injected by Allo at runtime. Never point this plugin at a home directory or filesystem root. Write operations are gated by `EXCEL_ALLOW_WRITE`; flipping it to `false` makes the server read-only.
