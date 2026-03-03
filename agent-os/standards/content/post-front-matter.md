# Post Front Matter

## Required Fields

```yaml
layout: post
title: "Post Title"
date: YYYY-MM-DD
categories: [kebab-case, lowercase]
description: "One-sentence summary for listings and SEO."
```

## Optional Hero Image Fields

Use all four together or none:

```yaml
hero_image: assets/images/posts/<post-slug>/filename.png   # relative, no leading slash
image: https://kcdatasherpa.com/assets/images/posts/<post-slug>/filename.png  # absolute, for OG tags
hero_alt: "Describe the image for accessibility."
hero_caption: "Optional caption displayed below the image."
```

- `hero_image` — rendered in the post layout
- `image` — consumed by jekyll-seo-tag for Open Graph / social card previews; must be absolute URL
- `hero_alt` defaults to `page.title` if omitted, but always set it explicitly

## File Naming

`_posts/YYYY-MM-DD-post-title-as-kebab-case.md`

- Date prefix required by Jekyll
- Slug = title in lowercase, hyphens, no date repeated in slug
- Example: "Declarative Over Desperation" → `2026-02-24-declarative-over-desperation.md`
- Drafts live in `_drafts/` without a date prefix

## Image Asset Paths

Images for posts live at: `assets/images/posts/<post-slug>/`

- Folder name matches the post slug exactly (kebab-case, hyphens not underscores)
- No leading slash — paths are relative
- `hero_image` uses this relative path; `image` uses the full absolute URL

**Note:** `_drafts/post-template.md` had an outdated path (`/assets/img/`). Correct directory is `assets/images/`.
