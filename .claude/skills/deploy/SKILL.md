# Deploy to GitHub Pages

Use this skill when the user asks to deploy, publish, or make the site live.

## Steps

1. **Check environment first** — Run `gh auth status` and check branch protections before attempting any push.
2. **Never push to main** — This repo has branch protection on main. Use GitHub Actions with `actions/deploy-pages` instead.
3. **Verify the workflow exists** — Ensure `.github/workflows/deploy.yml` is present and valid.
4. **Commit and push to the current feature branch** — The workflow triggers on push.
5. **If GitHub Actions deployment fails**, provide manual instructions:
   - Go to repo Settings > Pages
   - Set Source to "GitHub Actions"
   - Re-run the workflow from the Actions tab

## Fallback strategies (try in order)

1. GitHub Actions with `actions/deploy-pages` (preferred)
2. Create orphan `gh-pages` branch: `git checkout --orphan gh-pages`
3. Open a PR to main and instruct user to merge
4. Suggest Netlify/Vercel as alternative

## Rules

- Do NOT retry a failed approach more than once — pivot immediately
- Do NOT attempt `git push` to `main`
- Always validate YAML syntax before committing workflow files
