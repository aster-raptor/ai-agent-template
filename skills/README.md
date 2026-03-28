# Local Skills

This directory contains repo-local skills.

Use a local skill when:

- the workflow is repeated often
- the instructions should live with the codebase
- the task does not need a separate delegated role

## Installation Methods

### Recommended: keep skills in this repository

1. Create a folder under `skills/<skill-name>/`.
2. Add a `SKILL.md`.
3. Commit it to Git.
4. Reuse it across machines by cloning or pulling this repository.

This is the best default for team-shared skills.

### Install a curated skill from the marketplace or installer flow

1. Open Codex.
2. Run `$skill-installer <skill-name>`.
3. If the skill is only for you, keep it in your local Codex skill directories.
4. If the skill should be shared with the team, copy the reviewed content into this repo's `skills/` directory and manage it with Git.

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