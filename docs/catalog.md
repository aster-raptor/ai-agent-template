# Starter Catalog

This catalog keeps the starter set intentionally small. Add more only after the team has a clear use case.

## MCP

| Name | Use case | Dependency | Auth required | Best fit |
| --- | --- | --- | --- | --- |
| `openai-docs` | Official OpenAI and Codex documentation lookup | Team-standard Docs MCP setup | Usually yes | Codex, other MCP-capable clients |
| `context7` | Current library and framework docs | Node.js and `npx` | No | Codex, Claude Code, Cursor |
| `playwright` | Browser automation, UI checks, screenshots | Local Playwright MCP install | Sometimes | Codex, other MCP-capable clients |
| `github` | PR review, issues, releases, repo search | Chosen GitHub MCP server | Yes | Codex, Claude Code, Cursor |

## Plugins

Plugins are Codex-specific.

| Name | Use case | Dependency | Auth required | Best fit |
| --- | --- | --- | --- | --- |
| `gmail` | Summarize inbox, draft replies, triage threads | Codex plugin directory | Yes | Codex |
| `google-drive` | Search and summarize Docs, Sheets, and files | Codex plugin directory | Yes | Codex |
| `slack` | Summarize channels and draft responses | Codex plugin directory | Yes | Codex |

## Skills

These examples are local repo skills included in this template.

| Name | Use case | Dependency | Auth required | Best fit |
| --- | --- | --- | --- | --- |
| `repo-onboarding` | First-pass repo understanding and setup mapping | None | No | Any client with repo docs |
| `pr-review` | Consistent bug-first pull request reviews | None | No | Any client with code review workflows |
| `release-notes` | Draft release notes from commits and merged work | None | No | Any client with git context |

## Selection Guidance

- Start with `context7` if the team needs current technical docs.
- Add `github` next if reviews and issue workflows are central.
- Add `playwright` only when browser automation is actually needed.
- Install Codex plugins only for workflows that benefit from bundled external apps.
- Keep repo-local skills short and task-specific.
