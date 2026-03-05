## Tech Stack

### Site Generator
- **Framework:** Jekyll (static site generator)
- **Language/Runtime:** Ruby 3.2
- **Package Manager:** Bundler
- **Theme:** Minima (~> 2.5)

### Hosting & Deployment
- **Hosting:** GitHub Pages
- **Custom Domain:** kcdatasherpa.com
- **CI/CD:** GitHub Actions
  - `jekyll.yml` — builds and deploys on push to `main`
  - `pr-checks.yml` — Jekyll build + Codex AI review on all PRs

### Plugins
- `jekyll-feed` — RSS feed at `/feed.xml`
- `github-pages` gem (~> 232) — GitHub Pages compatibility layer

### AI / Review
- **PR Review:** `openai/codex-action@v1` runs on every PR

### No Database / No Backend
Static site. No backend, database, API, or server-side runtime in production.
