# WebNest – immersive mini-app update

## Standalone mini-app display
- Removed the WebNest app bar, close/refresh/menu controls, and all in-app navigation from standalone mini-app sessions.
- Expanded the WebView to fill the available display area.
- Enabled Android immersive-sticky system UI mode so the status and navigation bars are hidden during standalone use. Android may reveal system bars temporarily when the user performs the system edge gesture.
- Restores normal edge-to-edge system UI when the user exits the mini-app and returns to WebNest.
- Retains a minimal loading indicator and an in-page retry state for main-frame load failures.
- Browser-mode mini-apps continue to use the normal browser interface.

Note: Website-defined HTML fullscreen APIs and some video/game fullscreen behaviors depend on the website and native WebView platform support. This update provides app-level immersive display, not a separate native Android APK for each website.
