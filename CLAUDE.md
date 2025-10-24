# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static website for Triad Elite Group built with Astro.build. The site uses MDX for content pages, Astro components for layouts, and Tailwind CSS 4 for styling.

## Development Commands

- **Start dev server**: `npm run dev` (runs on `http://localhost:4321`)
- **Build for production**: `npm run build` (runs type checking with `astro check` before building)
- **Preview production build**: `npm run preview`

## Architecture

### Content Strategy
- Content pages are written in **MDX format** (Markdown + JSX) in `src/pages/`
- All MDX pages specify a layout via frontmatter: `layout: ../layouts/Page.astro`
- The `Page.astro` layout provides consistent navigation, header, and footer across all pages

### Layout System
- **Primary Layout**: `src/layouts/Page.astro`
  - Accepts optional `title` prop (defaults to "Triad Elite Group")
  - Includes global navigation in header (Home, About)
  - Contains global styles using `:global()` selectors for html and body
  - Provides centered content container with max-width of 800px

### Site Configuration
- Site URL is configured in `astro.config.mjs` as `https://triadelitegroup.com`
- Uses strict TypeScript configuration (`astro/tsconfigs/strict`)
- MDX integration is enabled via `@astrojs/mdx`

## Styling

- **Tailwind CSS 4** is integrated via the `@tailwindcss/vite` plugin
- Global Tailwind import is in `src/styles/global.css`
- The Page.astro layout uses Tailwind utility classes for all styling
- Use Tailwind classes directly in Astro components and MDX files

### Dark Mode

- Dark mode is configured to **automatically respect the user's system preference** via `prefers-color-scheme`
- No configuration needed - Tailwind CSS 4 supports this by default
- Use the `dark:` variant to specify dark mode styles (e.g., `dark:bg-neutral-900`)
- Custom color palette defined in `src/styles/global.css` using the `@theme` directive:
  - **Primary colors**: `primary-50` through `primary-950` (blue shades for branding)
  - **Neutral colors**: `neutral-50` through `neutral-950` (gray shades for UI elements)
- Example usage: `bg-neutral-100 dark:bg-neutral-950` for background colors that adapt to theme

## Key Patterns

When adding new pages:
1. Create an `.mdx` file in `src/pages/`
2. Add frontmatter with `layout: ../layouts/Page.astro` and optional `title`
3. Update navigation links in `src/layouts/Page.astro` if needed for main nav
4. Use Tailwind utility classes for styling within MDX content
- The triad current site is downloaded at ./docs/current.html
- the logo in the header should always be set to maintain its aspect ratio