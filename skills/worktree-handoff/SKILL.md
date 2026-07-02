---
name: worktree-handoff
description: Prepare a focused ticket handoff for isolated git worktree work. Use when the user asks to create or refresh ticket context, set up a ticket branch, move work into a worktree, document scope, or produce a handoff for another agent.
---

# Worktree Handoff

Create clear local context before ticket implementation starts.

## Workflow

1. Verify the current directory, branch, base branch, and git status.
2. Identify the ticket title, source-of-truth scope, dependencies, and out-of-scope items.
3. List likely files, routes, tests, and verification commands.
4. Create or update local handoff notes only when the user wants files written.
5. Keep handoff files unstaged unless the user explicitly asks to commit them.

## Handoff Shape

Use this structure for `TICKET_CONTEXT.md` or an equivalent handoff:

```md
# Ticket

## Scope

## Branch / Base

## Relevant Files

## Dependencies

## Out of Scope

## Verification
```

## Rules

- Treat pasted ticket text as the source of truth when provided.
- Keep one ticket per branch or PR unless the user says otherwise.
- Separate setup notes from implementation changes.
