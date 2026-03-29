# Codex Setup Guide

This guide uses project-scoped configuration so each repository can declare its own agent tooling.

## Prerequisites

- Codex CLI, Codex app, or the Codex IDE extension
- Node.js if you want to run `npx`-based MCP servers
- Any required tokens exported in your shell or stored in a local `.env`

## Where Config Lives

This template uses:

- `.codex/config.toml` for project-scoped Codex configuration
- `.codex/agents/*.toml` for project-scoped custom agents
- `.env` for local secrets and tokens

Codex can also use `~/.codex/config.toml` and `~/.codex/agents/`, but the project-scoped files are easier to share as a template.

## Setup on Windows

1. Copy `.codex/config.toml.example` to `.codex/config.toml`.
2. Copy `.env.example` to `.env`.
3. Edit `.codex/config.toml` and enable the MCP servers you want.
4. Review the example agent files under `.codex/agents/`.
5. Open a new Codex session in this repository.
6. Run `/mcp` to confirm the servers are visible.
7. Run `/plugins` if you want to browse and install Codex plugins.

### Example: add Context7 from the CLI

```powershell
codex mcp add context7 -- npx -y @upstash/context7-mcp
```

### Example: edit project config directly

```toml
[mcp_servers.context7]
command = "npx"
args = ["-y", "@upstash/context7-mcp"]
enabled = true
```

## Setup on macOS / Linux

1. Copy `.codex/config.toml.example` to `.codex/config.toml`.
2. Copy `.env.example` to `.env`.
3. Export any tokens you need or load them from your preferred shell startup flow.
4. Review the example agent files under `.codex/agents/`.
5. Open a new Codex session in this repository.
6. Run `/mcp` to confirm the servers are visible.
7. Run `/plugins` if you want to browse and install Codex plugins.

### Example: add Context7 from the CLI

```bash
codex mcp add context7 -- npx -y @upstash/context7-mcp
```

### Example: edit project config directly

```toml
[mcp_servers.context7]
command = "npx"
args = ["-y", "@upstash/context7-mcp"]
enabled = true
```

## Installing Skills

### Repo-local skills

The recommended team workflow is to keep shared skills under `skills/` and version them with Git.

1. Add `skills/<skill-name>/SKILL.md`.
2. Commit the file.
3. Pull the repository on each machine.

### Curated or marketplace-installed skills

If you want to install a curated skill directly in Codex:

```text
$skill-installer <skill-name>
```

Use local installation for personal workflows. If the skill should be standardized for the team, copy the reviewed skill into this repository and treat it as repo-managed content.

## Installing Subagents

Current Codex custom agents are defined as TOML files, not Markdown notes.

1. Add a file under `.codex/agents/<name>.toml`.
2. Define `name`, `description`, and `developer_instructions`.
3. Optionally add fields like `model`, `model_reasoning_effort`, `sandbox_mode`, or agent-specific MCP and skill settings.
4. Commit the file and share it via Git.

## Recommended Starter MCP Servers

### `context7`

- Purpose: up-to-date developer documentation
- Type: STDIO
- Example command:

```toml
[mcp_servers.context7]
command = "npx"
args = ["-y", "@upstash/context7-mcp"]
enabled = true
```

### `playwright`

- Purpose: browser automation and webapp testing
- Type: STDIO
- Notes: choose the local command that matches how your Playwright MCP server is installed

### `github`

- Purpose: pull requests, issues, releases, repo search
- Type: server-specific
- Notes: use the transport and auth method required by the GitHub MCP server you standardize on

### `openai_docs`

- Purpose: official OpenAI and Codex documentation access
- Type: server-specific placeholder in this template
- Notes: wire this to the official Docs MCP setup your team uses

## Plugins in Codex

Plugins are Codex-specific. Install them from the Codex plugin directory:

- In the app, open the Plugins view.
- In the CLI, run:

```text
/plugins
```

Use plugins when you want a bundled workflow that may include:

- Skills
- app integrations
- MCP servers

The local config file is mainly useful for enable/disable control after a plugin is installed.

## Verification Checklist

After setup, confirm the following:

- `/mcp` shows at least one enabled MCP server
- `.codex/config.toml` parses cleanly
- `.codex/agents/*.toml` files are present for any custom agents you want to use
- required tokens are present in your environment
- `/plugins` opens the plugin directory in Codex