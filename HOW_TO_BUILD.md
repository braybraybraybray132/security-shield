# Secure Shield — How to turn this code into an app on your phone

You have the complete source code for the **Secure Shield** Android app. Code is not
yet an app you can tap — it has to be **built** (compiled) into an `.apk` file, which
is the kind of file Android installs. This guide shows you three ways, slowest-to-set-up
but easiest first. **You do not need to understand the code to do any of this.**

Pick ONE path.

---

## Path A — Easiest: build in the cloud with GitHub (no software to install)

This uses a free service that builds the app **for you** on the internet, then hands you
the finished `.apk`. Good if you don't want to install anything on a computer.

1. Make a free account at **https://github.com**.
2. Click the **+** (top right) → **New repository**. Give it a name like `secure-shield`.
   Set it to **Private** if you like. Click **Create repository**.
3. On the new repository page, click **uploading an existing file**.
4. On your computer, unzip the `SecureShield.zip` I gave you. Drag **everything inside**
   the unzipped folder into the GitHub upload page. Wait for it to finish, then click
   **Commit changes**.
5. A file called `.github/workflows/build.yml` is already included. GitHub sees it and
   **automatically starts building**. Click the **Actions** tab at the top to watch it.
6. After a few minutes you'll see a green tick. Click into that run, scroll to
   **Artifacts** at the bottom, and download **SecureShield-debug-apk**.
7. Unzip that download to get **app-debug.apk**. Copy it to your phone (email it to
   yourself, or use a USB cable or Google Drive).
8. On your phone, tap the `.apk`. Android will ask permission to "install unknown apps" —
   allow it for your file manager or browser, then tap **Install**.

Done. Secure Shield is now on your phone.

> Note: it installs as a "debug" app, which is perfect for your own use. To put it on the
> Google Play Store you'd need a paid developer account and a signed "release" build — not
> needed just to use it yourself.

---

## Path B — Most control: Android Studio (free, on a computer)

This is the official tool. It's a big download but it does everything for you.

1. Download **Android Studio** (free) from **https://developer.android.com/studio** and
   install it. Open it once and let it finish its first-time setup (it downloads the
   Android tools automatically).
2. Unzip `SecureShield.zip`.
3. In Android Studio choose **Open**, then pick the unzipped **SecureShield** folder.
4. Wait. The bottom status bar will say "Gradle sync" and download what it needs. The
   first time can take 5–15 minutes. Let it finish. (You need to be online.)
5. To run on a **real phone**: on the phone, enable **Developer options** (Settings →
   About phone → tap "Build number" 7 times), then turn on **USB debugging**. Plug the
   phone into the computer with a USB cable and accept the prompt on the phone.
6. At the top of Android Studio pick your phone from the device dropdown, then press the
   green **▶ Run** button. The app builds and opens on your phone.
7. To get a shareable file instead: menu **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
   When it's done, click **locate** and you'll find **app-debug.apk**.

---

## Path C — Command line (if you already have the Android SDK)

If you're comfortable with a terminal and have the Android SDK installed:

```bash
# Tell Gradle where your SDK is (edit the path to yours):
echo "sdk.dir=/Users/you/Library/Android/sdk" > local.properties   # macOS
# or on Windows: echo sdk.dir=C:\\Users\\you\\AppData\\Local\\Android\\Sdk > local.properties

./gradlew assembleDebug          # macOS/Linux
gradlew.bat assembleDebug        # Windows
```

The finished app appears at:
`app/build/outputs/apk/debug/app-debug.apk`

Copy that to your phone and tap it to install.

---

## If something goes wrong

- **"Gradle sync failed" / download errors in Android Studio:** you're likely offline or
  behind a strict network. Connect to normal home Wi-Fi and try **File → Sync Project with
  Gradle Files** again.
- **The phone won't install the APK:** make sure you allowed "install unknown apps" for the
  app you're tapping the file from. This is an Android safety prompt, not an error.
- **It asks for a Google Play / developer account:** you don't need one to install your own
  debug app. That's only for publishing to the store.

Everything the app does runs **on your phone**. Your passwords, scans, and anything you
paste into the scam checkers never leave the device. The only times it uses the internet
are the clearly-labelled online features (security news, the email-breach check, the
password-breach check, and the public-IP lookup).
