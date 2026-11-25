---
name: ship
description: Test, secret-scan and deploy only the build/public folder of a site, check it live at phone width, commit locally and update the vault. Use for /ship when a site is ready to go live.
---

# Ship

The project folder is whatever the user typed after `ship`.

1. **Test.** Run its tests and every line of its `CHECKS.md`. If any fail, stop and show the first failure. Money or cost logic with no tests: stop and say so. No `CHECKS.md`: write one (5-10 checks), run it, and show the user before deploying.
2. **Find the build/public folder** (from the deploy config or the project's hub note). Deploy only that folder, never the project root, never `.env`.
3. **Secret scan** that folder first. Search for `sk-[A-Za-z0-9_-]{20,}|ghp_[A-Za-z0-9]{20,}|github_pat_|AKIA[A-Z0-9]{16}|BEGIN .*PRIVATE KEY` and long key-like values (20+ characters) next to `api_key`/`token`, plus any `.env` file. In a git repo, also check that `git ls-files` lists no `.env`. Any hit: stop and show it.
4. **Deploy** with the user's host (Cloudflare Pages, Netlify, Vercel, GitHub Pages...). Ask first if this is the first deploy of this project.
5. **Live check:** open the live URL at 390px wide and confirm it loads with no console errors. No browser tool? Ask the user to open it on their phone and confirm.
6. **Commit locally** with a short message. Never push without asking.
7. **Update the hub note** (edit only changed lines): live URL, date shipped, what changed, anything still open.
8. **Reply:** live URL, test result, commit hash, note updated.
