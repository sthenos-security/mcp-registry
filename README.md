# REACHABLE MCP Registry

[![Registry API](https://img.shields.io/badge/registry-registry.sthenosec.com-blue)](https://registry.sthenosec.com/v0.1/servers)
[![MCP](https://img.shields.io/badge/MCP-server%20registry-black)](https://modelcontextprotocol.io)
[![Status: early access (beta)](https://img.shields.io/badge/status-early%20access%20(beta)-orange)](https://sthenosec.com)
[![Sthenos Security](https://img.shields.io/badge/Sthenos%20Security-sthenosec.com-B22222)](https://sthenosec.com)

Public [Model Context Protocol](https://modelcontextprotocol.io) registry data
for **REACHABLE** by [Sthenos Security](https://sthenosec.com):
reachability-verified AppSec and AI supply-chain scanning with autonomous
remediation, run locally.

This repository holds data only. It does not contain the REACHABLE scanner or
the MCP server code.

## Registry API

The files here are served at `https://registry.sthenosec.com`:

| Endpoint | Returns |
|---|---|
| [`/v0.1/servers`](https://registry.sthenosec.com/v0.1/servers) | All servers in this registry |
| [`/v0.1/servers/com.sthenosec%2Freachable`](https://registry.sthenosec.com/v0.1/servers/com.sthenosec%2Freachable) | The current `com.sthenosec/reachable` entry |
| `/v0.1/servers/com.sthenosec%2Freachable/versions` | Every published version |
| [`/v0.1/servers/com.sthenosec%2Freachable/versions/latest`](https://registry.sthenosec.com/v0.1/servers/com.sthenosec%2Freachable/versions/latest) | One version (`latest` or e.g. `1.0.0-beta.261`) |

Entries follow the official
[server.json schema](https://static.modelcontextprotocol.io/schemas/2025-12-11/server.schema.json).

## Layout

```
servers/com.sthenosec/reachable/
  server.json            current entry
  versions/index.json    list of published versions
  versions/latest.json   the latest version
  versions/<version>.json
```

## Installing the REACHABLE MCP server

The server runs locally over stdio as `reachctl vibe mcp serve`. It is installed
by the signed REACHABLE installer, not from this repository:

- Download and install: <https://sthenosec.com/download>
- Claude Code and Codex plugins:
  [reachable-agent-plugin-installer](https://github.com/sthenos-security/reachable-agent-plugin-installer)

## How this repository is updated

A release workflow regenerates `servers/` on every signed REACHABLE release and
pushes it here, so each version entry matches a published release. Do not edit
`servers/` by hand; changes are overwritten on the next release.

Questions: <support@sthenosec.com>
