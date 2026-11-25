---
name: save-note
description: File a note, decision or open question into the right page of the Obsidian vault. Use for /save-note or whenever something is worth remembering across sessions.
---

# Save note

Save into the vault (path in `AGENTS.md`; if it still says `FILL IN`, ask first) whatever the user typed after `save-note`.

1. **Find the project.** Search the vault for its hub note. No matching project? Copy the 4 files in `vault-template/Projects/Example Project/` into `<vault>/Projects/<New Name>/`, rename each file, replace `Example Project` with the new name inside them (frontmatter and `[[links]]`), and add a line for it in `00 Index.md`.
2. **Pick one note by type:** a decision → `Decisions` (dated line, with the why); an open question → `Open Questions`; a finding with a source → `Research`; status or next step → the hub. Never leave a loose `.md` file.
3. **Edit** that note, don't rewrite it, and set `updated:` in its frontmatter to today's date.
4. Reply in one line: which note changed.
