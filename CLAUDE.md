# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Personal academic website for Zisheng Zhang, built on the [al-folio](https://github.com/alshedivat/al-folio) Jekyll theme. Deployed to GitHub Pages at zishengz.github.io.

## Build & Serve Commands

```bash
# Install dependencies
bundle install

# Local development server (with latent semantic indexing)
bundle exec jekyll serve --lsi

# Build static site (output to _site/)
bundle exec jekyll build --lsi

# Docker alternative (serves on port 8080)
docker-compose up
```

Deployment is automatic via GitHub Actions (`.github/workflows/deploy.yml`) — pushing to `master` triggers a build that deploys to the `gh-pages` branch.

## Architecture

- **`_config.yml`** — Central configuration: site metadata, social links, scholar settings, plugin list, feature toggles. Most site-wide changes happen here.
- **`_bibliography/papers.bib`** — BibTeX file that auto-generates the publications page via `jekyll-scholar`. Custom bibtex keywords (`abbr`, `abstract`, `arxiv`, `pdf`, `code`, `selected`, etc.) control display buttons.
- **`_data/coauthors.yml`** — Co-author metadata (names + URLs) for auto-linking in publication entries. Keyed by last name with firstname variants.
- **`_data/cv.yml`** — Structured CV data rendered by the `cv` layout.
- **`_data/venues.yml`** — Maps publication abbreviations to venue links.
- **`_pages/`** — Top-level site pages (about, publications, CV, projects). Each uses YAML front matter to select a layout from `_layouts/`.
- **`_news/`** — Markdown files for news items shown on the homepage (controlled by `news_limit` in config).
- **`_projects/`** — Markdown files for project cards displayed on the projects page.
- **`_layouts/bib.html`** — Template controlling how each bibliography entry renders (buttons, badges, author highlighting).
- **`_plugins/`** — `external-posts.rb` (fetches external blog RSS) and `hideCustomBibtex.rb` (strips internal bibtex keywords from display).
- **`_sass/_themes.scss`** — Theme color variables (`--global-theme-color`).

## Key Conventions

- Publications are managed entirely through `_bibliography/papers.bib` — add/edit entries there, not as individual pages.
- Author self-identification for underlining is configured in `_config.yml` under `scholar:last_name` and `scholar:first_name`.
- News items are sorted by filename date prefix (e.g., `2024-04-12_Science_paper.md`).
- Static assets (PDFs, images) go in `assets/pdf/` and `assets/img/` respectively.
