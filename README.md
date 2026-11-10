# AutoWeb Browser

A mobile Android web browser starter project with:
- WebView browsing and Google search
- URL/address bar and back/forward/reload/home controls
- Bookmarks and browsing history stored locally
- Downloads through Android DownloadManager
- JavaScript and DOM storage for modern websites and YouTube mobile web
- GitHub Actions workflow that builds a debug APK

## Important Android Auto limitation

This project is a **phone browser**. It does not project arbitrary web pages or video to an Android Auto head unit.
Google's current Android for Cars documentation lists browsers and video as parked-app categories for **Android Automotive OS**, not Android Auto. Android Auto supports a defined set of app categories and does not provide a general-purpose browser/video surface. Do not use this app while driving.

Official references:
- https://developer.android.com/training/cars
- https://developer.android.com/training/cars/parked
- https://developer.android.com/docs/quality-guidelines/car-app-quality

## Build locally

1. Open this folder in Android Studio (Ladybug or newer).
2. Let Gradle sync.
3. Build > Build Bundle(s) / APK(s) > Build APK(s).

Or install Gradle 8.9 and run:

```bash
gradle assembleDebug
```

APK output:
`app/build/outputs/apk/debug/app-debug.apk`

## Build with GitHub Actions

Push this project to a GitHub repository. The workflow at
`.github/workflows/android.yml` runs on every push and pull request.
Download `app-debug` from the workflow run's Artifacts section.

## Package

`com.autoweb.browser`

## Notes

- This is a starter implementation, not a Play Store-certified car app.
- Downloads use Android's system DownloadManager.
- Bookmarks and history are stored on-device using SharedPreferences.
- The app intentionally does not save passwords or payment details.
