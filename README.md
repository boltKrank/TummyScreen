# Tummy Screen — Android 6+ (Kotlin)

An offline, landscape, immersive video player for the Optus X Smart 5056I or other Android 6+ phones.

## Add your videos

1. Copy `tummy_01.mp4`, `tummy_02.mp4`, etc. to `app/src/main/res/raw/`.
2. Use **Build > Make Project** or **Run** in Android Studio. The app detects clips automatically; no code edits needed. File names must be lowercase and use underscores as shown, numbered 01 through 99.
3. Connect the phone with USB debugging and press **Run**, or install a debug APK with `adb install -r app/build/outputs/apk/debug/app-debug.apk`.

Videos are packaged in the APK. If you add or replace one, rebuild/reinstall.

## Behaviour

- Landscape fullscreen; navigation controls hidden (swipe inward from edge to reveal).
- Each clip loops until you tap the display, then the next clip starts.
- Screen kept awake while activity is shown.
- App brightness set to 25% (adjust the `screenBrightness = 0.25f` value in MainActivity.kt).
- Audio plays normally; uncomment `player.setVolume(0f, 0f)` in MainActivity.kt to mute.
- No network or storage permissions, trackers, or background services.

## Build

Open this folder in Android Studio, let Gradle sync, and install Android SDK Platform 35 and JDK 17 if prompted. Uses Android Gradle Plugin 8.6.1, Kotlin 2.0.21, minimum Android SDK 23 (Android 6). A Gradle wrapper is **not bundled**; Android Studio can use its configured Gradle installation or generate a wrapper with Gradle 8.7.

Recommended video: 1280x720 or less, H.264 video, AAC audio, MP4 container at 24/30 fps. This makes hardware video decoding more likely on the older phone. Large videos increase APK size.

## Safety

Use airplane mode and test battery life / temperature with the phone in a similar fabric pocket **off-body** before wearing. Keep it removable and ventilated. Never use a swollen battery. Avoid charging while worn.
