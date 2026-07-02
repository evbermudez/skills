# Skills

A personal skill library for reusable Codex workflows. Each folder under `skills/` is an installable skill with a `SKILL.md` contract. This repo also serves as a portfolio of agent workflow design.

## Catalog

| Skill | Description | Usage | Status |
|---|---|---|---|
| `caveman-commit` | Generates terse Conventional Commit messages from staged, unstaged, or untracked local changes. | Use when you want only a commit message for current uncommitted work. | Draft |
| `commit-summarizer` | Summarizes explicit commit hashes, ranges, latest commits, staged changes, or uncommitted files. | Use for explaining commits, reviewing hashes, or drafting changelog-style notes. | Draft |
| `diff-risk-review` | Reviews diffs for regressions, missing tests, and packaging risk. | Use before committing or opening a PR when you want a reviewer-style risk pass. | Draft |
| `pr-summary-format` | Drafts structured PR descriptions from diffs and verification evidence. | Use when you need a copy-ready PR body. | Draft |
| `repo-onboarding` | Maps an unfamiliar repository into a practical working guide. | Use when starting work in a new codebase or preparing another agent. | Draft |
| `review-loop` | Turns code review feedback into focused fixes and verification notes. | Use when addressing reviewer comments or rerunning a review cycle. | Draft |
| `ticket-planner` | Converts rough notes into AI-ready ticket scope and acceptance criteria. | Use when planning implementation prompts, ticket cards, or split work. | Draft |
| `worktree-handoff` | Prepares ticket context for isolated worktree development. | Use when setting up or handing off one-ticket-per-branch work. | Draft |

## Skill Format

Each skill should include:

- `SKILL.md`: the agent-facing instructions and trigger description.
- `agents/openai.yaml`: optional UI metadata for skill lists.
- `scripts/`, `references/`, or `assets/`: only when the skill needs reusable resources.

Do not add extra documentation inside a skill folder unless the skill needs it at runtime. Put portfolio-facing descriptions and usage notes in this catalog instead.

## Agent Support

These skills are written as portable `SKILL.md` folders. Codex can use the skill folders directly, and Claude Code can use the project-level `CLAUDE.md` instructions to read the same skill contracts.
