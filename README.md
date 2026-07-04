<a id="english"></a>
<p align="right"><strong>English</strong> | <a href="#zh-cn">中文</a> | <a href="./README_CN.md">中文独立版</a></p>

# CityGo - Smart Travel Companion

CityGo is an Android travel planning app for building city-walk itineraries. It combines a trip planner, Google Maps based navigation, AI-assisted itinerary generation, user travel preferences, and local budget tracking in one mobile workflow.

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

- Create CityWalk plans with destination city, hotel, attraction list, start date, and trip duration.
- Generate itineraries with an AI trip assistant.
- Display map-based routes and switch between walking, driving, and transit modes.
- Track daily trip budget and add expenses during a trip.
- Store user profile details, dietary preferences, home city, currency, and daily budget.
- Persist trips, users, and expenses locally with Room.

## Tech Stack

- Language: Java
- Platform: Android
- Build system: Gradle / Android Gradle Plugin 8.13.1
- SDK: compileSdk 36, minSdk 24, targetSdk 36
- UI: AndroidX, Material Components, ViewBinding
- Maps and places: Google Maps SDK for Android, Google Places API, Google Maps Android Utils
- Storage: Room
- Animation: Lottie

## APK Download

A prebuilt APK is hosted externally:

[Download CityGo.apk from Google Drive](https://drive.google.com/file/d/17oRw_qTTKMSMIE5jjJ8eAfsoAA1IJME_/view?usp=drive_link)

## Local Setup

### Prerequisites

- Android Studio Ladybug/Koala or newer
- Android SDK Platform 36 installed
- JDK 11 or newer
- Android emulator or physical Android device with Google Play Services
- Google Maps Platform keys with the required APIs enabled:
  - Maps SDK for Android
  - Places API
  - Directions API
- DeepSeek API key if you want to use the AI itinerary assistant

### Clone and Build

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

The debug APK is generated at:

```text
app/build/outputs/apk/debug/app-debug.apk
```

### Android SDK Path

If Gradle cannot find the Android SDK, create a local-only `local.properties` file in the project root. This file is ignored by Git.

```properties
sdk.dir=C\:\\Users\\<your-user>\\AppData\\Local\\Android\\Sdk
```

### Install and Launch from the Command Line

```bash
adb install -r app/build/outputs/apk/debug/app-debug.apk
adb shell am start -n com.example.citygo/.LoginActivity
```

You can also open the project in Android Studio and use the normal Run button.

## API Key Notes

This app depends on Google Maps/Places/Directions services and an AI itinerary service. Use your own restricted keys before running or publishing a build.

- The map key is referenced from `app/src/main/res/values/google_maps_api.xml`.
- Places, route planning, and AI itinerary code also require valid service keys.
- Do not commit production secrets. Prefer ignored local configuration, Gradle properties, or CI secrets for real deployments.

## Verified Locally

- `.\gradlew.bat assembleDebug` completed successfully on Windows.
- The debug APK was installed and launched on the `Pixel_8_Pro_2` Android emulator.
- README screenshots were captured from that local run.

## Troubleshooting

- `SDK location not found`: add `local.properties` with your local Android SDK path.
- Blank map or `Locate Failed`: check emulator/device location permission, Google Play Services, internet access, and Google Maps API key restrictions.
- Gradle sync fails: confirm Android SDK Platform 36 is installed and Android Studio is using JDK 11+.
- AI itinerary generation fails: confirm the AI API key is valid and the device/emulator can reach the API endpoint.

## Project Structure

```text
app/src/main/java/com/example/citygo/
|-- LoginActivity.java
|-- PreferenceSelectionActivity.java
|-- MainActivity.java
|-- CreateTripActivity.java
|-- MapActivity.java
|-- ProfileActivity.java
|-- TripBudgetController.java
|-- RouteManager.java
|-- GoogleMapsService.java
`-- database/
```

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

# CityGo - 智能城市旅行助手

CityGo 是一款面向城市旅行和 CityWalk 场景的 Android 应用。它把行程创建、地图导航、AI 行程生成、用户偏好和旅行预算记录整合到一个移动端流程里。

> Mobile Computing (COMP3011J) - 第 04 组项目

## 应用截图

以下截图来自本地 Android 模拟器实际运行结果。

<table>
  <tr>
    <td align="center"><img src="docs/screenshots/trip-list.png" width="220" alt="行程列表"><br>行程列表</td>
    <td align="center"><img src="docs/screenshots/create-trip.png" width="220" alt="创建行程"><br>创建行程</td>
    <td align="center"><img src="docs/screenshots/map-view.png" width="220" alt="地图与预算"><br>地图与预算</td>
    <td align="center"><img src="docs/screenshots/profile.png" width="220" alt="个人资料与偏好"><br>个人资料与偏好</td>
  </tr>
</table>

## 功能亮点

- 创建 CityWalk 行程，支持目的地城市、酒店、景点列表、出发日期和旅行天数。
- 通过 AI Trip Assistant 辅助生成旅行路线。
- 基于 Google Maps 展示路线，并支持步行、驾车、公共交通模式切换。
- 支持每日预算和旅行开销记录。
- 支持个人资料、饮食偏好、常住城市、货币和每日预算设置。
- 使用 Room 在本地保存用户、行程和开销数据。

## 技术栈

- 开发语言：Java
- 平台：Android
- 构建工具：Gradle / Android Gradle Plugin 8.13.1
- SDK：compileSdk 36，minSdk 24，targetSdk 36
- UI：AndroidX、Material Components、ViewBinding
- 地图与地点：Google Maps SDK for Android、Google Places API、Google Maps Android Utils
- 本地存储：Room
- 动画：Lottie

## APK 下载

预构建 APK 托管在外部链接：

[通过 Google Drive 下载 CityGo.apk](https://drive.google.com/file/d/17oRw_qTTKMSMIE5jjJ8eAfsoAA1IJME_/view?usp=drive_link)

## 本地运行

### 环境要求

- Android Studio Ladybug/Koala 或更新版本
- 已安装 Android SDK Platform 36
- JDK 11 或更新版本
- 带 Google Play Services 的 Android 模拟器或真机
- Google Maps Platform API Key，并启用：
  - Maps SDK for Android
  - Places API
  - Directions API
- 如果需要使用 AI 行程助手，需要准备 DeepSeek API Key

### 克隆与构建

```bash
git clone https://github.com/JojoZhu9/COMP3011J-CityGo.git
cd COMP3011J-CityGo
```

Windows：

```powershell
.\gradlew.bat assembleDebug
```

macOS/Linux：

```bash
./gradlew assembleDebug
```

Debug APK 输出位置：

```text
app/build/outputs/apk/debug/app-debug.apk
```

### Android SDK 路径

如果 Gradle 找不到 Android SDK，请在项目根目录创建只用于本机的 `local.properties` 文件。该文件已经被 Git 忽略。

```properties
sdk.dir=C\:\\Users\\<your-user>\\AppData\\Local\\Android\\Sdk
```

### 命令行安装并启动

```bash
adb install -r app/build/outputs/apk/debug/app-debug.apk
adb shell am start -n com.example.citygo/.LoginActivity
```

也可以直接用 Android Studio 打开项目并点击 Run。

## API Key 说明

应用依赖 Google Maps、Places、Directions 以及 AI 行程服务。运行或发布前请替换为自己的受限 API Key。

- 地图 Key 通过 `app/src/main/res/values/google_maps_api.xml` 引用。
- Places、路线规划和 AI 行程生成也需要有效的服务 Key。
- 不建议提交生产密钥。正式项目建议使用被 Git 忽略的本地配置、Gradle properties 或 CI secrets。

## 本地验证

- 已在 Windows 下执行 `.\gradlew.bat assembleDebug`，构建成功。
- 已将 debug APK 安装并启动到 `Pixel_8_Pro_2` Android 模拟器。
- README 中的截图来自该次本地运行。

## 常见问题

- `SDK location not found`：在项目根目录添加 `local.properties` 并写入本机 Android SDK 路径。
- 地图空白或出现 `Locate Failed`：检查定位权限、Google Play Services、网络连接和 Google Maps API Key 限制。
- Gradle 同步失败：确认已安装 Android SDK Platform 36，并使用 JDK 11+。
- AI 行程生成失败：检查 AI API Key 是否有效，模拟器或真机是否可以访问接口。

## 项目结构

```text
app/src/main/java/com/example/citygo/
|-- LoginActivity.java
|-- PreferenceSelectionActivity.java
|-- MainActivity.java
|-- CreateTripActivity.java
|-- MapActivity.java
|-- ProfileActivity.java
|-- TripBudgetController.java
|-- RouteManager.java
|-- GoogleMapsService.java
`-- database/
```

## 开发团队

| 姓名 | 角色 | GitHub |
|:---:|:---:|:---:|
| Jiuzhou Zhu | Member | [@JojoZhu9](https://github.com/JojoZhu9) |
| Ciara Behan | Member | - |
| Eva Barrett | Member | - |

Copyright 2025 CityGo Project. All rights reserved.
