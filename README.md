Gridiron Sidekick
An AI companion for a Yahoo college fantasy football league. Runs entirely in the browser — no backend, no login, no database.
Live site: `https://<your-username>.github.io/<repo-name>/` (fill in once GitHub Pages is on)
What it does
Roster — track your team, or paste text copied from your Yahoo roster page to have it parsed in automatically
This week's matchup — paste your Yahoo matchup page so every check below has real context, saved per week
Start/Sit — pick players you're deciding between, get a read backed by a live web search for current news and matchups
Waiver Wire — paste available players, or leave blank for this week's top pickups
Trade Analyzer — lay out both sides of a deal, get a fairness grade
History — a running log of every call made, by week
How it works
Single-page app (`index.html`) with no build step. Roster, matchup, and history data are saved in the browser's local storage, so they're private to whoever's using that browser and don't sync across devices.
Analysis calls go straight from the browser to Anthropic's API (`api.anthropic.com`) using Claude with web search enabled, so recommendations reflect current information rather than stale data baked into the app.
Files
File	Purpose
`index.html`	The app itself
`manifest.json`	Makes the app installable ("Add to Home Screen")
`sw.js`	Minimal service worker, required for installability
`icon-192.png`, `icon-512.png`	App icons
Setup
Upload all five files to this repo (root, not a subfolder).
Settings → Pages → Deploy from a branch → `main` / `/(root)` → Save.
Open the live URL on your phone in Chrome → menu → Add to Home Screen.
Notes
This is a personal tool, not a hosted product — data stays local to your browser and doesn't need an account.
No real-time Yahoo API connection (that would require OAuth and a backend). Yahoo data comes in via copy/paste instead.
