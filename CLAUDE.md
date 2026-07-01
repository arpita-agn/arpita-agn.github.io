# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Personal academic/professional profile website for Arpita Ghosh, deployed as a GitHub Pages site at `arpita-agn.github.io`. Built with Jekyll, modeled after the [academicpages](https://github.com/academicpages/academicpages.github.io) template structure.

## Architecture

Jekyll-based multi-page site following this structure:

- **`_config.yml`** — Site-wide settings: author info (name, bio, social links), plugin list, collection defaults. All author data used in sidebar/profile is defined here.
- **`_data/navigation.yml`** — Top navigation bar links. Add/remove/reorder pages here.
- **`_layouts/`** — Template hierarchy: `default.html` (base shell with head, topbar, sidebar, footer) → `page.html` (adds section title wrapper).
- **`_includes/`** — Reusable components: `head.html`, `topbar.html` (nav from `_data/navigation.yml`), `sidebar.html` (profile card from `_config.yml` author data), `footer.html`.
- **`_pages/`** — Content pages as Markdown with HTML blocks. Each page sets `permalink` and `title` in frontmatter. The `about.md` page serves as homepage (`permalink: /`).
- **`assets/css/style.css`** — All styling. Uses CSS custom properties (`:root` variables) for theming. Responsive breakpoints at 1024px, 768px, and 480px.
- **`images/`** — Static images (profile photo).

Layout: sticky top navigation bar + fixed sidebar (profile card) + scrollable main content. On mobile (<=768px), sidebar stacks above content and nav collapses to hamburger menu.

## Development

Requires Ruby and Bundler:

```bash
bundle install
bundle exec jekyll serve
```

Site is served at `http://localhost:4000`. Changes to most files auto-reload; `_config.yml` changes require server restart.

## Deployment

Hosted via GitHub Pages from the `main` branch of `arpita-agn/arpita-agn.github.io`. Pushing to `main` triggers a Jekyll build and deployment automatically.

## Adding a New Page

1. Create `_pages/my-page.md` with frontmatter: `permalink: /my-page/`, `title: "My Page"`
2. Add an entry to `_data/navigation.yml`

## External Dependencies (CDN)

- Font Awesome 6.5.1 (icons)
- Academicons (academic icons)
- Google Fonts — Inter (typeface)
