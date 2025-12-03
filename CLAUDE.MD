# CLAUDE.MD

## Project Overview

This is a personal Jekyll-based blog hosted on GitHub Pages. The site serves as a memory space for technical thoughts and learnings, authored by Marcelo Mendoza.

**Live Site:** http://mjmendo.github.io/
**Author:** Marcelo Mendoza
**Purpose:** Personal technical blog for documenting insights and thoughts

## Tech Stack

- **Static Site Generator:** Jekyll
- **Markdown Processor:** Redcarpet
- **Syntax Highlighting:** Pygments
- **Hosting:** GitHub Pages
- **CI/CD:** Travis CI (.travis.yml)

## Project Structure

```
.
├── _config.yml           # Jekyll configuration
├── _layouts/             # Page layout templates
├── _plugins/             # Jekyll plugins
├── _posts/               # Blog post markdown files
├── drafts/               # Draft posts (not published)
├── assets/               # Static assets
├── images/               # Image files
├── javascripts/          # JavaScript files
├── stylesheets/          # CSS files
├── index.html            # Homepage
├── archives.html         # Archives page
├── projects.html         # Projects page
├── about.md              # About page
└── params.json           # Configuration parameters
```

## Content Organization

### Blog Posts

Blog posts are located in `_posts/` and follow the Jekyll naming convention:
`YYYY-MM-DD-title-slug.md`

**Current Topics:**
- Backend to Frontend mental models
- TypeScript, Java, Python comparisons
- React patterns through backend analogies
- Data consistency models

### Post Format

Posts should follow Jekyll front matter format:
```yaml
---
layout: post
title: "Your Post Title"
date: YYYY-MM-DD
categories: [category1, category2]
---
```

## Configuration

**Site Settings (_config.yml):**
- Pagination: 15 posts per page
- Permalink structure: `/:title`
- Base URL: http://mjmendo.github.io/

## Development Workflow

### Adding a New Blog Post

1. Create a new file in `_posts/` with format: `YYYY-MM-DD-title.md`
2. Add Jekyll front matter at the top
3. Write content in Markdown
4. Commit and push to trigger GitHub Pages build

### Working with Drafts

- Store draft posts in `drafts/` directory
- Move to `_posts/` when ready to publish
- Update the date in filename to publication date

## Common Tasks

### Creating a New Post

1. Use the naming convention: `_posts/YYYY-MM-DD-descriptive-title.md`
2. Include front matter with title, date, layout
3. Write content using Markdown

### Updating Configuration

- Edit `_config.yml` for site-wide settings
- Requires Jekyll rebuild to see changes

### Testing Locally

```bash
bundle exec jekyll serve
```
(Requires Jekyll and Ruby environment)

## Style Guidelines

### Writing Style

Based on existing posts, the blog focuses on:
- Technical deep-dives
- Comparative analysis (languages, frameworks, patterns)
- Mental models and analogies
- Backend and frontend development topics

### Content Themes

- Software architecture patterns
- Language comparisons (TypeScript, Java, Python)
- Frontend frameworks (React)
- Distributed systems concepts
- Developer mental models

## Git Workflow

**Main Branch:** master
**Deployment:** Automatic via GitHub Pages on push to master

### Recent Activity
- TypeScript/Java/Python comparison posts
- React patterns documentation
- Backend-to-frontend mental models

## Important Notes

- This is a GitHub Pages site - changes pushed to master are automatically deployed
- The site uses older Jekyll configuration (redcarpet, pygments) which may need updating
- Posts are the primary content type
- Site serves as a personal knowledge base and memory aid

## Maintenance Considerations

1. **Dependencies:** Gemfile manages Ruby dependencies
2. **Build:** Travis CI configured for builds
3. **Content Focus:** Technical blog posts about software development
4. **Audience:** Personal reference with potential public readership

## Contact & Attribution

**Author:** Marcelo Mendoza
**Repository:** https://github.com/mjmendo/mjmendo.github.io

## Important information
- NEVER include Claude signature to documents, PRs commits or any other generated resource.
- When creating blog posts with tables and code, remember to use colors that are dark-mode friendly.

---

*This file helps Claude understand the project structure and provide better assistance with blog management, post creation, and site maintenance.*
