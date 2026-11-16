# WebNest — Flutter Web App Store

WebNest is a Flutter application that combines a web-app discovery catalogue, a website installer, a mini-app launcher and a lightweight embedded browser.

## Product direction

This is **not intended to imitate Google Chrome**. The primary experience is closer to an app marketplace:

1. **Discover** curated web applications by category.
2. Open a listing to read its description, then choose Install.
3. Add any website by entering its URL in **Add website**.
4. Inspect a site's Web App Manifest where available and use its name, icon, and display metadata.
5. Confirm the app name, URL, icon, launch mode and collection.
6. Launch installed web apps in standalone or browser mode.
7. Organize installed web apps into user-created collections.

The catalogue currently contains sample listings for Canva, Udemy, CrazyGames, Photopea, Figma, Google Docs, Khan Academy and Spotify Web. These are directory suggestions, not partnerships or guarantees that every feature of those sites works in an embedded WebView.

## Main navigation

- **Discover** — catalogue, categories, app search and direct website entry.
- **My Apps** — installed mini-apps and collections.
- **Add website** — enter a URL or search phrase, browse it, and install the current website.
- **Library** — collections and recently installed web apps.

## Architecture

- `lib/screens/store_home.dart` — marketplace, installation flow, launcher, browser surface and collections.
- `lib/models/browser_models.dart` — installed app, folder and bookmark models.
- `lib/services/browser_store.dart` — local persistence.
- `lib/services/pwa_manifest_service.dart` — Web App Manifest inspection.
- `lib/services/browser_engine.dart` — WebView file chooser and browser helpers.
- `lib/services/download_service.dart` — download storage service retained from Phase 3.

## Install flow

A listing's detail sheet explains the web app and offers **Install web app** or **Visit website first**. Direct website installation is also supported:

1. Open **Add website**.
2. Enter a URL and navigate.
3. Tap the install icon.
4. Confirm name, URL, icon, launch mode and collection.
5. The mini-app appears under **My Apps**.

PWA manifest detection is best-effort. Sites without a manifest can still be installed as browser-managed website shortcuts. A shortcut does not convert a website into a native application and cannot add features the website itself does not support.

## Run

From this directory:

```bash
flutter pub get
flutter run
```

If native platform folders are not present, generate them once:

```bash
flutter create --platforms=android,ios .
flutter pub get
flutter run
```

## Important limitations

- The current catalogue is a small starter directory. It is not a live app store backend.
- Web apps remain hosted and controlled by their original publishers.
- Some sites block embedded browsers, require external authentication, or depend on browser capabilities unavailable in WebView.
- Android WebView and iOS WKWebView have platform-specific behavior. Full Chromium extension support is not provided.
- True per-app cookie/profile isolation is not yet implemented. Mini-apps currently use the platform WebView's shared website storage context.
- Push notifications, offline installation, background sync, app-specific permissions and complete download interception need further native integration and testing.
- Test on physical Android and iOS devices before release. This archive has not been compiled in this environment.

## Next milestones

1. Persistent independent WebView profiles where platform support allows.
2. Native download interception with progress, pause/resume and file destinations.
3. Website permission prompts and safer popup handling.
4. Manifest and service-worker installability checks.
5. A remote catalogue backend so listings, categories, ratings and screenshots can be managed without shipping a new app version.
