# LiveTranslate — 100% Offline Android Translator

**LiveTranslate** converts any language to English **100% offline**, **instantly**, and **everywhere** — including **Google Chrome Incognito**, WhatsApp, YouTube, and Instagram — using an OS-level `AccessibilityService` and floating overlay bubble.

## Core Guarantees
- **100% Offline**: Powered by Google ML Kit On-Device Translation (`com.google.mlkit:translate`) and Language Identification (`com.google.mlkit:language-id`). Zero cloud APIs, zero servers. Works in Airplane Mode after one-time model download.
- **Works in Chrome Incognito**: Built at the Android OS level (`AccessibilityService` + `SYSTEM_ALERT_WINDOW`), not as a browser extension.
- **Instant**: Warm `Translator` instances + 500-entry `LruCache` for sub-second translations.
- **Private**: Nothing ever leaves your phone. No account, no login, no ads, no analytics, no tracking.

## Features
1. **Floating Translate Bubble**: Appears when you select or copy text in any app (including Chrome Incognito). Tap to see the English translation popup with **Copy**, **Listen (TTS)**, and **Close**. Drag anywhere or drag to the bottom `✕` to dismiss. Toggle ON/OFF in Settings.
2. **In-App Translator (Home)**: Auto-detects 50+ languages, instant English output, Copy, Share, and offline Text-to-Speech.
3. **Live Camera Translator**: CameraX + ML Kit Text Recognition (Latin, Devanagari, Chinese, Japanese, Korean) with live English overlays and freeze-frame toggle.
4. **Conversation Mode**: Two-way voice translation using Android's on-device `SpeechRecognizer` (API 31+) with clear fallback labeling when a device lacks an offline voice pack for a language.
5. **History & Favorites**: Room database with search, Favorites filter, delete, and Clear All.
6. **Manage Languages**: View all 50+ ML Kit languages, estimated download size, download/delete status, and Wi-Fi-only toggle.

## Setup in Android Studio
1. Open `LiveTranslate` in **Android Studio** (Ladybug / Koala or newer, JDK 17, Android SDK 34).
2. Let Gradle sync all dependencies.
3. Connect an Android phone (Android 8.0+ / API 26+) and click **Run**.

## How to Enable Floating Bubble (Required for Chrome Incognito)
On first launch, LiveTranslate shows a 3-step onboarding guide with direct buttons to system settings. You can also enable them anytime from **Settings**:
1. **Draw Over Other Apps**: Settings → *Enable* next to **Draw Over Other Apps** → allow **LiveTranslate**.
2. **Accessibility Service**: Settings → *Enable* next to **Accessibility Service** → **Installed apps** → **LiveTranslate Floating Bubble** → turn **ON**.
   - *(On Android 13/14 sideloaded APKs, if the toggle is restricted, open App Info for LiveTranslate → ⋮ menu → **Allow restricted settings**, then re-enable Accessibility).*

## Verification Checklist
- Download Hindi, Spanish, French, German, Arabic, and Tamil models in **Languages**.
- Turn on **Airplane Mode**.
- Open **Google Chrome Incognito**, select/copy a Hindi sentence → tap the floating bubble → verify instant English translation.
- Repeat inside **WhatsApp** and **YouTube** comments.
- Open **Camera** tab and point at a Spanish/Hindi sign → verify live English overlay.
