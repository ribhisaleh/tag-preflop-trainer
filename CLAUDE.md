# TAG Preflop Trainer

A single-page poker preflop range trainer for TAG (Tight-Aggressive) strategy.
Built as a self-contained HTML file with no dependencies beyond Google Fonts.

## Stack
- Pure HTML/CSS/JS — no build step, no package manager
- Single entry point: `index.html`
- PWA: installable on mobile and desktop, works offline
- Hosted on GitHub Pages and Vercel (static)

## Project Structure
```
index.html          # Entire app — HTML, CSS, JS in one file
favicon.svg         # App icon (gold spade on dark background)
manifest.json       # PWA manifest — name, theme, icons
sw.js               # Service worker — cache-first offline support
CLAUDE.md           # This file
docs/
  todo.md           # Enhancement backlog
  superpowers/      # AI planning artifacts (specs, plans)
```

## Live URLs
- Vercel (primary): https://tag-preflop-trainer.vercel.app
- GitHub Pages (fallback): https://ribhisaleh.github.io/tag-preflop-trainer

## Deploying
- GitHub Pages: Auto-deploys on every push to `master`
- Vercel: Auto-deploys on every push to `master` (connected via GitHub)

## Installing as an App
- **Desktop (Chrome/Edge):** Visit Vercel URL → click ⊕ in address bar → Install
- **iOS Safari:** Share → Add to Home Screen
- **Android Chrome:** Menu → Add to Home Screen

## Enhancing
Before making changes: run brainstorming skill → writing-plans skill → executing-plans skill.
See `docs/todo.md` for the enhancement backlog.
