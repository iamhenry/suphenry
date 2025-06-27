# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## PROJECT OVERVIEW

This is a personal blog and portfolio website built with the Dante Astro theme. It uses Astro.js 5.5.6 as a static site generator with TypeScript, Tailwind CSS 4.0, and MDX for content authoring.

## DEVELOPMENT COMMANDS

```bash
# Development
npm run dev          # Start dev server at localhost:4321
npm start            # Alternative dev server command

# Build & Deploy  
npm run build        # Build production site to ./dist/
npm run preview      # Preview production build locally

# Astro CLI
npm run astro        # Access Astro CLI commands
npm run astro check  # Type check and validate content
```

## ARCHITECTURE

### Content-Driven Structure
- **Content Collections**: Three main types defined in `src/content.config.ts`
  - `blog/` - Blog posts with frontmatter (title, description, publishDate, tags, etc.)
  - `projects/` - Portfolio projects with similar structure
  - `pages/` - Static pages (about, contact, terms)
- **Zod Schemas**: All content validated with TypeScript schemas
- **File-based Routing**: Pages in `src/pages/` become routes automatically

### Key Directories
- `src/components/` - Reusable Astro components (Header, Footer, Navigation, etc.)
- `src/layouts/` - Page templates, BaseLayout is the foundation
- `src/data/` - Site configuration and type definitions
- `src/utils/` - Helper functions for content processing and formatting
- `src/icons/` - SVG icon components as individual Astro files
- `src/styles/` - Global CSS and Tailwind configuration

### Configuration Files
- `src/data/site-config.ts` - Main site settings (title, description, author, social links)
- `astro.config.mjs` - Astro integrations and build configuration  
- `src/content.config.ts` - Content collection schemas and validation

## CONTENT MANAGEMENT

### Adding Blog Posts
Create `.md` or `.mdx` files in `src/content/blog/` with frontmatter:
```yaml
---
title: "Post Title"
description: "Meta description"
publishDate: "2024-01-01"
tags: ["tag1", "tag2"]
---
```

### Adding Projects
Create files in `src/content/projects/` with similar frontmatter structure.

### Theme Customization
- Colors and styling: `src/styles/global.css`
- Site metadata: `src/data/site-config.ts`
- Component styling uses Tailwind CSS utility classes

## STYLING SYSTEM

- **Tailwind CSS 4.0** with custom theme configuration
- **Dark/Light Mode**: Automatic theme switching with localStorage persistence
- **Typography Plugin**: Enhanced content styling for markdown
- **CSS Custom Properties**: Theme variables defined in global.css

## IMPORTANT NOTES

- NO TESTING FRAMEWORK is currently configured
- Uses strict TypeScript configuration
- Prettier 3.5.3 configured for code formatting
- Content pagination set to 8 items per page
- RSS feed and sitemap automatically generated
- SEO optimized with OpenGraph meta tags and canonical URLs