<p align="right"><a href="./README.md">English</a> | <strong>中文</strong></p>

# CityGo - 智能城市旅行助手

CityGo 是一个 Android 城市步行旅行规划应用，整合行程创建、Google Maps 导航、AI 行程建议、用户偏好和本地预算记录。

> **项目状态：** 本项目是 Mobile Computing (COMP3011J) 第 04 组课程项目，用于评估和学习。当前直连第三方服务的架构仅限本地演示；请使用自己的凭据从源码构建。

## 技术栈

- Android（minSdk 24，compileSdk/targetSdk 36）和 Java 11
- Gradle / Android Gradle Plugin 8.13.1
- Google Maps、Google Places、Google Maps Android Utils
- Room、AndroidX、Material Components、ViewBinding 和 Lottie

## 本地配置与构建

需要 Android SDK Platform 36、JDK 11+，带 Google Play Services 的模拟器或真机，以及启用 Maps SDK for Android、Places API、Directions API 和 Geocoding API 的 Google Maps Platform 凭据。仅在使用 AI 行程助手时需要 DeepSeek API 密钥。

绝不提交 API 密钥。请通过环境变量或项目根目录中已被 Git 忽略的 `local.properties` 提供受限凭据：

```properties
GOOGLE_MAPS_API_KEY=replace-with-a-restricted-key
DEEPSEEK_API_KEY=replace-with-your-ai-service-key
```

编译进 Android APK 的凭据可被恢复。Android 应用限制可以保护 Maps SDK for Android 密钥，但不能保护用于直接 Directions API、Geocoding API、Places Text Search 或 Nearby Search REST 调用的密钥；应用直接调用 DeepSeek 时，其密钥同样可被恢复。

此架构仅限本地演示。生产环境必须通过可信后端代理发送 Directions、Geocoding、Places Text Search、Nearby Search 和 DeepSeek 请求。Maps SDK for Android 应使用独立密钥，并按 application ID 和签名证书限制；后端凭据应按 API 以及服务器身份或 IP（如适用）分别限制。

仓库所有者仍须撤销或轮换任何曾经嵌入的凭据，并决定如何清理 Git 历史中的凭据；本次更改不会撤销密钥或重写历史。私密报告方式见 [SECURITY.md](SECURITY.md)。

Windows：

```powershell
.\gradlew.bat assembleDebug
```

macOS/Linux：

```bash
./gradlew assembleDebug
```

在 Android Studio 中打开项目后，可使用 Run 安装调试版本。

## 从源码构建

旧的外部预构建 APK 下载建议已停用，因为早期构建产物可能包含之前嵌入的凭据。请使用自有密钥从源码进行本地构建。

## 贡献与安全

提交贡献前请阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。安全问题请按 [SECURITY.md](SECURITY.md) 私密报告。问题与功能建议请使用仓库模板。

## 开发团队

| 姓名 | 角色 | GitHub |
|:---:|:---:|:---:|
| Jiuzhou Zhu | Member | [@JojoZhu9](https://github.com/JojoZhu9) |
| Ciara Behan | Member | - |
| Eva Barrett | Member | - |

Copyright 2025 CityGo Project. All rights reserved.
