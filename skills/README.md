# Local Skills

This directory contains repo-local skills.

Use a local skill when:

- the workflow is repeated often
- the instructions should live with the codebase
- the task does not need a separate delegated role

## Skills vs Subagents

- A `skill` explains how to perform a task.
- A `subagent` describes who should take ownership of a task.

Use skills for repeatable execution patterns and subagents for role-based delegation.

## How To Add a Skill

1. Create a folder under `skills/<skill-name>/`.
2. Add a `SKILL.md`.
3. Keep the scope narrow and actionable.
4. Prefer referencing repo files and commands that already exist.
5. Avoid baking secrets or machine-specific paths into the skill.

## Included Examples

- [skills/repo-onboarding/SKILL.md](C:\Develop\ai-agent-template\skills\repo-onboarding\SKILL.md)
- [skills/pr-review/SKILL.md](C:\Develop\ai-agent-template\skills\pr-review\SKILL.md)
- [skills/release-notes/SKILL.md](C:\Develop\ai-agent-template\skills\release-notes\SKILL.md)
