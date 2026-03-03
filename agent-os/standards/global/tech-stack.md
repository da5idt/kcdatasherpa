# Tech Stack

## Framework & Runtime
- **Site Generator:** Jekyll (via `github-pages` gem ~232)
- **Language/Runtime:** Ruby 3.2
- **Package Manager:** Bundler
- **Local dev:** `bundle exec jekyll serve`

## Theme & Frontend
- **Theme:** Minima ~2.5
- **CSS:** Custom overrides in `assets/css/custom.css`
- **Templating:** Liquid (Jekyll built-in)
- **JavaScript:** None

## Jekyll Plugins
- **jekyll-feed** ~0.12 — generates `feed.xml` (Atom)
- **jekyll-seo-tag** — Open Graph, Twitter card, and meta tags (included via github-pages gem)

## Hosting & Deployment
- **Hosting:** GitHub Pages with custom domain `kcdatasherpa.com` (CNAME)
- **Deploys on:** push to `main` branch

## CI/CD (GitHub Actions)
- **`jekyll.yml`** — builds and deploys to GitHub Pages on merge to main
- **`pr-checks.yml`** — runs on PRs to main:
  - Jekyll build check
  - OpenAI Codex PR review (`openai/codex-action@v1`)
