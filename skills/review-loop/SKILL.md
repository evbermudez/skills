---
name: review-loop
description: Convert code review feedback into focused fixes, verification, and a reviewer-ready response. Use when the user asks to address review comments, rerun a review loop, fix reviewer findings, apply nits, or summarize what changed after review.
---

# Review Loop

Handle review feedback as a fix-and-verify loop.

## Workflow

1. Read the review comments and classify each item as bug, risk, nit, question, or already-addressed.
2. Inspect the relevant files and current diff before editing.
3. Make the smallest coherent fix for each accepted item.
4. Run focused verification for the touched behavior.
5. Summarize which comments were fixed, which were declined, and why.

## Rules

- Do not broaden scope beyond the reviewed diff unless the fix requires it.
- Do not change behavior for a style-only nit unless the user accepts that tradeoff.
- Preserve unrelated user changes in the working tree.
- If a comment is incorrect, explain the evidence instead of making churn.
- Keep final responses reviewer-ready: files changed, verification run, residual risk.

## Useful Commands

```bash
git status --short
git diff
git diff --cached
```
