[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Android 优先的开源 AI 助手，集成了聊天、语音、视觉和图像生成工作流。

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#快速信息)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#先决条件)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#先决条件)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#许可证)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#先决条件)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#先决条件)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#先决条件)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)
[![Translations](https://img.shields.io/badge/Translations-11-2563EB?style=flat-square&logo=googletranslate&logoColor=white)](#目录)
[![Contributions](https://img.shields.io/badge/Contributions-Welcome-10B981?style=flat-square&logo=github&logoColor=white)](#贡献)
[![Support](https://img.shields.io/badge/Support-Open%20in%202%20clicks-EC4899?style=flat-square&logo=ko-fi&logoColor=white)](#-support)

| ✅ 内容 | 🔗 链接 |
|---|---|
| 安装 Android 应用 | [Google Play](https://play.google.com/store/apps/details?id=org.teslasoft.assistant) |
| 使用 Web 伴生站点 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |
| 查看 Issue | [GitHub Issues](https://github.com/AndraxDev/speak-gpt/issues) |
| 阅读其他语言文档 | [i18n/](i18n/) |

---

SpeakGPT 是一款先进且直观的 Android 开源 AI 助手。它在单一应用中统一了多模态 AI 场景（聊天、语音、图像生成与视觉识别），并支持 OpenAI 兼容接口的多模型接入。

官方支持 GPT、LLAMA、MIXTRAL、GEMMA、Gemini（常规版与 Pro）Vision、DALL-E 以及其他模型家族。

## 快速信息

| 快速信息 | 详情 |
|---|---|
| 📱 平台 | Android（`minSdk 28`，`targetSdk 36`） |
| 🧠 核心方式 | 自带端点 + 自带密钥 |
| 🧩 应用类型 | 开源 AI 客户端（非 API 提供方） |
| 🌐 Web 伴生站点 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> 本项目是我本科毕业论文的一部分。使用本作品时需注明出处。Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
> 
> 引用方式：Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> 由于 SDK 与安全机制变更，计划停止支持 Android 9、10、11。较旧版本依赖的 API（例如 RenderScript）已被弃用。

## 目录

- [下载](#下载)
- [SpeakGPT Web](#speakgpt-web)
- [概览](#概览)
- [截图](#截图)
- [想在本应用中使用 Google Gemini 模型的说明](#想在本应用中使用-google-gemini-模型的说明)
- [想低成本低门槛免费使用的人](#想低成本低门槛免费使用的人)
- [支持的 API 提供方](#支持的-api-提供方)
- [核心功能](#核心功能)
- [项目结构](#项目结构)
- [先决条件](#先决条件)
- [安装](#安装)
- [使用](#使用)
- [配置](#配置)
- [示例](#示例)
- [开发说明](#开发说明)
- [故障排查](#故障排查)
- [路线图](#路线图)
- [API Key 安全](#api-key-安全)
- [开发者身份](#开发者身份)
- [贡献](#贡献)
- [❤️ Support](#-support)
- [许可证](#许可证)

## 下载

📦 从 Google Play 安装：

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 打开 SpeakGPT Web：[https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub 仓库：[https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## 概览

SpeakGPT 为希望直接掌控 API 配置的用户提供了灵活的 provider 流程。

### 一览

| 模块 | 摘要 |
|---|---|
| 💬 核心体验 | 聊天、图像生成、图像识别、语音输入、助手集成 |
| 🔌 Provider 策略 | OpenAI 兼容端点，支持可配置 provider 与自定义端点 |
| 🔐 数据处理 | API Key 本地存储；对话记录可导入/导出 |
| 🧱 技术栈 | 使用 AGP `8.12.2`、Gradle `8.13`、Kotlin `2.2.10` 的 Android 多模块项目 |

仓库架构：

- `app`：Android 应用模块（`org.teslasoft.assistant`）
- `teslasoft-id`：用于鉴权与客户端工具链的内部 Android 库模块（`org.teslasoft.core.auth`）
- 仓库根目录的 JSON 元数据（`ai_sets.json`、`explore.json`、`experiment.json`）用于模型集合、发现与工作流元数据
- `i18n/`：多语言文档目录

## 截图

<div align="center">
	<img src="https://gpt.teslasoft.org/s/1.png" width="200"/>
	<img src="https://gpt.teslasoft.org/s/2.png" width="200"/>
	<img src="https://gpt.teslasoft.org/s/3.png" width="200"/>
</div>
<div align="center">
	<img src="https://gpt.teslasoft.org/s/4.png" width="200"/>
	<img src="https://gpt.teslasoft.org/s/5.png" width="200"/>
	<img src="https://gpt.teslasoft.org/s/6.png" width="200"/>
</div>

## 想在本应用中使用 Google Gemini 模型的说明

SpeakGPT 并不直接支持 Google API Key，但你可以通过 OpenRouter 使用 Gemini。

更多信息：[OpenRouter Models](https://openrouter.ai/docs#models)

## 想低成本低门槛免费使用的人

> [!WARNING]
> 
> 免费能力通常意味着一定限制。该应用是开源软件，按“当前状态”提供，不提供第三方 API 旗舰服务的完全免费高级访问。
> 
> 如果你期望几乎零成本、零门槛即可获得完整高级权限，建议直接选择其他产品。关于“API key 错误”这类问题，大多数情况下是端点或模型配置不正确，通常可通过检查配置解决。
> 
> 其余正常用途的用户仍可继续使用。

## 支持的 API 提供方

| Provider | 支持程度 | 说明 |
|---|---|---|
| OpenAI | 完整支持 | 主要集成路径 |
| GROQ | 部分支持 | 部分功能可能不一致 |
| Azure | 部分支持 | 端点和模型细节可能不同 |
| OpenRouter | 仅文本生成 | 已在 Gemini、Claude、Perplexity、Llama、Gemma、Mistral、OpenAI 模型上测试 |
| 其他 | 社区测试 | 欢迎反馈 |

> [!NOTE]
> 
> 要更换 provider，请在应用设置中选择 API endpoint。你也可以添加自定义 OpenAI 兼容端点。

## 核心功能

✅ 已实现能力：

- [x] 聊天（本地保存，可导入/导出）
- [x] 图像生成
- [x] 图像识别（可在对话中附加图片）
- [x] 激活提示词与系统消息流程
- [x] 语音输入（Whisper 与 Google）
- [x] 助手集成
- [x] 在上下文菜单中使用 SpeakGPT
- [x] 在分享面板中使用 SpeakGPT
- [x] 函数调用功能
- [x] 提示词库
- [x] 多种聊天布局
- [x] 自适应界面
- [x] 覆盖大量模型
- [x] 无验证码
- [x] 按量计费（Pay-as-you-go）
- [x] 新手引导与入门提示
- [x] 微调/自定义模型支持
- [x] AMOLED 深色模式
- [x] 自定义 API provider 支持
- [x] 模型参数自定义（`temperature`、`topP`、`frequencyPenalty`、`presencePenalty`、`logit_bias`）
- [x] Playground
- [x] 可接入最新版旗舰模型，如 o1、o3、o4、gpt-4.1、gpt-4.5、gpt-image-1

## 项目结构

```text
speak-gpt/
├── README.md
├── LICENSE.md
├── build.gradle
├── settings.gradle
├── gradle.properties
├── gradle/wrapper/gradle-wrapper.properties
├── gradlew / gradlew.bat
├── app/
│   ├── build.gradle
│   ├── google-services.json
│   ├── proguard-rules.pro
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── java/org/teslasoft/assistant/...
│       ├── assets/www/
│       └── res/
├── teslasoft-id/
│   ├── build.gradle
│   ├── proguard-rules.pro
│   └── src/main/
├── ai_sets.json
├── explore.json
├── experiment.json
├── MainActivity_robo_script.json
├── hub-purge.sh
└── i18n/
```

## 先决条件

- Android Studio（建议使用当前稳定版）
- Android SDK（`compileSdk 36`）
- JDK 21（`sourceCompatibility`/`targetCompatibility` 与项目设置一致）
- Git
- 用于 Gradle 依赖下载与 provider API 调用的网络连接

构建系统版本信息：

| 组件 | 版本 / 取值 |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin 插件 | `2.2.10` |
| Gradle wrapper | `8.13` |
| 应用包名 | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## 安装

### 1. 克隆仓库

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. 用 Android Studio 打开

- 通过 Android Studio 打开 `build.gradle`。
- 等待 Gradle 同步完成。

### 3. 构建 debug APK

```bash
./gradlew assembleDebug
```

### 4. 安装到已连接的设备或模拟器

```bash
./gradlew installDebug
```

### 5. 可选的质量检查

```bash
./gradlew lint
```

## 使用

### 终端用户流程（应用内）

1. 从 Google Play 或本地 debug 构建安装应用。
2. 完成新手引导。
3. 打开 API 设置并选择 provider/endpoint。
4. 添加有效的 API Key（会本地保存）。
5. 选择模型并开始聊天、视觉、图像生成或语音流程。

### 可用的 Android 集成

- 助手集成（`ASSIST` intent）
- 分享面板集成（`SEND`、`SEND_MULTIPLE` intents）
- 文本处理集成（`PROCESS_TEXT`）
- `assistant.teslasoft.org` 深链（`/chat`、`/prompts`、`/assistant`）

## 配置

### API 端点与 provider

- 在应用中打开**设置**。
- 选择 **API endpoint** 以在内置 provider 间切换。
- 若你的 provider 为 OpenAI 兼容，可添加自定义 endpoint。

### 模型与生成参数

SpeakGPT 支持运行时调整：

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### 本地数据与安全

- 对话会本地存储，并支持导入/导出。
- API key 等敏感值通过加密首选项保存。

### 注意事项与假设

- 本仓库当前包含 `google-services.json`，若在 fork 中移除，部分集成可能需要等效的 Firebase/App 服务配置。
- 不同 endpoint 与模型家族的行为可能不同。

## 示例

### 构建 release APK

```bash
./gradlew assembleRelease
```

### 清理后重建

```bash
./gradlew clean assembleDebug
```

### 用 OpenRouter 使用 Gemini 家族模型

1. 创建 OpenRouter API Key。
2. 在 SpeakGPT 设置中选择/添加 OpenRouter endpoint。
3. 选择兼容 Gemini 的模型。
4. 开始对话并检验返回结果。

### 完整清理构建

```bash
./gradlew clean build
```

## 开发说明

- 这是一个多模块 Android 项目（`:app`、`:teslasoft-id`）。
- 当前配置下 `debug` 与 `release` 均开启 `minifyEnabled true` 与 `shrinkResources true`。
- ProGuard/R8 规则位于：
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 内置 Web 文档位于：
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- 本地化字符串位于 `app/src/main/res/values-*`。
- 各语言 README 存放于 `i18n/`。

## 故障排查

| 问题 | 检查项 |
|---|---|
| API Key 错误 / 鉴权失败 | 核对 key 是否有效、provider 兼容性与模型是否可用。部分旗舰模型需额外账户验证。 |
| Endpoint 或模型不匹配 | 检查自定义 endpoint 是否符合 OpenAI 兼容请求/响应格式。可尝试更换设置中的 endpoint 预设后重试。 |
| 构建失败 | 确认使用 JDK 21、重新同步 Gradle，并使用 `./gradlew --version` 检查 wrapper 为 `8.13`，再执行 `./gradlew clean build`。 |
| 旧版 Android 运行问题 | 项目最低 `minSdk 28`。随着支持策略变化，Android 9/10/11 的废弃警告是可预期的。 |

## 路线图

### ❌ 计划新增

- [ ] 设备自动化例程（设置闹钟或打开应用）
- [ ] 聊天历史同步
- [ ] 提示词交换/类市场流转页面
- [ ] 面向联网工作流的官方浏览与工具能力

## API Key 安全

SpeakGPT 使用 API Key 与 provider 交互，因此凭据范围更可控，也比账号密码登录更安全。

- API key 在设备本地存储，不会被应用共享。
- 可随时在 provider 控制台吊销密钥。
- 若愿意，可使用仅限 SpeakGPT 的专用密钥。

安全提醒：

1. 为 SpeakGPT 使用单独的 API Key。
2. 设置计费额度上限。
3. 开启使用监控以控制成本。
4. 发现异常使用时立即吊销 key。

为何进行混淆发布：

混淆和资源收缩有助于减少安装包体积、提升性能，并降低凭据处理的逆向工程风险。你可以请求未混淆构建或自行编译。

> [!CAUTION]
> 
> 请勿安装不可信来源的构建包。第三方构建可能被篡改并注入恶意软件。官方构建会经过 VirusTotal 校验，并通过官方渠道发布。

## 开发者身份

| 字段 | 内容 |
|---|---|
| 开发者姓名 | Dmytro Ostapenko (AndraxDev) |
| 联系方式 | dostapenko82@gmail.com, +421951829517 |
| 法律地址 | Južná trieda 4B, 04001 Košice, Slovakia |
| 法人身份识别号 | 55545386 (D-U-N-S: 933739642) |
| 营业执照 | OU-KE-OZP1-2023/031005-2（依据《商业执照法》第455/1991号法第10(1)(a)条，于2023年6月14日签发） |
| 增值税号 | SK3121636045 |

（用于你决定为项目捐赠，或未来出现付费功能时核对收款信息。）

## 贡献

欢迎贡献。

- 在 Issues 中提交问题，并提供复现步骤。
- 用清晰的标题与上下文提出新功能建议。
- 保持 PR 范围明确，并附上原因和测试说明。

## 许可证

本项目采用 Apache 2.0 许可证，详见 [LICENSE.md](LICENSE.md)。

```text
Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```


## ❤️ Support

| Donate | PayPal | Stripe |
| --- | --- | --- |
| [![Donate](https://camo.githubusercontent.com/24a4914f0b42c6f435f9e101621f1e52535b02c225764b2f6cc99416926004b7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f6e6174652d4c617a79696e674172742d3045413545393f7374796c653d666f722d7468652d6261646765266c6f676f3d6b6f2d6669266c6f676f436f6c6f723d7768697465)](https://chat.lazying.art/donate) | [![PayPal](https://camo.githubusercontent.com/d0f57e8b016517a4b06961b24d0ca87d62fdba16e18bbdb6aba28e978dc0ea21/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f50617950616c2d526f6e677a686f754368656e2d3030343537433f7374796c653d666f722d7468652d6261646765266c6f676f3d70617970616c266c6f676f436f6c6f723d7768697465)](https://paypal.me/RongzhouChen) | [![Stripe](https://camo.githubusercontent.com/1152dfe04b6943afe3a8d2953676749603fb9f95e24088c92c97a01a897b4942/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f5374726970652d446f6e6174652d3633354246463f7374796c653d666f722d7468652d6261646765266c6f676f3d737472697065266c6f676f436f6c6f723d7768697465)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |
