# AI Agent Workspace Template

This repository is a starter template for setting up an AI-assisted development workspace.

It is centered on Codex, with notes for other clients where the concepts overlap.

## What This Template Covers

- `MCP`
  - Connect external tools, docs, and services to your agent.
- `Plugins`
  - Codex-specific workflow bundles that can include skills, app integrations, and MCP servers.
- `Skills`
  - Reusable task instructions you can keep in the repo and share with your team.
- `Subagents`
  - Reusable role definitions for delegated work. See [subagents/README.md](C:\Develop\ai-agent-template\subagents\README.md).

## Quick Start

1. Copy [.codex/config.toml.example](C:\Develop\ai-agent-template\.codex\config.toml.example) to `.codex/config.toml`.
2. Enable the MCP servers you need and fill in any required environment variables from [.env.example](C:\Develop\ai-agent-template\.env.example).
3. Add local skills from [skills/README.md](C:\Develop\ai-agent-template\skills\README.md) and install Codex plugins from the plugin directory when needed.

## Repository Layout

- [docs/agent-tooling-overview.md](C:\Develop\ai-agent-template\docs\agent-tooling-overview.md)
  - Concept map across Codex, Claude Code, and Cursor.
- [docs/codex-setup.md](C:\Develop\ai-agent-template\docs\codex-setup.md)
  - Codex CLI / App / IDE setup guide for Windows and macOS/Linux.
- [docs/catalog.md](C:\Develop\ai-agent-template\docs\catalog.md)
  - Recommended starter catalog for MCP, Plugins, and Skills.
- [skills/README.md](C:\Develop\ai-agent-template\skills\README.md)
  - How to add and maintain local repo skills.
- [subagents/README.md](C:\Develop\ai-agent-template\subagents\README.md)
  - Existing role-based delegation examples.

## Recommended Workflow

Use this template in the following order:

1. Start with MCP for shared tools and documentation access.
2. Add repo-local Skills for repeatable tasks that should live with the codebase.
3. Add Codex Plugins for bundled workflows and external app integrations.
4. Use Subagents when you want role-based delegation on larger tasks.

## Notes

- Codex stores MCP configuration in `config.toml`. This template uses project-scoped `.codex/config.toml`.
- Codex plugins are installed from the Codex plugin directory. The config file is mainly for enable/disable control.
- Skills in this repository are intentionally small and dependency-free so they can be copied into new projects quickly.
