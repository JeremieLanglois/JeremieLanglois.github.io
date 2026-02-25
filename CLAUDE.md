# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Hugo-based academic portfolio site for Jérémie Langlois, deployed to GitHub Pages at jeremielanglois.com.

## Build & Development Commands

```bash
hugo server              # Local dev server with live reload
hugo --minify            # Production build (outputs to ./public)
hugo new <section>/file.md  # Create new content page
```

Hugo extended v0.156.0+ is required (no npm/node dependencies).

## Architecture

- **Theme**: "minimal" (by calintat) installed as a Git submodule at `themes/minimal/`. Checkout requires `--recurse-submodules`.
- **Content**: Markdown files with TOML frontmatter in `content/` — three pages: home (`_index.md`), research, and CV.
- **Layouts**: No custom layouts; all rendering uses the theme's templates (`themes/minimal/layouts/`).
- **Config**: `hugo.toml` — sets base URL, theme, menu items, accent color, Google Font (Alegreya), and enables unsafe HTML in Goldmark.
- **Static assets**: `static/CNAME` (GitHub Pages domain) and `static/headshot.png`.

## Deployment

GitHub Actions (`.github/workflows/hugo_deploy.yml`) auto-deploys on push to `main`: builds with `hugo --minify` and publishes to GitHub Pages.
