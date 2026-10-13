# Daely Home – private family calendar PWA

Offline-first, static PWA for GitHub Pages. Calendar records are stored in the browser's IndexedDB; no backend or account is required.

## Features
- Dashboard with today's agenda and open tasks
- Month, week and day calendar views
- Events, categories, weekly recurrence, tasks and priorities
- JSON export/import
- Basic `.ics` import
- Optional weather lookup using Open-Meteo and browser geolocation
- Kiosk-style full-screen dashboard
- Service-worker asset caching

## Publish on GitHub Pages
1. Create a GitHub repository, for example `daely-home`.
2. Upload all files and folders from this project to the repository root.
3. Open **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**, branch `main`, folder `/(root)`, and save.
5. Wait for deployment, then open the URL shown by GitHub Pages, usually `https://YOUR-USER.github.io/daely-home/`.

The app uses relative URLs so it works under a project-site path.

## Install on Android / Xiaomi tablet
1. Open the Pages URL in Chrome.
2. Open Chrome's ⋮ menu and choose **Install app** or **Add to Home screen**.
3. Confirm, then launch the new icon. Choose full screen in the app with the Kiosk button.
4. For a stable wall display, configure Android's screen timeout and optionally pin the app using Android's app-pinning feature.

Installation menu wording and WebAPK behavior depend on Android/Chrome version and whether Google Mobile Services are available.

## Backups and privacy
Use **Daten & Einstellungen → JSON exportieren** regularly and keep the file somewhere safe. Import replaces existing categories, events and tasks. GitHub Pages serves the code; it does not sync browser data.

Do not put a GitHub personal access token in client-side JavaScript. Anyone who can inspect the deployed code can extract it. For GitHub backups, manually upload the exported JSON to a **private** repository, or add a separate trusted backend/proxy with authentication. A private repository does not make data in a public Pages app private.

## Current limitations
- ICS import handles common VEVENT fields and retains RRULE text, but does not fully expand every recurrence pattern, timezone, EXDATE or detached occurrence.
- External ICS URLs may be blocked by CORS. Download the `.ics` file and import it locally, or use a trusted proxy.
- Local browser data is device/browser-profile-specific; it does not automatically sync across devices.
- Tailwind and Google Fonts are loaded from external CDNs in this starter. The app's main files are cached, but for strict offline/privacy use, remove those CDN dependencies and use the included CSS/system fonts.
- This is a functional starter, not a full replacement for a production calendar's conflict handling, accessibility testing, or automated test suite.

## Development
Serve this folder over localhost (not `file://`) for service-worker testing, e.g. `python -m http.server 8000`, then open `http://localhost:8000`.
