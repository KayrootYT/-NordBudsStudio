# Budsy — Nord Buds Studio

Android companion app for **OnePlus Nord Buds 3 (non-Pro)**, targeting Android 16. Target firmware for device validation: `110.110.100`.

## UI direction

- Cream/light background, orange-red gradient accents, rounded white cards.
- Premium motion and transitions, with reduced-motion/accessibility considerations.
- Four distinct bottom-navigation screens: Overview, Sound, Controls, Settings.
- Connection, scanning, loading, empty, error and disconnected states must be designed—not just the happy path.

## Feature scope

The app should expose all relevant official Nord Buds 3 features and any additional model-specific options discovered in the supplied HeyMelody APK analysis. UI visibility and actual device control are separate concerns: do not silently fake successful commands.

### Overview / connectivity

- BLE scan, device picker, connect/disconnect and reconnect handling.
- GATT service/characteristic diagnostics and exportable logs.
- Left/right/case battery and firmware/device information wherever the connected device actually exposes them.
- Bluetooth connection status and permission guidance.

### Sound

- Sound Master EQ presets: Balanced, Serenade, Bass.
- BassWave 2.0 control (20-step range if confirmed for the device firmware).
- ANC on/off and Transparency modes.
- OnePlus 3D Audio when the phone/device combination supports it.

### Controls

- Touch gesture configuration where supported.
- Dual Connection management where exposed by the official control path.
- Game Mode / low-latency option if the device API exposes it.
- Find My Earbuds only when a verified command/path is available.

### Settings / diagnostics

- Device and firmware details, supported-feature discovery, permissions, logs, and connection recovery.
- Clear per-feature states: available, unavailable on this device, requires compatible OnePlus phone, or needs device verification.
- Persistent app preferences; no false success messages for unverified proprietary commands.

## Official feature reference

OnePlus lists ANC (up to 32 dB), Transparency, BassWave 2.0, Sound Master EQ presets, Dual Connection, Google Fast Pair, Bluetooth 5.4, and OnePlus 3D Audio compatibility for this model. Feature behavior and control APIs may depend on phone, OS and firmware. See [OnePlus Nord Buds 3 official page](https://www.oneplus.in/oneplus-nord-buds-3) and [official specifications](https://www.oneplus.com/global/oneplus-nord-buds-3/specs).

## Build and verification

- Android project source is packaged in [`Budsy.zip`](./Budsy.zip).
- GitHub Actions workflow: [Build and verify Budsy Android APK](./.github/workflows/android-apk.yml).
- A successful workflow should publish `Budsy-debug-apk` as an artifact.
- Do not claim an APK build or proprietary feature is verified unless the workflow/device test has actually passed.

## Target device

- OnePlus Nord Buds 3 (non-Pro)
- Firmware `110.110.100`
- Android 16 test phone
