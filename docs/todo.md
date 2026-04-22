# TAG Preflop Trainer — Enhancement Backlog

## High Priority
- [ ] Persist stats across sessions (localStorage)
- [ ] Add BB/SB defense ranges
- [ ] Sound effects for correct/wrong answers

## Medium Priority
- [ ] 3-bet and 4-bet scenario training
- [ ] Hand history review mode (see all hands answered in session)
- [ ] Export stats as CSV

## Under Consideration
- [ ] Custom range editor (upload your own ranges)
- [ ] GTO vs TAG range comparison mode
- [ ] Leaderboard / multiplayer challenge mode

## Review

### 2026-04-22 — Initial deploy + PWA
- Renamed `tag-preflop-trainer.html` → `index.html` for GitHub Pages / Vercel compatibility
- Added gold spade `favicon.svg` matching the app's amber/gold theme
- Created public GitHub repo: https://github.com/ribhisaleh/tag-preflop-trainer
- Deployed to Vercel: https://tag-preflop-trainer.vercel.app (auto-deploys on push)
- Enabled GitHub Pages: https://ribhisaleh.github.io/tag-preflop-trainer (auto-deploys on push)
- Added PWA support (`manifest.json` + `sw.js`) — app is now installable on mobile/desktop and works offline
