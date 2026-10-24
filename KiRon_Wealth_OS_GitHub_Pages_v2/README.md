# KiRon Wealth OS

A self-contained personal finance flashboard designed for GitHub Pages.

## What persists
The site uses browser `localStorage`. Your balances, goals, debts, transactions, and planner inputs auto-save on the GitHub Pages URL and remain after refresh/revisit on the same browser/device.

**Important:** browser storage is tied to the specific website origin and device/browser. It is not automatic cloud sync. Clearing site data can erase local entries.

Use **Settings / Backup → Export JSON** periodically. The exported backup can be imported on another device/browser.

## First migration from the standalone HTML
1. Open your previous flashboard.
2. Export JSON.
3. Publish this package to GitHub Pages.
4. Open the GitHub Pages URL.
5. Go to Settings / Backup and import the JSON once.

## Publish with GitHub Pages
1. Create a new GitHub repository (for example `kiron-wealth-os`).
2. Upload **all files and folders in this package** to the repository root.
3. Commit the files to the `main` branch.
4. In GitHub: **Settings → Pages**.
5. Under **Build and deployment**, set **Source** to **GitHub Actions**.
6. The included workflow (`.github/workflows/deploy-pages.yml`) will deploy the site after each push to `main`.
7. GitHub will provide a Pages URL such as:
   `https://YOUR-USERNAME.github.io/kiron-wealth-os/`

The app uses only static files, so there is no build step or server to maintain.

## Files
- `index.html` — the flashboard
- `manifest.webmanifest` — installable app metadata
- `sw.js` — offline caching/service worker
- `assets/` — app icons
- `.nojekyll` — keeps GitHub Pages from processing the site with Jekyll

## Data safety
- Auto-save runs on input changes and when the page is hidden/closed.
- A save-status pill shows local save state.
- Export/Import JSON provides portable backups.
- The app can work offline after the first successful load.

## Future upgrade
For true cross-device sync, add an authenticated backend (for example Supabase/Firebase) or a private GitHub/Gist sync flow. Do not put financial API secrets directly in this static site.

## Interactive drilldowns
The landing dashboard stays compact. Deeper analysis appears only when requested:
- Click Free Cash for cash runway
- Click Protected Savings for bucket progress
- Click Investments for long-term projections
- Click Net Worth for a personal balance sheet
- Click dashboard goals for goal-specific pacing
- Use Payday Mode for new-money allocation
- Use Decision Lab for purchase, debt-vs-investing, salary-growth, and emergency-runway scenarios

The existing Car Decision utility remains available, but there is intentionally no separate car-ownership page.
