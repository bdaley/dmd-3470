# Project Guidelines

## Overview

Course project (`dmd-3470`) with multiple weekly exercises and a `final-project`.
The `final-project` uses **HTML5 Boilerplate v9.0.1** + **Bootstrap 5.3.8**, bundled with **Webpack 5**.

## Build and Dev

Run all commands from the `final-project/` directory.

| Command | Purpose |
|---------|---------|
| `npm start` | Dev server with live reload (auto-opens browser) |
| `npm run build` | Production build → `final-project/dist/` |

## Architecture

```
final-project/
  css/style.css    # H5BP base styles + author custom section
  js/app.js        # Webpack entry point → dist/js/app.js
  js/vendor/       # Third-party scripts copied to dist as-is
  img/             # Static images copied to dist as-is
  index.html       # HTML template processed by HtmlWebpackPlugin
```

- **Bootstrap** is loaded via **CDN** — do NOT install it as an npm dependency or import it through Webpack
- The Webpack production build (`npm run build`) templates `index.html` and copies `img/`, `css/`, `js/vendor/` to `dist/`

## HTML Conventions

- Always fill in `<title>`, `<meta name="description">`, and OG tag placeholders before shipping
- Set correct `lang` attribute on `<html>` (e.g., `lang="en"`)
- Bootstrap CDN `<link>` must come **before** `css/style.css` in `<head>`
- Bootstrap JS bundle CDN `<script>` must come **before** `js/app.js` at the end of `<body>`

## CSS Conventions

- Add all custom styles **below** the H5BP base block in `css/style.css`
- Prefer Bootstrap utility classes for layout and spacing before writing custom CSS

## JavaScript

- Vanilla JS only — no frontend frameworks installed
- Place third-party scripts that should not be Webpack-bundled in `js/vendor/`
- ES modules are supported via Webpack (use `import`/`export` freely in `js/app.js`)

## Code Style

Enforced by `.editorconfig`: 2-space indent, UTF-8, LF line endings, trailing newline.
