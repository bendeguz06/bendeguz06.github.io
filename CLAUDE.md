# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

A personal academic portfolio site for Bendeguz Borbely-I., built with Jekyll and deployed to GitHub Pages at `https://bendeguz06.github.io/`. It uses the [`strata-academic`](https://github.com/yaoyao-liu/strata-academic) remote theme.

## Commands

```bash
# Serve locally (requires Ruby/Bundler)
bundle exec jekyll serve

# Build static site
bundle exec jekyll build

# Install dependencies
bundle install
```

The built site outputs to `_site/` — do not edit files there directly.

## Architecture

- **`_config.yml`** — all site-wide variables (title, links, avatar, social icons). This is the primary file to edit for profile metadata.
- **`index.md`** — the sole content page, rendered with `layout: homepage`. All sections (Interests, Projects, Competitions, etc.) live here as Markdown.
- **`_layouts/homepage.html`** — the single layout template. Pulls variables from `_config.yml` via `site.*` and renders `{{ content }}` from `index.md`. The sidebar (avatar, name, position, email) and footer icons are generated here.
- **`_sass/strata-academic.scss`** — custom SCSS overrides on top of the remote theme styles.
- **`assets/css/style.scss`** — entry point that imports `strata-academic`; compiled to `assets/css/style.css`.
- **`assets/`** — static files: CV PDF, images, favicon, the Obsidian vault graph (`vault_graph.html`), and vendored JS/CSS from the original Strata HTML5UP theme.

## Key conventions

- Site content is almost entirely in `index.md` and `_config.yml` — new sections go in `index.md`, new sidebar links/icons go in `_layouts/homepage.html` with a matching `_config.yml` key.
- The remote theme (`remote_theme: yaoyao-liu/strata-academic`) is fetched by GitHub Pages automatically; local `_layouts/` and `_sass/` files override theme defaults.
- `assets/original/` contains vendored Strata theme assets (jQuery, FontAwesome, etc.) — don't modify these.
