# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Single-page landing site for **Seedwork**, a Danish venture studio founded by Barnabas Skoda. Deployed via GitHub Pages at `seedwork.dk`.

## Architecture

**Zero build process.** Everything lives in `docs/index.html` — a single HTML file with all styles and scripts inline. GitHub Pages serves directly from the `docs/` folder.

```
docs/
├── index.html     # Entire site: HTML + inline CSS (~600 lines) + inline JS (~50 lines)
├── CNAME          # seedwork.dk
├── logo.png
├── pfp.jpeg       # Founder photo
├── hero.jpg       # Hero image
└── hero1.jpg
```

To preview: open `docs/index.html` directly in a browser. No server needed.

## Design System

The site uses a custom dark-theme design system defined within `index.html`:

- **Colors**: bg `#050505`, text `#FFFFFF`, gradient accent `#4285F4 → #9333EA → #DB2777`
- **Fonts**: Plus Jakarta Sans (sans-serif), Instrument Serif (serif) — loaded from Google Fonts
- **CSS variables**: `--bg`, `--text`, `--radius-xl` (2.5rem), `--ease` (`cubic-bezier(0.32, 0.72, 0, 1)`)
- **Patterns**: Double-bezel island components, bento grid layout, scroll-triggered reveal animations via Intersection Observer

Design system skills for Claude-assisted work are in `.claude/skills/` — particularly `stitch-skill/DESIGN.md` for comprehensive typography, spacing, component, and anti-pattern rules.

## Page Structure

1. Floating island nav (logo + links + CTA)
2. Full-viewport hero with mesh gradient glow animations
3. Founder / About split layout
4. Ecosystem bento grid — three ventures: Grain (AI safety), Core1000 (EdTech), BudGruppen (local commerce)
5. Footer
6. Hidden modals: About, Contact, Privacy, Terms

## JavaScript

Vanilla JS inline at bottom of `index.html`:
- Intersection Observer for `.reveal` scroll animations
- Modal open/close handlers
- Nav scroll effect (padding/background transition)
