---
name: ticket-planner
description: Turn rough product, bug, or engineering notes into AI-ready ticket scope. Use when the user asks for ticket text, implementation prompts, acceptance criteria, likely files, dependencies, sequencing, or a concise plan another coding agent can execute.
---

# Ticket Planner

Convert rough intent into implementable ticket scope.

## Workflow

1. Extract the user-visible problem and desired outcome.
2. Separate must-have scope from nice-to-have or adjacent work.
3. Identify likely files, modules, routes, data models, tests, and dependencies.
4. Write acceptance criteria that can be verified.
5. Call out sequencing when one ticket blocks another.

## Output Format

Use this shape unless the user asks for a shorter version:

```md
## Title

## Description

## Scope

## Acceptance Criteria

## Likely Files

## Verification

## Dependencies / Notes
```

## Rules

- Keep tickets small enough for one PR when possible.
- Avoid vague acceptance criteria like "works correctly."
- Preserve the user's product framing and terminology.
- Mark assumptions explicitly.
