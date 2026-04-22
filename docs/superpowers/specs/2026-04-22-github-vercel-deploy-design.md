# TAG Preflop Trainer — GitHub + Vercel Deploy Design

**Date:** 2026-04-22  
**Status:** Approved

## Goal

Deploy the existing single-file poker preflop trainer to GitHub and Vercel so it's accessible from any device (mobile/laptop) via a browser URL, and downloadable from GitHub.

## Repository

- **GitHub user:** ribhisaleh
- **Repo name:** tag-preflop-trainer
- **Visibility:** Public
- **URL:** https://github.com/ribhisaleh/tag-preflop-trainer

## Files

| File | Action | Notes |
|---|---|---|
| `index.html` | Rename from `tag-preflop-trainer.html` | GitHub Pages and Vercel require `index.html` as entry point |
| `favicon.svg` | Create | Poker spade icon with gold gradient matching app theme (#f59e0b → #fbbf24) |
| `CLAUDE.md` | Create | Project context for future Claude sessions |
| `docs/todo.md` | Create | Enhancement backlog |
| `.gitignore` | Create | Ignore OS files (.DS_Store, Thumbs.db) |

## Favicon Design

- Shape: Bold spade ♠ centered on a dark rounded card background
- Colors: Gold gradient (#f59e0b → #fbbf24) fill, dark background (#06080f) matching the app
- Format: SVG (scales perfectly on all devices, no blurriness)
- Integration: `<link rel="icon" href="favicon.svg" type="image/svg+xml">` added to `index.html` `<head>`

## Hosting

### GitHub Pages
- Enable on `main` branch, served from root `/`
- URL: `https://ribhisaleh.github.io/tag-preflop-trainer`
- Use: Fallback URL, direct download access

### Vercel
- Deploy via `vercel` CLI
- URL: `https://tag-preflop-trainer.vercel.app` (or similar)
- Use: Primary fast CDN URL, auto-deploys on every push to `main`

## Constraints

- Zero changes to the app logic or styling — only `index.html` rename + favicon link added
- No build step, no package.json — pure static HTML
- Vercel detects static site automatically, no `vercel.json` needed
