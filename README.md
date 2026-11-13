# TRACE (Android)

AI-powered UX research and design tracing. Native Android shell (Kotlin WebView) + offline web UI built from your Stitch "Luminous Clarity" design.

## Build the APK

**Option A: Android Studio (easiest)**
1. Open this folder in Android Studio (Koala or newer), let Gradle sync.
2. Build > Build Bundle(s) / APK(s) > Build APK(s).
3. APK: `app/build/outputs/apk/debug/app-debug.apk` (installable directly; enable "install unknown apps").

**Option B: Command line** (JDK 17 + Android SDK installed)
`./gradlew assembleDebug`

**Option C: GitHub Actions (no local setup)**
Push this folder to a GitHub repo. The "Build TRACE APK" workflow builds it; download `TRACE-apk` from the run's Artifacts.

## Using the app
- Settings > **Claude API Key**: needed for insights and the trace report (https://console.anthropic.com/settings/keys).
- Settings > **Figma Token**: only needed for loading Figma frames. Screenshots need no token.
- Flow: New Project > Add Research > AI Insights > Connect Design > Trace Report > Export PDF.
- All data is stored on the device only.

## Project layout
- `app/src/main/java/com/trace/app/MainActivity.kt`: WebView host, file picker, network bridge, PDF print, back button.
- `app/src/main/assets/www/`: the UI (`index.html`, `app.css`, `app.js`, bundled fonts and icons).
