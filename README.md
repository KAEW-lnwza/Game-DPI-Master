# Game DPI Master

Android Studio project (Kotlin).

## Features
- Lists only downloaded (non-system) applications, with a search box (by name or package).
- Select an app and enter a DPI profile value.
- Saves the value separately by package name using SharedPreferences.
- Launches the selected app from its settings screen.
- Can clear a saved profile.
- Animated anime-style background (moon/sun glow, twinkling stars, falling sakura petals, layered waves).
- Dark / Light mode switch (saved automatically).
- Press effects on buttons and list items.
- App icon: chicken with sunglasses.

## Shizuku (real DPI change)
The app talks to Shizuku and runs `wm density <value>` (device-wide) right before launching the selected app.
The value stays (even after reboot) until you press "คืนค่า DPI" in the app, which runs `wm density reset`.

If Shizuku is not connected, tapping an app shows a red message in the center of the screen
("กรุณาเชื่อมต่อชิซูกุก่อนใช้") and the app cannot be used until Shizuku is connected.
The dialog and the guide page include a "ดาวโหลดชิสุกู" link:
https://www.mediafire.com/file/u7mxnldfds8eg6a/shizuku-13-7-0-thedjchi.apk/file

Setup guide is inside the app (📖 คู่มือ Shizuku). Video guide: https://vt.tiktok.com/ZSshrLobP/
Android has no public API for a per-app density, so the change applies to the whole device.
Safe range is 120-900 DPI. If the screen ever becomes unusable: `adb shell wm density reset`.

## Requirements
- Android 7.0 (API 24) or higher (required by the Shizuku library).

## Credits
Made by kaew_king - TikTok: https://www.tiktok.com/@k_a_e_w.01

## Build
1. Open this folder in Android Studio.
2. Allow Gradle sync.
3. Build > Build APK(s).

Or push to GitHub: the workflow in `.github/workflows/build.yml` builds a debug APK
and uploads it as an artifact.

Package: `com.gamedpi.master`
