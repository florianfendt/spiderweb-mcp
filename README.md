# Spiderweb MCP

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python: 3.12+](https://img.shields.io/badge/Python-3.12%2B-blue.svg)](https://www.python.org/)
[![FastMCP](https://img.shields.io/badge/MCP-FastMCP-green.svg)](https://github.com/jlowin/fastmcp)
[![Managed by: uv](https://img.shields.io/badge/Managed%20by-uv-purple.svg)](https://astral.sh/uv)

**Spiderweb MCP** is a host-native Model Context Protocol (MCP) gateway connecting LLM agents (Claude Code, Hermes Agent) with personal productivity tools: **Google Workspace (Calendar & Tasks)**, **GitHub**, and **SearXNG Search**.

Executed natively via `uv` over standard I/O (`stdio`).

---

## Features

- **Google Calendar:** Multi-calendar scans (primary, shared, family), event creation, fuzzy calendar matching, and deletion.
- **Google Tasks:** Full CRUD operations (list, create, complete, delete).
- **GitHub API Suite:** Manage issues, PRs, file commits, and branch inspections via PyGithub.
- **Local Web Search:** Private search queries routed through a local SearXNG instance.
- **Host-Native Execution:** Managed directly by `uv`—no container wrappers, zero runtime port conflicts.

## Project Structure

```text
spiderweb-mcp/
├── auth/                 # OAuth tokens & credentials.json (gitignored)
├── src/
│   └── spiderweb_mcp/
│       ├── auth/         # OAuth2 handlers and token refresh
│       ├── tools/        # Modular tool definitions (Calendar, Tasks, GitHub, SearXNG)
│       └── server.py     # FastMCP stdio gateway
├── .env.example
├── pyproject.toml
├── uv.lock
└── README.md
