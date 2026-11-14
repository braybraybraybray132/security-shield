# 🛡️ Secure Shield — Mobile Security Toolbox for Android

Secure Shield is an all-in-one personal security app for Android. It checks how safe your
phone is, teaches you how scams and hacks actually work, and gives you practical tools to
protect yourself — all in plain language, and all running **on your own phone**.

> **To build and install it, read [`HOW_TO_BUILD.md`](HOW_TO_BUILD.md).** You don't need
> to be a programmer — the easiest path builds the app for you in the cloud.

---

## What's inside

### Check your security
- **Device Security Scan** — gives your phone a **1–100 safety score** from 10 real checks
  (screen lock, Android version, security patch age, encryption, root detection, USB
  debugging, sideloaded apps, accessibility misuse, device-admin apps and more). Each failed
  check comes with a plain explanation and a button that jumps to the right Settings screen.
- **App Risk Scanner** — reviews every app you installed and flags the warning signs that
  real Android malware shows (installed from outside a store, dangerous permission
  combinations, screen-reading access, hidden icons). Honest about what it can and can't do.
- **Shield AI Adviser** — reads your scan results and tells you, in priority order, exactly
  what to fix first. A rules-based expert system, not a chatbot — it runs offline.
- **Security Quiz** — 10 questions that score your security know-how out of 100 and explain
  every answer.

### Passwords
- **Password Lab** — rate any password 0–100, see roughly how long it would take to crack,
  get specific reasons it's weak, and generate strong random passwords or memorable
  passphrases. It will happily tell you when a password is rubbish.
- **Password Breach Check** — safely checks whether a password has appeared in known data
  breaches using k-anonymity (only a scrambled fragment ever leaves the phone).
- **Password Vault** — save logins (site, username, password, notes) encrypted with
  AES-256; the key lives in the phone's secure hardware (Android Keystore) and the vault is
  unlocked with your fingerprint/face/PIN. Warns you about reused and weak passwords.

### Spot scams
- **Phishing Radar** — paste a suspicious text, email or link and it highlights the tricks:
  fake look-alike links, brand impersonation, urgency and fear language, and more.
- **Card Fraud Radar** — the same idea, focused on payment and card scams.
- **Email Breach Check** — "has my email been compromised?" against known public breaches,
  with clear steps to take if it has.

### Learn
- **Threat Awareness library** — 8 in-depth, plain-language lessons: Phishing, Scam Texts,
  Card Fraud, Malware, Passwords, Public Wi-Fi, Social Engineering, and Updates & Patches.
- **Safety Tips** — quick wins you can do today.
- **Live security news** — latest **Exploits**, **Breaches**, **Scam Alerts** and
  **Android** security news, pulled live from reputable security news feeds.

### Device toolbox
- **Device Toolbox** — CPU, RAM, storage, battery, display, network, local IP, DNS and your
  public IP + rough location.
- **Benchmark & Gaming Test** — runs real CPU and memory work, scores your phone's speed,
  and estimates how well it handles games.

---

## Your privacy

Secure Shield does its work on your device. Your passwords, scan results, and anything you
paste into the scam checkers stay on the phone. The only features that use the internet are
clearly labelled and opt-in by tapping: security news, the email-breach check, the
password-breach check (which never sends your actual password), and the public-IP lookup.

## A note on honesty

This app genuinely strengthens your security through good checks, good education and good
habits. What it is **not** is a magic "antivirus" that scans files against a secret virus
database — no offline app can truly do that, and the code says so plainly where it matters.
Its malware scanner looks for the *warning signs* of bad apps, which is a real and useful
defence. For deep real-time virus protection, pair it with Google Play Protect (built into
Android) or a well-known antivirus.

## Tech, for the curious
- **Language:** Kotlin · **UI:** Jetbrains Compose (Material 3) · **Min Android:** 8.0 (API 26)
- No tracking, no ads, no accounts. Permissions are kept to the minimum and each is
  explained in `AndroidManifest.xml`.
