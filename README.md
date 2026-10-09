# Thumbnail Files (Android prototype v0.1)

Independent file browser for Android 8+, using Android's Storage Access Framework. No root, Samsung modifications or broad storage permission.

## Get an APK using GitHub Actions (no PC setup)
1. Create a new GitHub repository (private is fine).
2. Upload **the contents of this folder** to the repository root, including `.github/workflows/build.yml` (GitHub web upload may hide dotfolders; verify workflow is present).
3. Open **Actions > Build Android APK > Run workflow** (or push to `main`).
4. When green, download `thumbnail-files-debug-apk` from the run's Artifacts section, unzip and install `app-debug.apk` on your Android phone.
5. Android may require you to enable installing unknown apps for your browser/file manager.

## Features
- Pick a folder using the Android system picker, browse folders and videos.
- Grid (2-4 columns) or list mode.
- Visible video tiles autoplay, muted, looping from a configurable start to end point. No artificial concurrent-player cap. Performance depends on the phone and file codecs.
- Long-press a video for settings: choose a custom image cover and set preview start/end in seconds.
- Settings are stored locally, keyed by the document URI.

## Known limitations
- Prototype: not a complete replacement for Samsung My Files. Uses system folder picker; no copy/move/delete, carousel or arbitrary aspect-ratio control yet.
- VideoView may temporarily display a black frame while starting and hardware decoder availability limits simultaneous videos.
- The custom cover is shown until autoplay starts; for a permanent still cover, disable animation for that video.
- Folder permissions are granted by the user. Some Android protected folders are inaccessible.
- Debug APK is signed by Android's default debug key generated in the cloud; each fresh runner may use a different key, so subsequent builds may require uninstalling the previous build (local preferences would then be lost).
