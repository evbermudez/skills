# Claude Code Instructions

This repository is a portable skill library. Each skill lives in `skills/<skill-name>/` and the source of truth is its `SKILL.md`.

## Working With Skills

- Read the relevant `skills/<skill-name>/SKILL.md` before using or editing a skill.
- Keep skill folders lean: `SKILL.md`, optional `agents/openai.yaml`, and only the resource folders the skill needs.
- Put portfolio-facing descriptions in `README.md`, not inside individual skill folders.
- Preserve each skill's narrow scope. Add a new skill when a workflow has a different job.

## Editing Rules

- Use concise, imperative instructions in skill bodies.
- Keep frontmatter to `name` and `description`.
- Make descriptions trigger-friendly: include what the skill does and when to use it.
- Avoid adding generated process notes, changelogs, or installation guides inside skill folders.

## Verification

- After editing a skill, check its frontmatter and scan for template placeholders.
- If available, run the skill validator from the skill-creator tooling.
- If the validator cannot run because local dependencies are missing, state that clearly.
