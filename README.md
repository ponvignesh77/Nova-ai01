# ✨ Nova Assistant (Android)

Voice assistant + chatbot + draw-to-open launcher, in one small Jetpack Compose app.
It opens **any installed app directly by package name**, so no links or deep links are needed.

## Features

| Feature | What it does |
|---|---|
| 🎤 Voice | Tap the orb and say "open Instagram". It fuzzy-matches your real installed apps. |
| 💬 Chatbot | Answers from Wikipedia, plus time, date and simple math. Add an Anthropic API key in ⚙️ for full AI answers. |
| ✍️ Draw to open | Draw a shape, save it for any installed app, then redraw it to launch that app. |
| 🔊 Spoken replies | Nova reads its answers aloud with Android text-to-speech. |

## Try these

- "What time is it"
- "Open Camera"
- "Tell me about Mars"
- "12 times 8"

## Build the APK on GitHub (no Android Studio needed)

1. Create a new GitHub repository.
2. Upload **everything inside the project folder**. `.github`, `app`, `build.gradle.kts` and the other files must sit at the **repo root**.
3. Open the **Actions** tab, choose **Build APK**, and wait about 5 minutes. You can also click **Run workflow**.
4. Open the finished run and download **Nova-debug-apk** from **Artifacts**.
5. Unzip it, copy `app-debug.apk` to your phone, and install it. You may need to allow "Install unknown apps".

## Build locally

Open the folder in Android Studio and press **Run**, or run `gradle assembleDebug`.
The APK is written to `app/build/outputs/apk/debug/app-debug.apk`.

## Full AI (optional)

Tap ⚙️, paste your Anthropic API key, and press Save. The key is stored only on your device
(in app preferences) and is sent only to `api.anthropic.com`. Without a key, Nova uses Wikipedia.

## Tech stack

Kotlin 1.9 · Jetpack Compose (Material 3) · Android Gradle Plugin 8.5.2 · minSdk 26 · targetSdk 34

## Project layout

```
.github/workflows/build.yml          GitHub Actions build
app/src/main/AndroidManifest.xml
app/src/main/java/com/nova/assistant/MainActivity.kt
app/build.gradle.kts
build.gradle.kts · settings.gradle.kts · gradle.properties
```

## Troubleshooting

- **No "Build APK" workflow shown:** `.github/workflows/build.yml` is not at the repo root.
- **Build fails:** open the failed run, expand the *gradle assembleDebug* step, and read the first red error.
- **App not found by voice or draw:** the app must have a launcher icon and be installed on that phone.
- **Voice button does nothing:** the device has no speech-recognition service (install the Google app).
