# Setup

A clean checkout of this repository can complete the core task by following this page.

The core task: the runner puts the phone in a pocket, starts a session, and hears what to do and how the run is going until they stop.

## Prerequisites

- Android Studio with Android SDK 35, and an Android phone or emulator running Android 8 (API 26) or newer.
- JDK 17, which Android Studio installs.
- Headphones, so the spoken coach is audible with the screen covered.
- For the pocket path, a wired headset or a Bluetooth device with a media button. The emulator can use the on-screen buttons and the question field instead.

No API key is required. The shape of later configuration is [`.env.example`](../.env.example). Copy it to `.env` only if you add a value. The Week 3 app reads neither file.

## Install

1. Clone the repository and open the folder in Android Studio.
2. Let Android Studio create the Gradle wrapper if the project does not already have `gradlew`.
3. Wait for Gradle to sync.

## Configure

Grant the app microphone and location when it asks. Location is how distance and pace are measured. Without a location fix the coach says that distance is not available, and it does not invent one.

## Run the product

1. Run the `app` configuration on a device.
2. Put headphones on.
3. Start an interval session with the headset media button, or with **Start interval** on the screen. The phone says "Session started." and then "Jog."
4. Leave the screen covered. Within three minutes the phone says the elapsed time, the pace, and the distance, or that distance is not available yet.
5. Keep the interval session going past one minute. The phone says "Hard." at the first effort change. A steady session, started with **Start steady**, does not say an effort word.
6. While the session is going, ask aloud "How long have I been running?" The phone says the elapsed time. Ask something that is not time, pace, or distance. The phone does not invent a stat.
7. Press the media button again, or **Stop**. The phone says "Session stopped." and then stays quiet.

On an emulator with no microphone, type the question into the field and press **Ask**.

## Checks and tests

From the project root, after the wrapper exists:

```sh
./gradlew test
```

On Windows:

```sh
gradlew.bat test
```

The Markdown check and the link check run on GitHub for every pull request. Locally, the Markdown check is `npx markdownlint-cli2 "**/*.md"`.
