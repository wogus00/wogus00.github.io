# wogus00.github.io

A lightweight personal website and multilingual Markdown blog for GitHub Pages.

## Structure

- `index.html`: homepage composition and page metadata
- `_layouts/portfolio.html`: shared homepage document shell
- `_includes/site-header.html`: primary navigation
- `_includes/site-footer.html`: homepage footer
- `_includes/sections/`: one file per homepage section
- `assets/css/styles.css`: shared responsive styles
- `blog/en/_posts/`: English Markdown posts
- `blog/ko/_posts/`: Korean Markdown posts
- `_layouts/post.html`: shared blog post layout

To edit homepage content, open the matching file:

```text
_includes/sections/
├── home.html
├── education.html
├── experience.html
├── projects.html
└── blog.html
```

## Writing a post

Create a Markdown file named `YYYY-MM-DD-post-slug.md` in the appropriate
language folder. For example:

```text
blog/en/_posts/2026-06-09-my-first-post.md
```

Start the file with YAML front matter:

```markdown
---
title: "My First Post"
date: 2026-06-09
description: "A short summary shown on the blog index."
translation_key: my-first-post
tags:
  - statistics
  - research
---

Write the post here using Markdown.
```

For a Korean translation, create a file under `blog/ko/_posts/` and use the
same `translation_key`. The language switcher links directly between matching
translations. A post does not need to have a translation.

## Local preview

The blog uses Jekyll, so a plain Python static server will not render Markdown
posts. Install the dependencies once:

```sh
bundle install
```

Then start the local site:

```sh
bundle exec jekyll serve
```

Open `http://localhost:4000`.

## Deployment

The repository is named `wogus00.github.io`. Pushing to `main` triggers the
GitHub Actions workflow in `.github/workflows/pages.yml`, which builds the
Jekyll site and deploys it to GitHub Pages.
