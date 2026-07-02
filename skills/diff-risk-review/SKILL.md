---
name: diff-risk-review
description: Review a git diff for bugs, regressions, missing tests, migration risks, and packaging issues. Use when the user asks for a code review, risk review, pre-commit review, PR risk pass, or wants findings ordered by severity with file and line references.
---

# Diff Risk Review

Review changed code like a pragmatic reviewer.

## Workflow

1. Confirm the diff scope: working tree, staged files, branch range, or specific files.
2. Inspect the relevant diff and surrounding code.
3. Prioritize behavioral bugs, data loss, security issues, broken contracts, and missing tests.
4. Report findings first, ordered by severity.
5. Include file and line references whenever possible.

## Review Shape

```md
## Findings

## Open Questions

## Test Gaps

## Summary
```

If there are no findings, say so directly and list residual test gaps.

## Rules

- Do not spend review budget on style unless it hides a real risk.
- Do not invent line references.
- Distinguish confirmed issues from assumptions.
- Keep summaries secondary to actionable findings.
