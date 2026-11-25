---
name: research-pipeline
description: Deep research with the tools the user names (never silent built-in web search), parallel angles, a verifier, a vault save and an optional share page. Use for /research-pipeline, deep research, or researching a market, problem or idea.
---

# Research pipeline

The topic is whatever the user typed after `research-pipeline`. Follow the steps in order. `AGENTS.md` rules still apply.

## 1. Confirm first
Ask in one go:
- **Output:** webpage / PDF / webpage + 2-page PDF / vault note only.
- **Audience:** just me / friends / a pitch.
- **Depth:** deep (default: rounds repeat until two come back empty) or light (3 angles, one round).
Then say back in one line what you'll make, for whom, in what format. Wait for OK.

## 2. Check the vault
Search the vault for the topic. Read the hub and its `Research` note. Tell every agent what is already known so they don't redo it.

## 3. Tool check before launching
- Test each tool the user named with one tiny request (open the browser, run one search, call the Reddit tool once).
- If a site needs sign-in to work properly, tell the user; they sign in themselves.
- Show a short table: which tools work, which lanes are dropped. Then launch.

## 4. Research agents (parallel if your tool supports it, otherwise one after another)
Angles (light run = first three):
1. Competitors and existing solutions
2. User pain points, in users' own words (forums, Reddit, social posts)
3. Laws and rules in the user's country (from `AGENTS.md`)
4. Market size and pricing
5. Technical feasibility on the user's limits

Also add, every deep run:
- **Social search** in the languages the users actually speak.
- **Reviews and footprints:** app store pages, business directory entries, first Wayback Machine capture.
- After each round, a critic lists what is still missing; the next round chases it.

Paste this block into **every** agent prompt:

> Tools: use only `<the tools the user named>`. Do NOT use built-in web search or web fetch. If a tool fails, stop and report the exact error. Do not switch tools yourself.
> A search engine or AI answer only finds sources; it is not proof. Open the page it cites and read the claim there.
> Every claim needs the URL of the page you actually opened. Mark anything you couldn't open as "not checked".
> Return: findings as bullets with URLs, then "what I could not find".

If an agent reports a tool failure: stop, tell the user which tool failed and why, and ask before switching.

## 5. Verifier
One agent gets all findings and cross-checks the key claims (numbers, laws, prices, competitor facts). A claim with only one source is marked **unverified**.

## 6. Verdict
- A **go / no-go / needs-more** verdict per idea, in bold.
- A top 5, each item 2-3 sentences: what it is, why it matters, the next step. Never bare titles.

## 7. Second opinion
Before saving, have a fresh reviewer check the verdict, top 5 and claim table: a sub-agent if your tool has them, otherwise give the user a copy-paste prompt for a new chat (or another AI). Fix weak claims and wrong numbers. Say in one line what changed.

## 8. Save to the vault
- Topic belongs to a project: raw findings with URLs go into `Projects/<Project>/<Project> Research.md`, linked from the hub. Log the verdict in `Decisions` and gaps in `Open Questions`.
- Not a project yet: one note `Reference/<Topic> <Month YYYY>.md` (verdict, top 5, claim table, raw findings, sources, open questions) plus a line in `00 Index.md`.

## 9. Share page (only if step 1 chose one)
- One self-contained HTML file, phone-first. Check it at 390px wide before showing it.
- PDF: a 2-page summary printed from its own HTML. Open it and check nothing is cut off.
- Show the user the local file first. **Ask before publishing.**

## 10. Report
Verdict first, then the top 5, then one next action under 2 minutes. List any `AGENTS.md` rule you couldn't follow.
