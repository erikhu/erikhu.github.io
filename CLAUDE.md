# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static personal portfolio/resume website for Erik Gonzalez, hosted on GitHub Pages at erikhu.github.io (custom domain: erikhu.com).

## Development & Deployment

There is no build step. Edit files and push to `master` to deploy via GitHub Pages.

To preview locally, open `index.html` in a browser. For live reload, use any static file server (e.g., `python3 -m http.server`).

## Architecture

The entire site is three files:

- **index.html** — Single-page layout using Alpine.js for templating and DaisyUI/Tailwind for styling. All frameworks loaded via CDN.
- **data.js** — JavaScript object containing all resume content (experience, skills, bio, etc.). The HTML template binds to this data via Alpine.js `x-data`.
- **CNAME** — Custom domain config for GitHub Pages.

**Key patterns:**
- Content changes go in `data.js`; layout/structure changes go in `index.html`
- Alpine.js v2 directives (`x-data`, `x-for`, `x-text`, `x-show`) drive all dynamic rendering
- Dark/light theme toggle uses DaisyUI themes with localStorage persistence
- Print styles are included for PDF export via browser print
