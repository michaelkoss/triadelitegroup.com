# Triad Elite Group Website

A static website built with [Astro.build](https://astro.build) for Triad Elite Group.

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ and npm

### Installation

```bash
npm install
```

### Development

```bash
npm run dev
```

Visit `http://localhost:4321` to see your site.

### Building for Production

```bash
npm run build
```

The static site will be generated in the `dist/` directory.

### Preview Production Build

```bash
npm run preview
```

## 📁 Project Structure

```
/
├── public/
│   └── favicon.svg
├── src/
│   ├── layouts/
│   │   └── Page.astro      # Main page layout
│   └── pages/
│       ├── index.mdx        # Homepage
│       └── about.mdx        # About page
├── astro.config.mjs         # Astro configuration
├── package.json
└── tsconfig.json
```

## 🧞 Commands

| Command          | Action                                       |
|:-----------------|:---------------------------------------------|
| `npm install`    | Installs dependencies                        |
| `npm run dev`    | Starts local dev server at `localhost:4321`  |
| `npm run build`  | Build production site to `./dist/`           |
| `npm run preview`| Preview build locally before deploying       |

## 📝 Content

Content is written in MDX format, which allows you to use both Markdown and JSX components.

- **Homepage**: `src/pages/index.mdx`
- **About**: `src/pages/about.mdx`

All pages use the `Page.astro` layout which provides consistent navigation and styling.