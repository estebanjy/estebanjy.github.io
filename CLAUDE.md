# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Personal portfolio/GitHub Pages site for Juan E. Yurquina at `jyurquina.com`. Built with Jekyll — GitHub Pages builds and deploys automatically on push to `master`.

## Local development

Requires Ruby >= 3.2. Install dependencies and serve locally:

```bash
bundle install
bundle exec jekyll serve
```

The site is then available at `http://localhost:4000`.

## Writing a blog post

Create a file in `_posts/` named `YYYY-MM-DD-slug.md` with this front matter:

```markdown
---
layout: post
title: "Post Title"
date: YYYY-MM-DD
description: "One-line summary shown in the blog index."
---

Post content here in Markdown.
```

## Architecture

- `_layouts/default.html` — site-wide shell (header, nav, footer); all pages use this
- `_layouts/post.html` — wraps `default.html`, adds post title, date, and back link
- `_config.yml` — Jekyll config; `permalink` is set to `/blog/:year/:month/:day/:title/`
- `index.html` — home page (bio, projects, skills); uses Jekyll front matter + `default` layout
- `blog/index.html` — blog listing; loops over `site.posts` automatically
- `_posts/` — one `.md` file per post
- `style.css` — all styles; blog-specific classes are `.post-container`, `.post-list`, `.post-date`, `.post-content`
- `images/` — static assets; `cansat/` subdirectory for project photos

## Conventions

- Page layout uses HTML tables for main content columns (intentional, matches academic personal-page style)
- Inline styles coexist with `style.css` — avoid consolidating them unless specifically asked
- Page language is `es` but content is English
