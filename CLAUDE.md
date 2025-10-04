# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo static site for Orthodox Christianity and theology discussions. The site uses the Hugo PaperMod theme (as a git submodule) and is designed for deployment via GitHub Pages.

**Live Site:** https://orthodoxnobody.com/

## Essential Commands

### Development
```bash
# Start local development server
hugo server

# Start with drafts and future posts visible
hugo server --buildDrafts --buildFuture

# Check Hugo version (requires Extended v0.150.0+)
hugo version
```

### Content Creation
```bash
# Create new blog post
hugo new posts/post-name.md

# Posts go in: content/posts/
# Pages go in: content/
```

### Building
```bash
# Production build (outputs to public/)
hugo --minify

# Build with detailed template metrics
hugo --templateMetrics

# Clear Hugo cache if needed
hugo --gc
```

### Theme Management
```bash
# Initialize/update the PaperMod theme submodule
git submodule update --init --recursive
```

## Architecture

### Directory Structure
- **content/posts/** - Blog posts in Markdown
- **content/** - Top-level pages (about.md, connect.md, archives.md, search.md)
- **layouts/partials/** - Custom HTML partials that override/extend theme
- **layouts/shortcodes/** - Custom Hugo shortcodes for content
- **assets/css/extended/** - Custom CSS that extends the theme
- **static/** - Static assets (images, files) served at site root
- **themes/hugo-PaperMod/** - Git submodule (DO NOT edit directly)
- **hugo.yaml** - Main site configuration

### Key Customizations

**Custom Shortcode:** `layouts/shortcodes/hero-quote.html`
- Creates styled quote blocks with optional author attribution
- Usage in content: `{{</* hero-quote author="Name" */>}}Quote text{{</* /hero-quote */>}}`

**Custom Fonts:** `layouts/partials/extend_head.html`
- Atkinson Hyperlegible (body text) - accessibility-focused
- Piazzolla (headings/hero elements) - serif display font
- Loaded from Google Fonts

**Custom Styling:** `assets/css/extended/custom.css`
- Hero quote styling with hover effects
- Font family overrides
- Dark mode theme support
- Mobile responsive design

### Hugo Configuration (`hugo.yaml`)
- Outputs HTML, RSS, and JSON (for search functionality)
- Menu structure defined for navigation
- Theme set to `hugo-PaperMod`

## Content Guidelines

### Front Matter Template
```yaml
---
title: "Post Title"
date: 2025-01-15T10:00:00-07:00
draft: false
tags: ["orthodoxy", "theology"]
categories: ["faith"]
summary: "Brief description"
---
```

### Image References
- Place images in `static/images/`
- Reference in content as `/images/filename.jpg`

## Theme Notes

- PaperMod theme is included as a git submodule at `themes/hugo-PaperMod/`
- Never edit theme files directly
- Extend theme functionality using:
  - `layouts/partials/extend_head.html` for custom head content
  - `layouts/partials/extend_footer.html` for custom footer content
  - `assets/css/extended/` for custom CSS
  - `layouts/shortcodes/` for custom shortcodes

## Deployment

The site is configured for GitHub Pages deployment, though no GitHub Actions workflow is currently set up. Manual deployment requires:

1. Build: `hugo --minify`
2. Deploy the `public/` directory to hosting

## Troubleshooting

**Theme not loading:** Run `git submodule update --init --recursive`

**Build failures:** Clear cache with `hugo --gc` and check content file syntax

**Font issues:** Verify `layouts/partials/extend_head.html` exists and Google Fonts CDN is accessible
