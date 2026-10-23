This is a fork of the official upstream project, which can be found at: [filippocalippo/StykAnimate-App](https://github.com/filippocalippo/StykAnimate-App)
Make sure to show your support to the official release!

The goal of this fork is to replace Styk's Electron foundation entirely with Tauri to make native mobile builds possible.

So far no native functionality has been ported, but the Styk **web** version runs successfully on Tauri. See the instructions below on how to try it.

## Prerequisites
1. Install Rust
2. Install Node.js 22 or higher
3. Install [Tauri prerequisites](https://v2.tauri.app/start/prerequisites/)
4. Install [Taui CLI](https://v2.tauri.app/reference/cli/) (I prefer installing the Tauri CLI using Cargo, and that's what I use in the commands below, but you can install however you prefer and substibute the beginning of the command invocation).
5. If you want to build for mobile targets, follow [Tauri's instructions for configuring for mobile targets](https://v2.tauri.app/start/prerequisites/#configure-for-mobile-targets).
6. Clone this repo
7. Navigate to the root of the repo in your terminal before executing the commands below (replace `cargo tauri` with whatever tauri cli you installed)

## Run Styk Web Version on Tauri (Desktop)
```
npm ci
npm run web:build
cargo tauri dev
```

## Run Styk Web Version on Tauri (Android)
```
npm ci
npm run web:build
cargo tauri android init
```

Make sure to connect your Android device via adb, then run:
```
cargo tauri android run
```

## Run Styk Web Version on Tauri (iOS) *UNTESTED!
```
npm ci
npm run web:build
cargo tauri ios init
cargo tauri ios dev
```