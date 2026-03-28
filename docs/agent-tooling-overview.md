# Agent Tooling Overview

This template uses Codex as the primary target, but the same ideas map to other agent clients with different names and setup flows.

## Concept Mapping

| Concept | Codex | Claude Code | Cursor |
| --- | --- | --- | --- |
| External tools and shared context | MCP | MCP | MCP |
| Bundled workflows with integrations | Plugins | No direct equivalent | No direct equivalent |
| Reusable task instructions | Skills | Repo instructions / prompts / skills-style docs | Rules / prompts / repo docs |
| Delegated roles | Subagents | Parallel agents / task decomposition | Agent workflows or manual task splits |

## How To Read This Template

- `MCP` is the most portable layer.
- `Plugins` are Codex-specific.
- `Skills` are portable in spirit, but not identical across clients.
- `Subagents` are separate from skills.

## Practical Guidance

- Use `MCP` when the agent needs tools, APIs, browser access, docs, or third-party systems.
- Use `Skills` when the team repeats the same task pattern across issues or repos.
- Use `Plugins` when Codex users want pre-bundled workflows with app integrations.
- Use `Subagents` when the work benefits from role-based decomposition.

## Suggested Adoption Order

1. Set up one or two MCP servers.
2. Add one local skill for a common repo task.
3. Add Codex plugins only when the team actually needs bundled external integrations.
4. Introduce subagents for larger or parallel workflows.
