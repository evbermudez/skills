---
name: commit-summarizer
description: Summarize git commits, commit ranges, or uncommitted changes into concise commit messages or human-readable change summaries. Use when the user asks for a commit summary, commit message, changelog note, or wants to summarize one hash, multiple hashes, a range, HEAD/latest commit, staged files, unstaged files, or the current working tree.
---

# Commit Summarizer

## Workflow

Determine the source before drafting:

1. If the user provides one commit hash, summarize that commit with `git show --stat --patch <hash>`.
2. If the user provides multiple hashes, summarize each hash in order, then produce one combined summary unless the user asks for separate entries.
3. If the user provides a range, summarize the range with `git log --stat --patch <range>`.
4. If no hash or range is provided:
   - For commit-message requests, prefer staged changes with `git diff --cached`. If nothing is staged, use unstaged/untracked working-tree changes.
   - For committed-change summary requests, use the latest commit, `HEAD`.
   - If the user wording is ambiguous and both uncommitted changes and `HEAD` are plausible, inspect both briefly and state which source was used.

## Output Rules

- Keep the summary grounded in the diff. Do not infer product intent beyond what the changes show.
- For a commit message, output only the proposed message unless the user asks for explanation.
- Prefer Conventional Commit subjects when writing commit messages.
- Keep the subject concise, ideally 50 characters or fewer.
- Add a body only when the reason, risk, or behavior change is not obvious from the subject.
- For multiple hashes, mention shared themes and call out materially different changes.

## Useful Commands

Use these as needed:

```bash
git show --stat --patch <hash>
git log --stat --patch <hash1> <hash2>
git log --stat --patch <base>..<head>
git diff --cached
git diff
git status --short
```

For untracked files, inspect filenames with `git status --short` and read only the relevant files needed to describe the change.
