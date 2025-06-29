# GPS Rider

**GPS Rider** is a powerful Android app and Xposed module that allows you to change your device's location system-wide, without enabling Android's mock location setting. This is ideal for testing, automation, privacy, and bypassing apps that detect or block mock locations.

---

## 📱 Features

- **System-wide fake location**: Change your device's location for all apps, without enabling mock location.
- **Start/Stop/Toggle fake location**: Control the fake location service easily.
- **Set custom location**: Enter latitude and longitude to set any location.
- **Randomize location**: Randomize your location within a specified radius for extra privacy.
- **Set accuracy**: Control the reported GPS accuracy.
- **Get current fake location**: Retrieve the current spoofed coordinates.
- **Favorites**: Save and quickly switch between favorite locations.
- **Material You UI**: Modern, beautiful, and responsive interface using Jetpack Compose.
- **Intent API**: Control the app programmatically from other apps via Intents.
- **No mock location detection**: Uses advanced Xposed hooks and anti-detection techniques to hide all traces of mock location.
- **Multi-process and system service hooks**: Works at the system level for maximum compatibility.
- **Root/Xposed required**: Works with LSPosed/EdXposed.

---

## 🛠️ How It Works

- **Xposed Hooks**: The app uses Xposed to hook into Android's `LocationManager` and `Location` classes, intercepting location requests from all apps and system services.
- **Bypass Mock Detection**: It forcibly sets `isFromMockProvider` to `false` and uses hidden APIs to prevent apps from detecting that the location is fake.
- **No Mock Location Permission Needed**: You do not need to enable "Allow mock locations" in developer settings.
- **System Service Level**: Hooks are applied at both app and system service levels for maximum reliability.
(<a href="screenshot">Screenshot</a>)

---

## 🏁 Requirements

- **Android 11 (API 30) or higher** (Tested on android 16) (minSdk = 30, targetSdk = 34)
- **Rooted device**
- **Xposed Framework** (LSPosed or EdXposed recommended)

---

## 🌍 Supported Languages

- **English** (default)
- *(You can add more by creating `values-xx` folders.)*

---

## 🚀 Installation

1. **Install LSPosed/EdXposed** on your device.
2. **Install GPS Rider APK** (see below).
3. **Enable the module in LSPosed/EdXposed Manager**.
4. **Reboot your device**.
5. **Open GPS Rider and set your desired location**.

---

## 🏗️ Building from Source

```sh
git clone https://github.com/dvhamham/GPSRider.git
cd gps-rider
./gradlew :app:assembleDebug
adb install -r app/build/outputs/apk/debug/app-debug.apk
```

---

## 📡 Intent API

You can control GPS Rider from other apps using Intents:

- **Start fake location**: `com.dvhamham.START_FAKE_LOCATION`
- **Stop fake location**: `com.dvhamham.STOP_FAKE_LOCATION`
- **Toggle fake location**: `com.dvhamham.TOGGLE_FAKE_LOCATION`
- **Set custom location**: `com.dvhamham.SET_CUSTOM_LOCATION` (extras: `latitude`, `longitude`)
- **Set accuracy**: `com.dvhamham.SET_ACCURACY` (extra: `accuracy`)
- **Randomize location**: `com.dvhamham.RANDOMIZE_LOCATION` (extra: `radius`)
- **Get status**: `com.dvhamham.GET_STATUS`
- **Get current location**: `com.dvhamham.GET_CURRENT_LOCATION`

See `IntentApiDocs.kt` and the in-app documentation for more details.

---

## ⚠️ Disclaimer

> **Use this app responsibly and only for legitimate purposes such as testing and automation. You are fully responsible for any misuse.**

---

## 👨‍💻 Author

- **Name:** Mohammed (dvhamham)
- **Solo Developer:** I worked alone on this project and put a lot of effort into it.
- **PayPal for support:** [dv.hamham@gmail.com](mailto:dv.hamham@gmail.com)

> If you liked or benefited from this project, you can support me via PayPal: dv.hamham@gmail.com

---

## 📋 License

This project is licensed under the MIT License. 
