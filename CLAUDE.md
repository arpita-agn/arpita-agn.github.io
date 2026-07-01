# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal academic/professional profile website for Arpita Ghosh, deployed as a GitHub Pages site at `arpita-agn.github.io`. Built with Jekyll using the [academicpages](https://github.com/academicpages/academicpages.github.io) theme (based on Minimal Mistakes).

## Architecture

- **`_config.yml`** — Site-wide settings: author info (name, bio, social links, avatar), plugins, collection defaults. All sidebar profile data is defined here.
- **`_data/navigation.yml`** — Top navigation bar links. Add/remove/reorder pages here.
- **`_layouts/`** — Template hierarchy: `compress.html` → `default.html` (base shell) → `single.html` / `archive.html` (page types).
- **`_includes/`** — Reusable components: `author-profile.html` (sidebar), `masthead.html` (nav), `head.html`, `footer.html`, `seo.html`.
- **`_pages/`** — Content pages as Markdown. Each sets `permalink`, `title`, and `layout: archive` in frontmatter. `about.md` serves as homepage (`permalink: /`).
- **`_sass/`** — SCSS partials compiled via `assets/css/main.scss`. Theme variables in `_sass/_variables.scss`.
- **`assets/`** — Compiled CSS, JS (main.min.js), webfonts (Font Awesome), academicon fonts.
- **`images/`** — Static images (profile photo referenced as `author.avatar` in `_config.yml`).

## Development

```bash
bundle install --path vendor/bundle
bundle exec jekyll serve
```

Site served at `http://localhost:4000`. Changes to most files auto-reload; `_config.yml` changes require server restart.

## Deployment

Hosted via GitHub Pages from `main` branch of `arpita-agn/arpita-agn.github.io`. Push to `main` triggers automatic Jekyll build and deploy.

## Adding a New Page

1. Create `_pages/my-page.md` with frontmatter: `layout: archive`, `permalink: /my-page/`, `title: "My Page"`, `author_profile: true`
2. Add entry to `_data/navigation.yml`

## Customization Notes

- LeetCode and Codeforces links were added to `_includes/author-profile.html` (not in the upstream theme). Configured via `author.leetcode` and `author.codeforces` in `_config.yml`.
- Theme colors/fonts can be changed in `_sass/_variables.scss`.
