<a id="english"></a>
<p align="right"><strong>English</strong> | <a href="#zh-cn">中文</a> | <a href="./README_CN.md">中文独立版</a></p>

# CityGo - Smart Travel Companion

[![Android](https://img.shields.io/badge/Android-API%2024%2B-3DDC84?logo=android&logoColor=white)](https://developer.android.com/)
[![Java](https://img.shields.io/badge/Java-11%2B-ED8B00?logo=openjdk&logoColor=white)](https://www.java.com/)
[![Google Maps](https://img.shields.io/badge/Google%20Maps-Platform-4285F4?logo=googlemaps&logoColor=white)](https://developers.google.com/maps)
[![Room](https://img.shields.io/badge/Room-2.6.1-3DDC84)](https://developer.android.com/training/data-storage/room)
[![Rights](https://img.shields.io/badge/Rights-All%20rights%20reserved-555555)](#contributors)

CityGo is an Android travel-planning app for building city-walk itineraries. It combines trip planning, Google Maps navigation, AI-assisted itineraries, travel preferences, and local budget tracking in one mobile workflow.

> **Project status:** Course-group project maintained for evaluation and learning. The current direct-to-service architecture is for local demos only; build from source with your own credentials.

> Mobile Computing (COMP3011J) - Group 04 Project

## Screenshots

Screenshots below were captured from a local Android emulator run.

<table>
  <tr>
    <td align="center"><img src="docs/screenshots/trip-list.png" width="220" alt="Trip list"><br>Trip list</td>
    <td align="center"><img src="docs/screenshots/create-trip.png" width="220" alt="Create trip"><br>Create trip</td>
    <td align="center"><img src="docs/screenshots/map-view.png" width="220" alt="Map and budget"><br>Map and budget</td>
    <td align="center"><img src="docs/screenshots/profile.png" width="220" alt="Profile preferences"><br>Profile preferences</td>
  </tr>
</table>

## Features

- Create CityWalk plans with a destination, hotel, attractions, start date, and duration.
- Generate itineraries with an AI trip assistant.
- Display routes and switch between walking, driving, and transit modes.
- Track a daily trip budget and trip expenses.
- Store user preferences, trips, and expenses locally with Room.

## Tech Stack

- Java 11 and Android (compileSdk 36, minSdk 24, targetSdk 36)
- Gradle and Android Gradle Plugin 8.13.1
- AndroidX, Material Components, and ViewBinding
- Google Maps SDK for Android, Google Places API, and Google Maps Android Utils
- Room and Lottie

## Build from Source

The previously linked external prebuilt APK is retired because an older artifact may contain previously embedded credentials. Build the app locally from source with user-owned keys instead.

## Local Setup

### Prerequisites

- Android Studio Ladybug/Koala or newer
- Android SDK Platform 36
- JDK 11 or newer
- An Android emulator or device with Google Play Services
- Google Maps Platform credentials for Maps SDK for Android, Places API, Directions API, and Geocoding API
- A DeepSeek API key only when using the AI itinerary assistant

### Configure Credentials

Never commit API keys. Supply restricted credentials through your shell environment or an ignored `local.properties` file in the project root:

```properties
GOOGLE_MAPS_API_KEY=replace-with-a-restricted-key
DEEPSEEK_API_KEY=replace-with-your-ai-service-key
```

Credentials compiled into an Android APK are recoverable. An Android application restriction can protect a Maps SDK for Android key, but it does not protect a key used by direct Directions API, Geocoding API, Places Text Search, or Nearby Search REST calls. The DeepSeek key is likewise recoverable when the app calls DeepSeek directly.

This architecture is local-demo only. A production deployment requires a trusted backend proxy for Directions, Geocoding, Places Text Search, Nearby Search, and DeepSeek requests. Use a separate Maps SDK for Android key restricted by application ID and signing certificate, and separately restrict backend credentials by API and server identity or IP where applicable.

Repository owners still need to revoke or rotate any previously embedded credentials and decide how to remove credentials from Git history. This change does not revoke credentials or rewrite history. See [SECURITY.md](SECURITY.md) for private reporting guidance.

### Build

```bash
git clone https://github.com/JojoZhu9/COMP3011J-CityGo.git
cd COMP3011J-CityGo
```

On Windows:

```powershell
.\gradlew.bat assembleDebug
```

On macOS/Linux:

```bash
./gradlew assembleDebug
```

Open the project in Android Studio and use Run to install a debug build on an emulator or device.

## Troubleshooting

- `SDK location not found`: set `ANDROID_HOME` and `ANDROID_SDK_ROOT`, or add `sdk.dir` to the ignored `local.properties` file.
- Blank map or `Locate Failed`: check location permission, Google Play Services, network access, and Maps credential restrictions.
- Gradle sync fails: confirm Android SDK Platform 36 and JDK 11+ are selected.
- AI itinerary generation fails: confirm the AI credential is valid and the device can reach the service endpoint.

## Contributing and Security

Read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a contribution. Report vulnerabilities privately as described in [SECURITY.md](SECURITY.md). Bug reports and feature requests use the repository templates.

## Contributors

| Name | Role | GitHub |
|:---:|:---:|:---:|
| Jiuzhou Zhu | Member | [@JojoZhu9](https://github.com/JojoZhu9) |
| Ciara Behan | Member | - |
| Eva Barrett | Member | - |

Copyright 2025 CityGo Project. All rights reserved.

---

<a id="zh-cn"></a>
<p align="right"><a href="#english">English</a> | <strong>中文</strong> | <a href="./README_CN.md">中文独立版</a></p>

## 中文简介

CityGo 是 COMP3011J 第 04 组的 Android 城市步行旅行规划课程项目，提供行程规划、Google Maps 导航、AI 行程建议、偏好设置和本地预算记录。

- 本项目用于课程评估和学习，当前直连第三方服务的架构仅限本地演示，不是生产服务。
- 本地运行需要 Maps SDK for Android、Places API、Directions API 和 Geocoding API，并请使用自己的 Google Maps 与 DeepSeek 密钥，绝不提交密钥。
- APK 中用于 Directions、Geocoding、Places Text Search、Nearby Search REST 调用及 DeepSeek 的密钥均可被恢复；Android 应用限制不能保护这些 REST 调用。生产环境必须使用可信后端代理，并按用途分别限制凭据。
- 旧的外部预构建 APK 可能包含之前嵌入的凭据，下载建议已停用；请使用自有密钥从源码构建。
- 详细中文说明见 [README_CN.md](README_CN.md)。

Copyright 2025 CityGo Project. All rights reserved.
