# Budsy — Nord Buds Studio

Android companion app project for OnePlus Nord Buds 3 (non-Pro), targeting Android 16.

## Current project

- Android project source is packaged in [`Budsy.zip`](./Budsy.zip).
- GitHub Actions workflow: [Build and verify Budsy Android APK](./.github/workflows/android-apk.yml).
- The workflow attempts to build a debug APK and publish it as the `Budsy-debug-apk` artifact.

## Feature status

The UI project includes Overview, Sound, Controls, and Settings navigation. Bluetooth/GATT functionality and device-specific proprietary commands still require testing against the actual Nord Buds 3 with firmware `110.110.100`. Do not assume that generic HeyMelody/Oplus SDK strings prove a feature is supported on this model.

Controls such as ANC, EQ, BassWave, game mode, battery reporting, and find-earbuds should only be marked working after command-level/device verification. No claim is made here that an APK build has passed or that proprietary controls have been verified.

## Build

Open the Android project extracted from `Budsy.zip` in Android Studio, or run the repository's GitHub Actions workflow from the Actions tab. A successful workflow should upload `Budsy-debug-apk` as a downloadable artifact.

## Device

- OnePlus Nord Buds 3 (non-Pro)
- Firmware: `110.110.100`
- Android target/testing phone: Android 16
