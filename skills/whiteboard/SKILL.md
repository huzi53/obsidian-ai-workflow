---
name: whiteboard
description: Plan a multi-step project on a board, split it into phases, tag each phase SOLO or TEAM, and run TEAM phases as parallel agents only after the user's OK. Use for /whiteboard or a project too big for one session.
---

# Whiteboard

The project is whatever the user typed after `whiteboard`. Follow the steps in order.

## 1. Gather
- Search the vault for the project. Read its hub note plus its `Research` note, so no team repeats finished research.
- Find the next real step in the hub (open questions, "next session"). Anything the user hasn't decided yet becomes **Phase 1: a SOLO decision gate**. No later phase may assume an answer they haven't given.

## 2. Split into phases
- 3 to 6 phases. Each phase gets a goal (one line), a "Done when" test, and a tag.
- **Tag TEAM only if** the phase splits into 3+ pieces that don't need each other (sources, sites, files, cases), or is bigger than one session. **Everything else is SOLO.** One agent working step by step beats a team on chained work; teams pay off for fan-out.
- Anything that sends, posts or pays is SOLO and done by the user.

## 3. Draw it
- Draw the plan as an Obsidian canvas: `Projects/<Project>/<Project> Board.canvas` (JSON Canvas format: text nodes plus edges). If your tool can't write files, draw it as a table in chat.
- If the board already has a "Phase plan" section, update it in place. Never draw a second plan.
- Layout: one row of phase blocks, left to right, arrows between. Each block: `**Phase N · SOLO**` or `**Phase N · TEAM (k agents)**`, the goal, "Done when". Under each TEAM phase, a box listing its agents.
- Link the board from the hub note.

## 4. Run the phases
- **SOLO phases:** do them one at a time. When a phase's "Done when" is the user's decision, stop and ask before the next phase.
- **Tool check:** before a TEAM phase, confirm every agent can reach what its piece needs. If not, make the phase SOLO.
- **TEAM phases, gate first.** Show this card and wait:
  1. **Goal:** what this team finds or makes.
  2. **For + format:** who sees it, the exact output.
  3. **Tools:** named per agent. Never built-in web search without asking.
  4. **Team:** the agents and what each one does.
  One OK covers one team only.
- **Running a team:** use your tool's way to run parallel agents (sub-agents, background tasks, or several chats). No sub-agent support? Run the pieces one after another yourself.
  - The main session merges and checks the workers' output.
  - Every agent prompt names its tools. Only one agent at a time drives a shared browser.
  - First team ever: start small, 2-3 agents.

## 5. Save
- Hub note: change only the lines that changed. Add the phase plan (one line per phase with its tag) and a `Decisions` or `Open Questions` entry.
- Board: mark finished phases ✅.
- Raw team output goes into the project's `Research` note, never a loose file.
