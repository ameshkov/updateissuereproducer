# Minimal Reproducer For Bug [#280783677](https://issuetracker.google.com/issues/280783677?pli=1)

The issue can be reproduced on Android 13 with an app that targets SDK level 30.

This [behavior change](https://developer.android.com/about/versions/13/behavior-changes-all#intents)
of Android 13 looks awfully relevant:

> When your app sends an intent to an exported component of another app that targets Android 13 or
higher, that intent is delivered if and only if it matches an <intent-filter> element in the
receiving app. 

### How to reproduce the issue

1. Put a newer version of the app to your device: `adb push app-release-2.0.apk /storage/emulated/0/Download/`
2. Run the app (release config).
3. Tap "Start Update" and choose the apk file with a newer version that you previously pushed on step 1.
4. Once you grant necessary permissions and install the newer version tap "Open" button on the final dialog.

*Expected result*

The app should be opened.

*Actual result*

On some devices it does not open.
 
### test.keystore

* Passwords: `123123`
* Key name: `keystore`