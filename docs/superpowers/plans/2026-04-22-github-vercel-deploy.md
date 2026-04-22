# GitHub + Vercel Deploy Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Deploy the TAG Preflop Trainer as a public static web app on GitHub Pages and Vercel, accessible from any device.

**Architecture:** Single static HTML file served from a public GitHub repo. GitHub Pages auto-serves from the root of `main`. Vercel connects via GitHub and auto-deploys on every push.

**Tech Stack:** HTML/CSS/JS (no build step), GitHub CLI (`gh`), Vercel CLI (`vercel`)

---

### Task 1: Create `.gitignore`

**Files:**
- Create: `.gitignore`

- [ ] **Step 1: Create `.gitignore`**

Create `d:/desktop2-oct13/TAG-PreFlopTrainer/.gitignore` with this exact content:

```
.DS_Store
Thumbs.db
desktop.ini
.vercel
```

- [ ] **Step 2: Verify file exists**

Run: `ls d:/desktop2-oct13/TAG-PreFlopTrainer/`
Expected: `.gitignore` appears in listing.

---

### Task 2: Create `favicon.svg`

**Files:**
- Create: `favicon.svg`

- [ ] **Step 1: Create `favicon.svg`**

Create `d:/desktop2-oct13/TAG-PreFlopTrainer/favicon.svg` with this exact content:

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32 32">
  <defs>
    <linearGradient id="g" x1="0" y1="0" x2="1" y2="1">
      <stop offset="0%" stop-color="#f59e0b"/>
      <stop offset="100%" stop-color="#fbbf24"/>
    </linearGradient>
  </defs>
  <rect width="32" height="32" rx="6" fill="#06080f"/>
  <path d="M16 4 C12 4 7 8.5 7 13.5 C7 17.2 9.5 19.5 13 19.5 C11.5 22 9.5 23.5 7.5 24.5 L24.5 24.5 C22.5 23.5 20.5 22 19 19.5 C22.5 19.5 25 17.2 25 13.5 C25 8.5 20 4 16 4 Z" fill="url(#g)"/>
  <rect x="14.5" y="22.5" width="3" height="3.5" rx="1" fill="url(#g)"/>
</svg>
```

---

### Task 3: Rename HTML to `index.html` and add favicon link

**Files:**
- Rename: `tag-preflop-trainer.html` → `index.html`
- Modify: `index.html` (add favicon `<link>` tag)

- [ ] **Step 1: Rename the file**

Run:
```bash
mv "d:/desktop2-oct13/TAG-PreFlopTrainer/tag-preflop-trainer.html" "d:/desktop2-oct13/TAG-PreFlopTrainer/index.html"
```

- [ ] **Step 2: Add favicon link to `<head>`**

Open `index.html`. Find this line (it's near the top, around line 4):
```html
<meta charset="UTF-8"/>
```

Add the favicon link immediately after it so `<head>` looks like:
```html
<meta charset="UTF-8"/>
<link rel="icon" href="favicon.svg" type="image/svg+xml"/>
```

- [ ] **Step 3: Verify the file opens correctly in a browser**

Open `index.html` in a browser locally. Confirm:
- App loads with the dark background and gold "TAG" logo
- Browser tab shows a gold spade icon (favicon)

---

### Task 4: Create `CLAUDE.md`

**Files:**
- Create: `CLAUDE.md`

- [ ] **Step 1: Create `CLAUDE.md`**

Create `d:/desktop2-oct13/TAG-PreFlopTrainer/CLAUDE.md` with this exact content:

```markdown
# TAG Preflop Trainer

A single-page poker preflop range trainer for TAG (Tight-Aggressive) strategy.
Built as a self-contained HTML file with no dependencies beyond Google Fonts.

## Stack
- Pure HTML/CSS/JS — no build step, no package manager
- Single entry point: `index.html`
- Hosted on GitHub Pages and Vercel (static)

## Project Structure
```
index.html          # Entire app — HTML, CSS, JS in one file
favicon.svg         # App icon (gold spade on dark background)
CLAUDE.md           # This file
docs/
  todo.md           # Enhancement backlog
  superpowers/      # AI planning artifacts (specs, plans)
```

## Live URLs
- GitHub Pages: https://ribhisaleh.github.io/tag-preflop-trainer
- Vercel: https://tag-preflop-trainer.vercel.app

## Deploying
- GitHub Pages: Auto-deploys on every push to `main`
- Vercel: Auto-deploys on every push to `main` (connected via GitHub)

## Enhancing
Before making changes: run brainstorming skill → writing-plans skill → executing-plans skill.
See `docs/todo.md` for the enhancement backlog.
```

---

### Task 5: Create `docs/todo.md`

**Files:**
- Create: `docs/todo.md`

- [ ] **Step 1: Create `docs/todo.md`**

Create `d:/desktop2-oct13/TAG-PreFlopTrainer/docs/todo.md` with this content:

```markdown
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
_Add completed features here as they ship._
```

---

### Task 6: Initialize git, create GitHub repo, and push

**Files:** None (git operations)

**Prerequisites:** GitHub CLI must be installed and authenticated.
- Check: `gh --version` (if not found, install from https://cli.github.com)
- Check auth: `gh auth status` (if not authed, run `gh auth login`)

- [ ] **Step 1: Initialize git repo**

```bash
cd d:/desktop2-oct13/TAG-PreFlopTrainer
git init
git add .
git commit -m "feat: initial commit — TAG Preflop Trainer with GitHub Pages + Vercel deploy"
```

Expected output ends with: `1 file changed` or similar — no errors.

- [ ] **Step 2: Create public GitHub repo**

```bash
gh repo create ribhisaleh/tag-preflop-trainer --public --source=. --remote=origin --push --description "TAG Poker Preflop Range Trainer — play from any device"
```

Expected: Outputs `✓ Created repository ribhisaleh/tag-preflop-trainer` and pushes commits.

- [ ] **Step 3: Verify repo is live**

Run: `gh repo view ribhisaleh/tag-preflop-trainer --web`
Expected: Opens `https://github.com/ribhisaleh/tag-preflop-trainer` in browser showing all files.

---

### Task 7: Enable GitHub Pages

**Files:** None (GitHub API call)

- [ ] **Step 1: Enable GitHub Pages via API**

```bash
gh api repos/ribhisaleh/tag-preflop-trainer/pages \
  --method POST \
  --field source[branch]=main \
  --field source[path]=/
```

Expected output includes `"html_url": "https://ribhisaleh.github.io/tag-preflop-trainer"`.

- [ ] **Step 2: Wait for Pages to build (60–90 seconds), then verify**

```bash
gh api repos/ribhisaleh/tag-preflop-trainer/pages --jq '.status,.html_url'
```

Expected: `"built"` and `"https://ribhisaleh.github.io/tag-preflop-trainer"`.

- [ ] **Step 3: Open in browser and confirm**

```bash
gh api repos/ribhisaleh/tag-preflop-trainer/pages --jq '.html_url' | xargs start
```

Confirm the app loads and the gold spade favicon shows in the browser tab.

---

### Task 8: Deploy to Vercel

**Files:** None (Vercel deployment)

**Prerequisites:** Node.js must be installed (`node --version`).

- [ ] **Step 1: Install Vercel CLI if not present**

```bash
vercel --version
```

If not found, run:
```bash
npm install -g vercel
```

- [ ] **Step 2: Login to Vercel**

```bash
vercel login
```

Follow the prompts — choose email login with `ribhisaleh@gmail.com` or GitHub OAuth. This opens a browser to authenticate.

- [ ] **Step 3: Deploy**

From the project directory:
```bash
cd d:/desktop2-oct13/TAG-PreFlopTrainer
vercel --prod
```

When prompted:
- **Set up and deploy?** → `Y`
- **Which scope?** → Select your personal account
- **Link to existing project?** → `N`
- **Project name?** → `tag-preflop-trainer`
- **Directory?** → `.` (current directory)
- **Want to override settings?** → `N`

Expected: Outputs a `https://tag-preflop-trainer.vercel.app` URL (or similar).

- [ ] **Step 4: Connect Vercel to GitHub for auto-deploys**

Go to https://vercel.com/dashboard → find `tag-preflop-trainer` → Settings → Git → Connect to `ribhisaleh/tag-preflop-trainer` on GitHub.

From now on, every `git push` to `main` triggers automatic Vercel redeploy.

- [ ] **Step 5: Verify Vercel URL in browser**

Open the Vercel URL from Step 3. Confirm:
- App loads correctly
- Gold spade favicon visible in tab
- Works on mobile (test with your phone)

---

## Self-Review Notes

- Spec requirement: `index.html` rename ✅ Task 3
- Spec requirement: `favicon.svg` creation ✅ Task 2
- Spec requirement: favicon link in `<head>` ✅ Task 3
- Spec requirement: `CLAUDE.md` ✅ Task 4
- Spec requirement: `docs/todo.md` ✅ Task 5
- Spec requirement: GitHub public repo ✅ Task 6
- Spec requirement: GitHub Pages enabled ✅ Task 7
- Spec requirement: Vercel deploy ✅ Task 8
- No placeholders or TBDs found.
- All commands include expected output.
