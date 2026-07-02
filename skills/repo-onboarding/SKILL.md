---
name: repo-onboarding
description: Inspect an unfamiliar repository and produce a practical onboarding guide for agentic coding work. Use when the user asks to understand a repo, map architecture, identify commands, document conventions, or prepare another agent to work safely in the codebase.
---

# Repo Onboarding

Map a repository into a practical working guide.

## Workflow

1. Start with `pwd`, `git status --short --branch`, and top-level files.
2. Identify the language, package manager, framework, entrypoints, and test commands.
3. Read README, package manifests, config files, and key source directories.
4. Capture conventions for edits, tests, formatting, environment, and deployment.
5. Write a concise guide that helps the next agent make safe changes.

## Output Format

```md
## Purpose

## Stack

## Structure

## Common Commands

## Development Conventions

## Testing

## Risks / Unknowns
```

## Rules

- Prefer evidence from files over assumptions.
- Note commands that were not run.
- Keep the guide operational, not marketing-oriented.
