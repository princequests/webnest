# WebNest v5 UI update

- Popular marketplace listings now use a two-column app-store grid instead of full-width list rows.
- Selecting a listing opens a dedicated full-screen app details page with an install action.
- Installation is now a dedicated full-screen setup flow. Users can edit the app name, URL and icon, choose standalone or browser launch mode, and select a collection.
- Standalone installed mini-apps open in their own route with the web content filling the available screen. The WebNest bottom navigation and marketplace chrome are not shown while the mini-app is open.
- Apps configured for browser mode continue to open in the browser view.

## Build

Run `flutter pub get` and `flutter run` from the project root. This package has not been compiled in this environment; run `flutter analyze` and test on Android/iOS before release.
