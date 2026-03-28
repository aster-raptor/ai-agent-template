# Release Notes

Use this skill when drafting release notes from commits, merged pull requests, or a sprint summary.

## Goals

- explain user-visible changes clearly
- group changes by theme
- avoid internal-only implementation detail unless it affects operators

## Workflow

1. Gather the relevant commits, PRs, or issue summaries.
2. Remove duplicate points that describe the same change.
3. Group items into a few release themes.
4. Rewrite each item in user-facing language.
5. Add a short operations note only when deployment or configuration changed.

## Output

Provide:

- a short release summary
- grouped bullets for user-visible changes
- an optional operator note if setup, migration, or rollout changed
