# PR Review

Use this skill when reviewing a pull request or a local diff.

## Review Standard

Prioritize:

1. correctness bugs
2. regressions
3. missing tests
4. security or data handling risks
5. maintainability issues with immediate impact

## Workflow

1. Read the diff before reading the summary.
2. Check for behavior changes, not just style changes.
3. Verify that new branches and failure paths are covered by tests or reasoning.
4. Flag risky assumptions about auth, data shape, concurrency, or config.
5. Keep findings concrete and cite file paths and lines when possible.

## Output

Provide:

- findings first, ordered by severity
- a short note on residual risk
- a brief summary only after the findings
