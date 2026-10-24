# Orbit TV Launcher

Orbit TV is an Android TV-style launcher built as a native Android app with an HTML interface.

## Build the APK on GitHub (no Android Studio required)

1. Create a repository on [GitHub](https://github.com/new).
2. Extract this ZIP on your computer.
3. Upload **the contents of the extracted folder** to the repository root. Do not upload only the ZIP file. Ensure the `.github/workflows/build.yml` file is included. If hidden files are not visible, enable viewing hidden files.
4. Open the repository's **Actions** tab. The **Build Orbit TV APK** workflow starts after a push. You can also open it and select **Run workflow**.
5. Wait for the workflow to finish successfully.
6. Open the completed workflow run, scroll to **Artifacts**, and download **OrbitTV-apk**.
7. Extract the downloaded artifact. It contains `app-debug.apk`.
8. Install that APK on your Android TV using a USB drive, an APK installer, or ADB.

## Install with ADB

Replace `TV_IP` with your TV's IP address, and run these commands from a computer with Android Platform Tools installed:

```sh
adb connect TV_IP:5555
adb install app-debug.apk
```

Wireless ADB must be enabled on the TV for this method to work. Some TV brands restrict installing third-party launchers or setting a custom home app.

## Troubleshooting

- **No Actions workflow appears:** Check that `.github/workflows/build.yml` is present in the repository and that GitHub Actions is enabled.
- **Build failed:** Open the failed workflow run and inspect the first red step and its log.
- **APK does not appear:** Download the artifact from a *successful* workflow run; the APK is not committed to the repository.
- **Only a ZIP is visible in the repository:** Extract the project first, then upload its files and folders.

The workflow builds a **debug APK** for testing. A production release should be signed with a private release key before distribution.
