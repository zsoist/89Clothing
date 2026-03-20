# 89Clothing / 8998 Project

## General Rules

- When a tool or approach fails twice, STOP. Explain the blocker and suggest 2-3 alternatives instead of retrying.
- If any git or gh command fails, diagnose the root cause before attempting a fix.
- Do not brute-force solutions with repeated shell commands.

## Deployment

- The `main` branch has protection rules. Do NOT push directly to main.
- Use GitHub Actions (`actions/deploy-pages`) for GitHub Pages deployment.
- The deployment workflow is at `.github/workflows/deploy.yml`.
- If GitHub Pages isn't working, check that Pages source is set to "GitHub Actions" in repo Settings.
- Fallback order: GitHub Actions > gh-pages branch > PR to main > Netlify/Vercel.

## GitHub / Git

- Before using `gh` CLI, verify auth with `gh auth status`.
- Check repository permissions before attempting pushes.
- If API access fails, provide manual steps the user can follow instead of retrying.

## Tech Stack

- Single-page HTML/CSS/JS site (no build step)
- Google Fonts CDN (Montserrat)
- Language: Spanish
