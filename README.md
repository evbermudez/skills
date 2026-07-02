# Skills

A personal skill library for reusable Codex workflows. Each folder under `skills/` is an installable skill with a `SKILL.md` contract. This repo also serves as a portfolio of agent workflow design.

## Catalog

| Skill | Description | Usage | Status |
|---|---|---|---|
| `commit-summarizer` | Summarizes explicit commit hashes, ranges, latest commits, staged changes, or uncommitted files. | Use for commit messages, commit summaries, changelog notes, or reviewing one or more hashes. | Draft |

## Skill Format

Each skill should include:

- `SKILL.md`: the agent-facing instructions and trigger description.
- `agents/openai.yaml`: optional UI metadata for skill lists.
- `scripts/`, `references/`, or `assets/`: only when the skill needs reusable resources.

Do not add extra documentation inside a skill folder unless the skill needs it at runtime. Put portfolio-facing descriptions and usage notes in this catalog instead.
