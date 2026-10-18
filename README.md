# CareLoop

A gamified, multi-page web prototype for CareLoop, an AI health companion (HackShift Round 1).
Single static file (`index.html`): no build step, no dependencies.

## Pages
Home, Story, Decoder (prescription upload), Vitals, Check-in, Coach, Trust, Roadmap, Sign in, Quests.

## Run locally
Open `index.html` in a browser.

## Deploy on GitHub Pages
1. Create a new repository and upload `index.html`, `README.md` and `.nojekyll`.
2. Go to Settings > Pages > Build and deployment.
3. Source: "Deploy from a branch", Branch: `main`, folder `/ (root)`. Save.
4. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

## What works outside Claude
- All pages, XP, levels, streaks, badges, vitals chart, Coach phone simulator, wellbeing and symptom check-ins, consent center.
- Progress is saved in the browser (localStorage). The sign-in is a demo: no password, nothing leaves the browser.

## What needs Claude
Reading a prescription photo and cross-checking doses use the Claude artifact runtime
(`claude.use("sample")`), which exists only when the page is opened inside Claude.
On GitHub Pages those two features fall back to the built-in sample prescription.
To make them work on a public site you need a small backend (for example a serverless function)
that holds an API key and calls a vision model; never put an API key in `index.html`.

## Disclaimer
Demo only. A support tool, not a diagnosis. Scale wording and cut-offs (PHQ, GAD, WHO-5, PSS-4)
must be verified against official sources and reviewed by clinicians before any real use.
