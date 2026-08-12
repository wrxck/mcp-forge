---
name: mcp-forge
description: >-
  Scaffold a hardened MCP server that wraps a CLI tool or API, with input validation, injection
  prevention, path safety and rate limiting generated in rather than bolted on. Load when the user
  asks to build, scaffold or generate an MCP server, to wrap a command-line tool or API as MCP, or
  to audit an existing MCP server for security problems.
allowed-tools: "Bash Read Write Edit Glob Grep Task"
---

# mcp-forge

Scaffold hardened MCP servers wrapping CLI tools.

## Routing

| Command | Action |
|---------|--------|
| `/mcp-forge <cli-name>` | Run the main scaffold generator |
| `/mcp-forge:audit [path]` | Security audit an MCP server project |
| `/mcp-forge:install [path]` | Register generated server with Claude Code |
| `/mcp-forge:eval` | Run benchmarks (dev only) |

## References

Load these on demand -- do not read all upfront:

- `${CLAUDE_PLUGIN_ROOT}/skills/mcp-forge/references/mcp-sdk-patterns.md` -- MCP SDK v1.27.x API
- `${CLAUDE_PLUGIN_ROOT}/skills/mcp-forge/references/security-checklist.md` -- Security layers
- `${CLAUDE_PLUGIN_ROOT}/skills/mcp-forge/references/template-index.md` -- Template map
- `${CLAUDE_PLUGIN_ROOT}/skills/mcp-forge/references/eval-guide.md` -- Eval framework

## Templates

The generator writes the project itself, from the TypeScript templates in
`${CLAUDE_PLUGIN_ROOT}/generator/src/templates/`. There is nothing to read before running it.

`${CLAUDE_PLUGIN_ROOT}/skills/mcp-forge/references/template-index.md` lists which files come out and
under what condition, which is worth checking when a generated project is missing something you
expected.

## Examples

Complete worked examples at `${CLAUDE_PLUGIN_ROOT}/skills/mcp-forge/examples/`.

## Agents

- **cli-discoverer** -- Parses CLI help/man output into structured tool list
- **scaffold-writer** -- Reads templates, generates project files
- **security-auditor** -- Audits MCP server code for vulnerabilities
