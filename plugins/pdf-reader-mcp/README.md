# PDF Reader MCP

Production-ready MCP server for reading PDF files from AI agents. Pairs well with the Excel MCPs in this marketplace: agents often need to ingest PDF reports that were exported from Excel.

## Command

`npx -y @sylphx/pdf-reader-mcp`

## Tools

- `read_pdf` — single tool that handles every PDF operation. Extract full text, specific page ranges, metadata (author, title, dates), page counts, and embedded images. Supports absolute and relative paths on Windows/Unix.

## Permissions

- filesystem-read
- pdf-read

## Safety

Read-only — no file writes. For path sandboxing, install `filesystem-tools` and let Allo confine the workspace via `ALLO_WORKSPACE_PATH`, then instruct the agent to keep all `path` arguments under that directory.
