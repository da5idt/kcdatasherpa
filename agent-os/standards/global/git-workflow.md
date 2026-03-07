# Git Workflow

## Branch Naming

- **AI-generated branches:** `claude/<description>` (set automatically by agents)
- **Manual branches:** kebab-case, descriptive, no type prefix
  - `add-data-quality-post`
  - `fix-feed-image-path`
  - `update-tech-stack-standards`

## PR Workflow

All changes to `main` require a PR. Direct pushes to `main` are blocked.

**Required checks (must pass before merging):**
1. Jekyll build — confirms the site builds without errors
2. Claude Code review — automated PR review via `anthropics/claude-code-action`

No human review required; passing checks is sufficient to merge.

## Draft-to-Post Publishing

1. Write content in `_drafts/` — no date prefix on filename
2. Before publishing, confirm:
   - Hero image assets are in place at `assets/images/posts/<slug>/` (if using one)
   - `description` front matter is accurate and tight
   - `categories` are correct
3. Move file to `_posts/YYYY-MM-DD-slug.md` with today's date
4. Open a PR — site deploys automatically on merge to main
