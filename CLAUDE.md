# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a portfolio website with an integrated blog, built using [Zola](https://www.getzola.org/) static site generator with the [Radion](https://github.com/micahkepe/radion) theme.

## Key Commands

### Development
```bash
zola serve
```
Site runs at `http://127.0.0.1:1111`

### Building
```bash
zola build
```
Output goes to `public/` directory.

### Testing Syntax Highlighting Changes
If syntax highlighting themes are modified in `config.toml`:
```bash
# Delete old generated files
rm -rf static/syntax

# Rebuild to regenerate CSS files
zola build
```

## Architecture

### Content Organization

**Homepage (`content/_index.md`)**: Portfolio content including About, Education, Projects, Experience, Skills, and Contact sections. Uses Markdown with inline HTML for styling.

**Blog posts (`content/blog/*.md`)**: Individual blog posts with frontmatter. The blog section uses `content/blog/_index.md` for configuration.

**Taxonomies**: Posts are organized by `categories` and `tags` taxonomies (configured in `config.toml`).

### Template System

The site uses Zola's Tera templating engine with the following template hierarchy:

- `themes/radion/templates/_base.html`: Base template with common HTML structure, meta tags, and theme switching logic
- `templates/index.html`: **Custom override** for homepage (portfolio layout)
- `templates/section.html`: **Custom override** for blog listing page
- Theme templates in `themes/radion/templates/`: All other pages (individual posts, category/tag pages, etc.)

**Important**: Custom templates in `templates/` override theme templates. Changes to portfolio or blog listing layouts should be made to the custom templates, not the theme files.

### Theme System

The Radion theme supports light/dark mode switching with the following components:

1. **Theme initialization** (`themes/radion/static/js/init-theme.js`): Runs in `<head>` to prevent flash of wrong theme. Reads from localStorage and applies theme class to `<html>` and `<body>`.

2. **Theme toggling** (`themes/radion/static/js/toggle-theme.js`): Handles theme switching including:
   - Swapping light/dark classes on DOM elements
   - Toggling syntax highlighting stylesheets via `disabled` property
   - Updating Giscus comments theme (if enabled)
   - Updating sun/moon icons

3. **Syntax highlighting themes**: Configured in `config.toml` via `highlight_themes_css`:
   - `syntax/syntax-theme-dark.css`: Applied when dark mode is active (currently Catppuccin Mocha)
   - `syntax/syntax-theme-light.css`: Applied when light mode is active (currently Catppuccin Latte)

   Both stylesheets are **always loaded** in `_base.html`, but the JavaScript toggles the `disabled` property to show only the active theme.

### Static Assets

- `static/`: User assets (profile pictures, etc.)
- `themes/radion/static/`: Theme assets (JavaScript, syntax CSS, etc.)
- During build, both are copied to `public/`

### Sass Compilation

Theme styles are in `themes/radion/sass/`:
- `site.scss`: Main entry point
- `_theme.scss`: Theme variables and base styles
- `parts/`: Component-specific styles (code blocks, TOC, etc.)

Zola automatically compiles Sass during build when `compile_sass = true` in config.

## Deployment

Automated deployment via GitHub Actions (`.github/workflows/deploy.yml`):
- Triggers on push to `main` branch
- Uses Zola 0.21.0
- Builds and deploys to GitHub Pages
- Site URL: `https://obrown426.github.io`

## Configuration

Main configuration is in `config.toml`:

- **Base settings**: `base_url`, `title`, `description`, `theme = "radion"`
- **Markdown**: Syntax highlighting with class-based CSS for CSP compliance
- **Taxonomies**: Categories and tags with RSS feeds
- **Theme options** (under `[extra]`):
  - `theme = "toggle"`: Allows user to toggle light/dark mode
  - `codeblock = true`: Enhanced code blocks with clipboard and language tags
  - `enable_search = true`: Search functionality
  - `radion_menu`: Navigation menu items

## Common Tasks

### Adding a New Blog Post

Create file in `content/blog/` with frontmatter:

```markdown
+++
title = "Post Title"
date = 2025-12-15
description = "Brief description"

[taxonomies]
categories = ["category-name"]
tags = ["tag1", "tag2"]

[extra]
toc = true  # Optional: enable table of contents
+++

Post content...

<!-- more -->

Extended content after summary...
```

### Changing Syntax Highlighting Themes

1. Edit `config.toml` `highlight_themes_css` section with desired themes from [Zola docs](https://www.getzola.org/documentation/getting-started/configuration/#syntax-highlighting)
2. Delete `static/syntax/` directory
3. Run `zola build` to regenerate CSS files

### Updating Portfolio Content

Edit `content/_index.md` - this file contains all portfolio sections (About, Education, Projects, etc.).
