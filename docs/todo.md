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

### 2026-04-23 — Range Chart screen
- Added interactive 13×13 range chart screen accessible from home and mid-session
- Position selector (UTG/HJ/CO/BTN/SB/BB), action filter, tap-to-inspect hand verdict
- Chart peek button inside feedback bar during drill sessions

### 2026-04-26 — Rush & Cash Drill + Spin & Gold Chart
- Added Rush & Cash Drill screen: NL2 Rush & Cash specific ranges, 4 modes (RFI / vs Raise / Squeeze / All), 20-hand sessions with scoring and feedback
- Added Spin & Gold Chart screen: push/fold reference chart with 8 stack depth presets (4–25BB), push/call range toggle, tap-to-inspect detail, and golden rules summary
- Both accessible from home screen via new buttons
- Bumped service worker cache to v4
