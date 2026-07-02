---
name: pr-summary-format
description: Draft a structured pull request summary from a git diff, ticket, branch, or user-provided change notes. Use when the user asks for a PR description, PR body, pull request summary, release-ready change summary, or wants exact testing and risk notes captured for reviewers.
---

# PR Summary Format

Create a copy-ready PR body grounded in the actual diff and verification evidence.

## Workflow

1. Confirm the requested diff base, branch, or file scope.
2. Inspect the relevant diff with `git diff`, `git diff --cached`, or `git log --stat --patch`.
3. Identify the ticket, intent, user-facing behavior, implementation changes, and verification commands.
4. Keep unverified claims out of the summary.
5. Preserve exact commands and pass/fail results when the user provides or runs them.

## Default Format

Use this structure unless the repo or user gives a stricter template:

```md
## Summary
- 

## Changes
- 

## Verification
- 

## Notes
- 
```

Use `N/A` for empty sections only when the user expects a fixed template.

## Rules

- Do not invent tests, ticket links, screenshots, or reviewer context.
- Mention known caveats directly.
- Keep bullets concrete and diff-backed.
- If the user asks for a fenced block, wrap the whole PR body in one `md` fence.
