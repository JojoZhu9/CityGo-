<p align="right"><a href="./README.md">English</a> | <strong>中文</strong></p>

# CityGo - 智能城市旅行助手

CityGo 是一个 Android 城市步行旅行规划应用，整合行程创建、Google Maps 导航、AI 行程建议、用户偏好和本地预算记录。

> **项目状态：** 本项目是 Mobile Computing (COMP3011J) 第 04 组课程项目，用于评估和学习。请使用自己的受限 API 密钥；外部 APK 仅为演示便利文件，不保证可复现发布。

## 技术栈

- Android（minSdk 24，compileSdk/targetSdk 36）和 Java 11
- Gradle / Android Gradle Plugin 8.13.1
- Google Maps、Google Places、Google Maps Android Utils
- Room、AndroidX、Material Components、ViewBinding 和 Lottie

## 本地配置与构建

需要 Android SDK Platform 36、JDK 11+，以及带 Google Play Services 的模拟器或真机。

绝不提交 API 密钥。请通过环境变量或项目根目录中已被 Git 忽略的 `local.properties` 提供受限凭据：

```properties
GOOGLE_MAPS_API_KEY=replace-with-a-restricted-key
DEEPSEEK_API_KEY=replace-with-your-ai-service-key
```

Google Maps 凭据应仅启用所需 API，并限制到应用的 Android application ID 和签名证书。若密钥可能泄露，请立即轮换。私密报告方式见 [SECURITY.md](SECURITY.md)。

Windows：

```powershell
.\gradlew.bat assembleDebug
```

macOS/Linux：

```bash
./gradlew assembleDebug
```

在 Android Studio 中打开项目后，可使用 Run 安装调试版本。

## 演示 APK

[从 Google Drive 下载 CityGo.apk](https://drive.google.com/file/d/17oRw_qTTKMSMIE5jjJ8eAfsoAA1IJME_/view?usp=drive_link)

该 APK 仅用于演示便利，不代表可复现或长期支持的发布版本。

## 贡献与安全

提交贡献前请阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。安全问题请按 [SECURITY.md](SECURITY.md) 私密报告。问题与功能建议请使用仓库模板。

## 开发团队

| 姓名 | 角色 | GitHub |
|:---:|:---:|:---:|
| Jiuzhou Zhu | Member | [@JojoZhu9](https://github.com/JojoZhu9) |
| Ciara Behan | Member | - |
| Eva Barrett | Member | - |

Copyright 2025 CityGo Project. All rights reserved.
