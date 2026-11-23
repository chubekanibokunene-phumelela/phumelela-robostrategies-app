# Phumelela RoboStrategies

An offline-first, Android-friendly Progressive Web App (PWA) for tracking the Average-home vs Unclassified-away full-time draw strategy.

## Included
- Mobile-first dashboard and performance analytics
- CSV import for 2026/27 fixtures and verified cohort register
- Eligibility filter: Home cohort = Average; Away cohort = Unclassified
- Manual Bet365 full-time draw odds recording
- Pre-kickoff observation timestamp
- Bet placed / not placed tracking
- Full-time result entry (H/D/A), one-unit default stake, profit calculation
- CSV ledger export and JSON full-app backup/restore
- Service-worker offline cache

## Important limitations
- The app does not connect to Bet365, scrape odds, or place bets.
- It does not connect directly to Google Drive. Use Android's share/download flow or your browser's Downloads folder to move exported backups to Drive.
- Data is stored in the browser's local storage on the device. Export JSON backups regularly. Clearing browser site data can erase local records.
- This is a PWA project, not a signed Android APK. It must be hosted over HTTPS to install on Android. GitHub Pages is one free hosting option.

## Install on Android
1. Upload the contents of this folder to a GitHub repository.
2. Enable GitHub Pages for the repository (Settings → Pages → deploy from branch).
3. Open the published HTTPS URL in Chrome on Android.
4. Open Chrome menu → **Install app** or **Add to Home screen**.
5. Launch Phumelela RoboStrategies from the home screen. After its first successful load, the app shell can open offline.

## Import your Colab data
In the app, open **Data & rules**:
1. Import `FIXTURES_2627.csv` (columns: `date,time,League,home,away`).
2. Import `COHORT_REGISTER_2627_VERIFIED.csv` (columns include `League,Fixture_Team,Predictive_Cohort`).
3. Open Fixtures. Eligible matches are calculated from those two imported files.

## Backup
- Use **Download full backup** to save fixtures, cohorts and ledger in one JSON file.
- Use **Export ledger CSV** for the forward-testing ledger.
- Upload the downloaded backup files to your Google Drive manually.
- To restore on the same or a new device, open Data & rules → Restore backup and select the JSON file.

## Forward-test discipline
Only record odds observed before kickoff. Use Bet365 exclusively. Enter results after matches finish. Do not change the primary cohort rules during the V1 test. Experimental strategy candidates must be tracked separately.
