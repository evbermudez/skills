---
name: caveman-commit
description: Draft an ultra-concise Conventional Commit message from unstaged, staged, untracked, or otherwise uncommitted git changes. Use when the user asks for a commit message, says "write a commit", "commit message", "/commit", or invokes caveman commit for current local changes.
---

# Caveman Commit

Generate one terse commit message from the repository's uncommitted changes.

## Source Rules

1. Inspect `git status --short` first.
2. Prefer staged changes with `git diff --cached` when any files are staged.
3. If nothing is staged, inspect unstaged changes with `git diff`.
4. For untracked files, read only the relevant file contents needed to understand the change.
5. If there are no uncommitted changes, say there is no diff to summarize.

## Message Rules

- Output only the commit message unless the user asks for explanation.
- Use Conventional Commits: `<type>(<scope>): <imperative summary>`.
- Keep the subject terse, ideally 50 characters or fewer.
- Use imperative mood: `add`, `fix`, `remove`, `update`.
- Include a body only when the why is not obvious, the change is risky, or the change is breaking.
- Do not mention files unless the file name is the clearest scope.
- Do not add AI attribution.

## Types

Use the smallest accurate type:

- `feat`: user-facing capability
- `fix`: bug fix
- `docs`: documentation only
- `test`: tests only
- `refactor`: behavior-preserving code restructure
- `style`: formatting only
- `chore`: maintenance, config, metadata, or repo setup
- `build`: build system or dependency changes
- `ci`: CI configuration

## Examples

```text
feat(auth): add session refresh guard
```

```text
docs: add skill catalog
```

```text
fix(api): preserve tenant scope in exports

Exports were falling back to the platform connection when queued.
```
