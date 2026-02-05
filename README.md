# KCDataSherpa

KCDataSherpa is a Jekyll site built on the `minima` theme and deployed to GitHub Pages.

**Project Structure**
- `_config.yml`: Site metadata (title, description, base URL), theme, and plugins.
- `_posts/`: Published articles. Filenames must follow `YYYY-MM-DD-title.md` (or `.markdown`).
- `_drafts/`: Unpublished articles; Jekyll will only render these with the `--drafts` flag.
- `_layouts/` and `_includes/`: Layout templates and shared partials.
- `assets/`: Images, icons, and other static assets.
- `index.markdown`, `about.markdown`, `404.html`: Top-level pages.
- `_site/`: Generated output from `jekyll build` or `jekyll serve` (do not edit by hand).
- `.github/workflows/`: CI and deployment workflows.

**Write a New Article**
1. Create a new file in `_posts/` using the naming pattern:

   ```text
   _posts/YYYY-MM-DD-your-title.md
   ```

2. Add front matter at the top of the file. Example (based on existing posts):

   ```yaml
   ---
   layout: post
   title: "Your Title Here"
   date: 2026-02-05
   categories: [operating-models, leadership]
   description: "Short summary for previews and SEO."
   hero_image: assets/images/posts/your-post/hero.png
   hero_alt: "Accessible description of the hero image."
   hero_caption: "Optional caption shown under the hero image."
   ---
   ```

3. Write the content in Markdown below the front matter.
4. Add any images under `assets/images/posts/<your-post>/` and reference them with the `hero_image` path above.

**Use the Post Template**
- The starter template lives at `_drafts/post-template.md`.
- Copy it to start a new draft or post:

  ```text
  _drafts/your-post-slug.md
  ```

  or

  ```text
  _posts/YYYY-MM-DD-your-post-slug.md
  ```

- Update the front matter fields (`title`, `date`, `categories`, `description`, `hero_*`) and replace the placeholder body.
- The template includes an image organization convention. Follow it for predictable asset paths.

**Write a Draft Article**
1. Create a draft in `_drafts/`:

   ```text
   _drafts/your-post-slug.md
   ```

2. Use the same front matter as published posts. (Drafts can omit the `date`, but including it helps when you publish.)
3. Preview drafts locally:

   ```bash
   bundle exec jekyll serve --drafts
   ```

4. Publish by moving the draft into `_posts/` and adding the `YYYY-MM-DD-` prefix to the filename.

**Local Development**
- Install dependencies:

  ```bash
  bundle install
  ```

- Run the site locally:

  ```bash
  bundle exec jekyll serve
  ```

- To preview drafts:

  ```bash
  bundle exec jekyll serve --drafts
  ```

**Deployment**
- Production deploys are handled by GitHub Actions.
- Any push to the `main` branch triggers `.github/workflows/jekyll.yml`, which builds the site and deploys to GitHub Pages.
- Pull requests run `.github/workflows/pr-checks.yml`, which builds the site and runs the Codex review action.

**Notes**
- The site’s public URL and base path live in `_config.yml` (`url` and `baseurl`).
- If you change `_config.yml`, restart `jekyll serve` to pick up those changes.
