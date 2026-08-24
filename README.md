# Operating System

A personal daily "operating system" — a phone-installable habit tracker that ramps up gradually instead of demanding everything on day one.

**Live app:** https://filipsslavov.github.io/operating-system/

## What it does

The app installs habits in **layers**, one at a time:

1. **Foundation** — fixed wake time, phone charging outside the bedroom, a daily walk.
2. **Movement** — adds the gym (3×/week) and a daily step goal.
3. **Food** — adds four food rules (protein anchor, no liquid calories on weekdays, etc.).
4. **Full system** — adds deep work blocks, a job-search cadence, and a long-running project plan.

A layer only unlocks the next one after it's been **held 5 of 7 days** in a week — missed weeks just repeat, nothing is lost. This keeps the system honest about pace instead of front-loading every habit at once.

### Four tabs

- **Today** — a giant numeral showing habits done today, a red "right now" block driven by a built-in weekday schedule, the day's checklist grouped by layer (with the next locked layer visible below), and quick stats (days held, steps, weight lost so far).
- **Plan** — the full reference: the install order, the weekday schedule, the four food rules, the gym program (A/B split), the weekly job-search cadence, the 12-week project plan, phone rules, and what "on track" looks like at 1/3/6/12 months.
- **Log** — today's counters (applications sent, outreach, project hours, steps), a weekly weigh-in field, and a "parking lot" for new project ideas so they don't derail the current one.
- **Review** — a weight-loss trend with a sparkline, a weekly stats summary, and a short Sunday reflection note.

## How it's built

A single self-contained static web app — no backend, no build step, no dependencies beyond one Google Font (Archivo). All data (checklist state, weigh-ins, notes) is stored locally on your device via `localStorage`; nothing is sent anywhere.

- `index.html` — the entire app: markup, styles, and logic
- `manifest.json` — the web app manifest (name, icon, standalone display) so it installs as a real app
- `icon.svg` — the home-screen icon
- `sw.js` — a small service worker that caches the app shell for offline use after the first load

Visually it follows the **Modernist** design system: flat, architectural, set entirely in Archivo, with a single red accent, zero corner radius, and strong 2px rules.

## Installing on your phone

1. Open the live app link above in Chrome (Android) or Safari (iOS).
2. Tap **Install app** (Chrome) or **Share → Add to Home Screen** (Safari).
3. Launch it from your home screen — it runs full-screen and works offline after the first load.

## Updating

Edit the files and re-upload them at `github.com/filipsslavov/operating-system/upload/main` (or push via git) — GitHub Pages redeploys automatically from the `main` branch.
