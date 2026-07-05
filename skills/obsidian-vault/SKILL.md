---
name: obsidian-vault
description: Boot a session against an Obsidian vault so Claude works as a knowledge-base assistant — reading, querying, and updating notes in the vault's own conventions. Also scaffolds a fresh vault when none exists. Use when the user mentions their Obsidian vault, a personal knowledge base, "second brain," daily notes, or asks to capture, retrieve, link, or organize notes across sessions.
---

# Obsidian Vault Assistant

Connect a session to an Obsidian vault and act as its knowledge-base assistant. On first use, locate the vault and load enough of it to work fluently. If no vault exists, scaffold one.

## Locate the Vault

1. Use a path the user gives you. Otherwise check common locations: `~/Documents`, `~/Obsidian`, `~/vaults`, `~/Library/Mobile Documents/iCloud~md~obsidian/Documents` (macOS iCloud), and the current directory.
2. A vault is any directory containing a `.obsidian/` folder. Search for it before asking.
3. If several vaults match, list them and ask which to use. If none, offer to scaffold one (see below).

## Load Vault Context

Before answering or editing, build a working picture of the vault:

1. Read the index or map-of-content note if present (`index.md`, `home.md`, `MOC.md`, `_index.md`, or a note linked from `.obsidian/` workspace).
2. Read any conventions note (`README.md`, `conventions.md`, `.claude.md`, or a note describing how the vault is organized).
3. Scan the top-level folder layout and note the organizing scheme (PARA, Zettelkasten, topic folders, daily notes) rather than imposing one.
4. Inspect a few representative notes to learn the vault's frontmatter fields, tag style, and link format.

Report a one-line summary of what you found (structure, note count, conventions) so the user knows the session is oriented.

## Work in the Vault's Conventions

- Match the existing folder scheme, filename casing, frontmatter keys, and tag style. Detect; do not prescribe.
- Use `[[wikilinks]]` for internal links and keep them resolvable. Prefer linking new notes into an existing index or MOC so they are discoverable.
- Preserve YAML frontmatter and only add fields the vault already uses, unless the user asks for a new one.
- When capturing new knowledge, write atomic notes with a clear title, then link them — do not dump everything into one file.

## Reading and Retrieval

- Answer from the vault's actual contents, quoting note titles and paths so the user can open them.
- When a query spans notes, follow links and tags to gather context before synthesizing.
- Distinguish what the vault says from your own inference; flag gaps rather than inventing note content.

## Writing Back

- Confirm the target location and filename before creating or overwriting a note.
- For updates, edit in place and keep surrounding structure intact.
- Optionally log meaningful session outcomes into a daily note or the relevant MOC so knowledge compounds across sessions.

## Scaffold a New Vault

Only when no vault exists and the user wants one. Ask for a location and a preferred structure (default to PARA if unsure), then create:

```
<vault>/
  .obsidian/            (empty; Obsidian populates it on first open)
  index.md              top-level map of content
  conventions.md        how this vault is organized and how the assistant should use it
  Projects/
  Areas/
  Resources/
  Archive/
  Daily/
```

Seed `index.md` with links to each area and `conventions.md` with the frontmatter fields, tag style, and link rules to follow. Tell the user to open the folder in Obsidian to finish setup.

## Rules

- Detect and respect existing conventions before writing anything.
- Never modify `.obsidian/` config unless asked.
- Keep new notes atomic and linked, not orphaned.
- Cite note paths so the user can verify in Obsidian.
