# Subagents

This directory contains reusable subagent definitions for Codex-style delegated work.

## How Subagents Are Managed

Subagents do not have a dedicated installer like skills or plugins.
The normal way to manage them is to keep Markdown definition files in the repository and reuse them across machines via Git.

## Installation Method

### Recommended: manage subagents in the repository

1. Create a file under `subagents/<name>.md`.
2. Describe the role, scope, strengths, and expected output.
3. Commit the file to Git.
4. Clone or pull the repository on each machine.
5. Reference the definition when creating or instructing a delegated agent.

## When To Use a Subagent

Use a subagent when:

- you want a stable delegated role
- you want repeatable ownership boundaries
- you want to standardize the tone or review angle of delegated work

## Suggested Agent Types

- implementation-heavy tasks: `agent_type: "worker"`
- repo exploration and analysis: `agent_type: "explorer"`
- mixed or general-purpose tasks: `agent_type: "default"`

## Included Examples

- `backend-architect.md`
- `devops-automator.md`
- `autonomous-optimization-architect.md`
- `git-workflow-master.md`
- `data-engineer.md`
- `analytics-reporter.md`
- `executive-summary-generator.md`
- `trend-researcher.md`

## Practical Notes

- Keep subagents small and role-focused.
- Prefer Git-managed Markdown files over machine-local copies.
- If a subagent becomes workflow-oriented instead of role-oriented, move that logic into a skill.