# Ameer Finance — 2026 PWA

A private, offline-capable personal finance planner designed for iPhone and GitHub Pages. No account, backend, analytics, or third-party libraries are required.

## Features
- Dashboard with monthly metrics, savings chart, category breakdown and quick actions.
- Month-specific salary settings and payslip calculation.
- Leave planner that counts actual Thursdays, Fridays, Saturdays and Sundays in each month, excluding leave dates.
- Optional manual override of paid working days for payroll adjustments.
- USD and MVR expense entries, with monthly exchange rate (default 22.50 MVR/USD).
- Optional actual USD exchanged amount for MVR expenses.
- Savings ledger with month-to-month running balance.
- Annual report and CSV export.
- JSON backup and restore.
- Local browser storage and offline PWA cache.

## Salary calculation
Gross = base salary + (daily allowance × paid working days) + telephone allowance.
Net = gross − (base salary × pension percentage) − social fund.

Default salary settings: base $1,365; daily allowance $51; telephone $10; pension 7%; social fund $5.

Savings = net salary − USD expenses − MVR expenses converted to USD. If an actual USD exchanged amount is entered for the month, that amount replaces the calculated MVR conversion in the savings formula.

## Publish free with GitHub Pages
1. Create a GitHub account if needed.
2. Create a new repository named `ameer-finance` (public is simplest for GitHub Free Pages).
3. Upload **all files inside this folder** to the repository root. Keep the filenames and folder structure unchanged.
4. Open repository **Settings → Pages**.
5. Under **Build and deployment**, select **Deploy from a branch**; choose `main` and `/ (root)`, then Save.
6. Wait for GitHub Pages to publish. Your app address will look like `https://YOUR-USERNAME.github.io/ameer-finance/`.

## Install on iPhone
1. Open the published address in Safari.
2. Tap Share (square with arrow) → Add to Home Screen.
3. Enable “Open as Web App” if shown, then tap Add.
4. Launch Ameer Finance from the Home Screen.

## Data and backups
- Finance records are stored in this browser's local storage on the device. They are not uploaded to GitHub.
- Export a JSON backup regularly, especially before clearing Safari website data, changing browsers, or changing phones.
- To move records to another device, export the backup on the old device and import it on the new device.
- GitHub Pages hosts the app code. A public repository means the source code is publicly visible; do not put personal finance records in the repository.
- This is a budgeting tool, not a payroll system. Confirm payslips against your employer's actual payroll calculation.

## Local preview
For service worker/offline features, serve this folder through a local static web server or publish it to GitHub Pages. Opening `index.html` directly still allows basic local use, but service workers require HTTPS or localhost.


## Multiple budget years
Use the year selector in the top-right corner to switch between 2026–2030. Each year has its own local records (salary settings, leave, expenses, and exchange rates). Your existing 2026 records remain under the original 2026 storage key. New years start with the configured defaults, including 22.50 MVR/USD. Switch years at any time; data is saved automatically. Export a separate backup for each year.
