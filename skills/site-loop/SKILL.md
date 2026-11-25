---
name: site-loop
description: Score-and-fix loop for a website. Independent critics score it, a browser checks phone and desktop, fixes are applied in small batches, repeat until every score is 8.0+ or 6 rounds. Add "ship" to deploy when it passes. Use for /site-loop or polishing a site before sharing.
---

# Site loop

The target is the folder typed after `site-loop`. If the word **`ship`** follows it, a passing loop also deploys (see "When done").

Stop when **every critic scores 8.0+, tests pass and the browser check is clean**, or after **6 rounds**.

## Before round 1
- Read the project's hub note for style decisions already made. Don't undo them.
- In a git repo, commit the starting state so every round has an undo point.
- Never overwrite config files (`.env`, deploy configs, `settings.json`); merge into them.
- Read `CHECKS.md` in the site folder. If there isn't one, write 5-10 pass/fail checks first.
- Start the site locally and note its local URL.

## Each round
1. **Tests.** Write or extend small tests for any money or calculation logic (totals, splits, rounding). Run them.
2. **Critics.** Five reviewers, each seeing only the folder and the URL, never each other's opinion. Use parallel sub-agents if your tool has them. If not, review one lens at a time yourself, judging only the files and screenshots (not your build notes), and say in the report the critics weren't independent. Each returns a score out of 10 and a ranked fix list with file and line:
   - Visual design
   - Mobile UX (390px wide)
   - Legal and privacy rules for the user's country (from `AGENTS.md`)
   - Copy clarity
   - AI slop (purple gradients, glows, emoji labels, generic copy, uneven spacing)
   The design and mobile critics also get the **design rules** below.
3. **Browser check.** Screenshot every page at 390px and 1440px. Look for layout breaks, sideways scroll, tap targets under 44px, things covering buttons, and console errors. No browser tool? Ask the user before installing a local headless browser (for example Playwright in the project folder). If they say no, mark it **⚠️ browser not checked**: the loop can still finish, but `ship` won't deploy.
4. **Fix in small batches.** Targeted edits, never bulk find-and-replace. Search for a class name before adding it, to avoid clashes. After each batch, re-test the exact area, then rerun the tests and `CHECKS.md`. A batch that breaks something that passed before gets reverted and tried another way.
5. **Log.** Append the round to `ITERATIONS.md` in the site folder: scores before and after, what changed. Commit locally.

## Design rules
1. UI animations under 300ms, ease in-out, never linear. The more often something is used, the less it animates.
2. Every tap shows feedback within 400ms.
3. Tap targets at least 44px.
4. Nested rounded corners: inner radius = outer radius minus padding.
5. Borders use alpha colours (`rgb(0 0 0 / 0.12)`), not solid hex.
6. Palettes in OKLCH; gradients `in oklch` so the middle doesn't go grey.
7. Full-height sections use `100dvh`, with `100vh` the line before it as a fallback.
8. Dark mode shows depth with lighter surfaces, not shadows.
9. Scroll reveals animate each item as it enters, not a whole group at once.
10. The page still reads correctly with JavaScript off and with reduced motion.
11. If the user gave a reference, pull its colours, fonts and spacing first and judge against them.

If the AI-slop score is below 6, tell the user straight away in one bold line, with the top 3 signs, and keep looping.

## When done
- Report: any slop warning first, then a score table, what was fixed, and what is still below 8.0 and why.
- Save the score history and open weak spots to the project's `Decisions` note.
- **Without `ship`: don't deploy or push.** Ask first.
- **With `ship`:** deploy only if every critic is 8.0+ and all checks pass, then follow `skills/ship`. Never push to git without asking.
