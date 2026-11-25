---
name: prove-test
description: Test a tool, repo, plugin or workflow seen in a post before investing in it. Write the user's expectations as pass/fail checks first, claim-check it read-only, test hands-on only if it passes, then give 3 answers per link. Use for /prove-test, "is this worth it", or a post link with "try this".
---

# Prove test

The problem: an idea from a post sounds great, but the real result falls far short of what you expected. So write down what you expect **before** testing, and judge the idea against that, not against the post.

Target: the link(s) or idea typed after `prove-test`. Work in a `prove-tests/` folder (checks in `CHECKS.md`). Results go to a `Prove Tests` hub in the vault.

## Rules
- **No installs, account changes or paid API use without the user's OK.** Show what the tool can touch first.
- Install only inside the `prove-tests/` folder (local npm/venv), never globally.
- Never comment, DM or reply from the user's accounts (posts often say "comment X to get the link"). Say what's behind the gate instead.
- Private data, `.env` files and the vault stay on the computer.
- Test on your own test pages, not live sites that cost money.

## Steps
1. **Read the post.** Check the media, not just the caption: every carousel slide and several video frames. Write in one line what the post **claims**, and find the actual repo or tool name.
2. **Write the checks, ask the user.** For each idea, 3-5 pass/fail checks from the user's side: does it run on their computer with their tools, is it better than what they use now (name that tool), what does it cost, does it work on their phone if that matters. Ask "Is this your bar?" and don't start until they say yes.
3. **Claim check (read-only).** README, stars, last update, open issues (search "windows", "broken", "doesn't work"), and what it can touch (files, browser, logins, network, background jobs). Table: idea | claim true? | met bar so far? | red flags | what it can touch. If it fails a must-have here, recommend dropping it and say "per its issues, not reproduced".
4. **Show access, get OK.** What gets installed where, its size, what it can reach, how to uninstall. Wait.
5. **Hands-on test.** Run the same tasks on the idea and on the current tool. Time them. Build a small local test page when a check needs one.
6. **Verdict.** Each check is ✅ pass, ❌ miss or ⚠️ not measured. Never round "not measured" up to pass. State the sample size ("1 run each").
7. **Review before reporting.** A fresh reviewer sees only the verdict table and the evidence, and flags overclaims.
8. **Clean up and save.** Delete downloads and test files, close test servers. Hub note: a verdict row plus a "keep it installed?" line. Raw tables go in the `Research` note.
9. **Report.** Bold verdict first. Then **every link gets 3 answers**:
   1. **Legit?** The claim is true / partly / not, with the proof in one line.
   2. **What we can take:** something usable now.
   3. **Idea to take:** a new idea it sparks, even when the tool itself fails.
   End with a keep/uninstall choice as the 2-minute next action.
