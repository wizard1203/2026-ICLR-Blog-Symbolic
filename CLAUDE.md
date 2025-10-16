# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is the repository for the ICLR 2026 Blogposts Track, a Jekyll-based static website built using the [al-folio](https://github.com/alshedivat/al-folio) theme. The site hosts blog posts for the International Conference on Learning Representations (ICLR) 2026 blog track.

## Development Commands

### Local Development with Docker (Recommended)
```bash
# Run the development server
./bin/entry_point.sh
```

This command starts Jekyll with live reload on port 8080 and automatically monitors `_config.yml` changes.

### Local Development without Docker
```bash
# Install dependencies
bundle install

# Start development server
bundle exec jekyll serve --watch --port=8080 --host=0.0.0.0 --livereload
```

### Build Commands
```bash
# Build the site
bundle exec jekyll build

# Deploy to GitHub Pages (automatic via GitHub Actions)
./bin/deploy
```

## Architecture

### Site Structure
- **Jekyll-based static site** built with Liquid templating
- **al-folio theme** with custom modifications for ICLR branding
- **Multi-language support** with English as primary language
- **Responsive design** with Bootstrap components

### Key Directories
- `_layouts/` - Liquid layout templates (default.liquid, distill.liquid, post.liquid, etc.)
- `_posts/` - Blog posts in Markdown format with frontmatter
- `_pages/` - Static pages (about.md, call.md, submitting.md, reviewer_guidelines.md)
- `_config.yml` - Main configuration file
- `_includes/` - Reusable Liquid components
- `_data/` - YAML data files for dynamic content
- `assets/` - Static assets (CSS, JS, images)
- `_bibliography/` - BibTeX files for publications

### Content Management
- **Blog Posts**: Markdown files in `_posts/` with YAML frontmatter
- **Distill-style Posts**: Use `layout: distill` for the distill.pub style
- **Static Pages**: Create files in `_pages/` with appropriate frontmatter
- **Publications**: Managed through `_bibliography/papers.bib` with custom BibTeX keywords for buttons

### Configuration
- **Site Settings**: Title, URL, baseurl, theme colors in `_config.yml`
- **Analytics**: Google Analytics, Pirsch, OpenPanel support
- **SEO**: Open Graph and Schema.org metadata
- **Theme**: Customizable CSS variables in `_sass/` directory

### Publishing Workflow
- **GitHub Pages**: Automatic deployment via GitHub Actions
- **Branch Structure**: Source on main branch, deploys to gh-pages branch
- **Preview**: Site available at `https://iclr-blogposts.github.io/2026/`

### Custom Features
- **Distill Pub Style**: Special layout for academic blog posts
- **Math Support**: MathJax for mathematical content
- **Code Highlighting**: GitHub-style syntax highlighting
- **Responsive Grids**: Bootstrap-based layouts
- **Author Annotations**: Automatic linking of co-authors

### Build Process
- **Ruby/Jekyll**: Site generation and processing
- **Prettier**: Code formatting for Liquid files
- **Pre-commit**: Basic linting for file formatting
- **Docker**: Containerized development environment