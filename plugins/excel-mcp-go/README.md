# Excel MCP (Go)

Lightweight MCP server written in Go for reading and writing spreadsheet files. Ships as a native binary via npm — no Python, no Node runtime required at install time.

## Command

`npx -y @xuzan/excel-mcp`

## Tools

- `read_excel` — read an `.xlsx` / `.xlsm` / `.xltx` / `.xltm` file and return data as JSON.
- `read_csv` — read a CSV file and return data as JSON.
- `write_excel` — write JSON data to an xlsx or CSV file, with correct integer/float formatting (no scientific notation).

## Permissions

- filesystem-read
- filesystem-write
- excel-read
- excel-write
- csv-read
- csv-write

## Safety

The binary is downloaded and executed by `npx`. Treat it like any other executable plugin — only install if you trust the publisher. For sandboxed file access, pair with the `filesystem-tools` plugin bound to the Allo workspace.
