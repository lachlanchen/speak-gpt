[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


# SpeakGPT

![Platform](https://img.shields.io/badge/platform-Android-brightgreen)
![Min SDK](https://img.shields.io/badge/minSdk-28-blue)
![Target SDK](https://img.shields.io/badge/targetSdk-36-blue)
![License](https://img.shields.io/badge/license-Apache--2.0-orange)
![Gradle](https://img.shields.io/badge/gradle-8.13-02303A?logo=gradle&logoColor=white)
![Kotlin](https://img.shields.io/badge/kotlin-2.2.10-7F52FF?logo=kotlin&logoColor=white)
![AGP](https://img.shields.io/badge/AGP-8.12.2-3DDC84?logo=android&logoColor=white)

<img src="https://assistant.teslasoft.org/SPEAKGPT_BANNER_ANDROID.png" style="width: 100%;"/>

SpeakGPT 是一款面向 Android 的高级、直观且开源的 AI 助手。它将现代大语言模型（LLM）提供商与多模态工作流（聊天、语音、图像生成、视觉）整合到同一个移动应用中。

官方支持 GPT 模型、LLAMA、MIXTRAL、GEMMA、Gemini（普通版与 Pro）Vision、DALL-E 及其他模型。

| 快速信息 | 详情 |
|---|---|
| 📱 平台 | Android（`minSdk 28`, `targetSdk 36`） |
| 🧠 核心使用方式 | 自带端点 + 自带 API Key |
| 🧩 应用类型 | 开源 AI 客户端（不是 API 提供商） |
| 🌐 Web 版本 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> 该项目是我本科毕业论文的一部分。使用本作品需署名。Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
>
> 引用格式：Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> 我们即将停止对以下 Android 版本的支持：9、10、11。这与近期 SDK 和安全策略变化有关。较旧的 Android 版本使用了已弃用且不稳定的特性，例如 RenderScript。

## 目录

- [下载](#下载)
- [SpeakGPT Web](#speakgpt-web)
- [概览](#概览)
- [截图](#截图)
- [给想在本应用中使用 Google Gemini 模型的用户的信息](#给想在本应用中使用-google-gemini-模型的用户的信息)
- [给那些想少付出或不付出就免费使用某些东西的人](#给那些想少付出或不付出就免费使用某些东西的人)
- [支持的 API 提供商](#支持的-api-提供商)
- [基础功能](#基础功能)
- [项目结构](#项目结构)
- [前置条件](#前置条件)
- [安装](#安装)
- [使用](#使用)
- [配置](#配置)
- [示例](#示例)
- [开发说明](#开发说明)
- [故障排查](#故障排查)
- [路线图](#路线图)
- [API Key 安全](#api-key-安全)
- [开发者身份信息](#开发者身份信息)
- [贡献](#贡献)
- [支持](#支持)
- [请我喝杯咖啡](#请我喝杯咖啡)
- [许可证](#许可证)

## 下载

📦 从 Google Play 安装：

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 启动 SpeakGPT Web：[https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub 仓库：[https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## 概览

SpeakGPT 是一个 Android 优先的 AI API 客户端。它围绕“自带端点”和“自带密钥”设计，用户可自行选择提供商、模型，以及成本/性能配置。

仓库架构：

- `app`：Android 应用模块（`org.teslasoft.assistant`）
- `teslasoft-id`：用于认证/客户端工具的内部 Android 库模块（`org.teslasoft.core.auth`）
- 仓库根目录的 JSON 元数据（`ai_sets.json`、`explore.json`、`experiment.json`），用于模型集合、发现与导入/导出类工作流
- `i18n/`：多语言 README 输出目录（仓库中已存在）

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

## 给想在本应用中使用 Google Gemini 模型的用户的信息

SpeakGPT 本身不支持 Google API Key，但你仍可以通过 OpenRouter API 使用 Google Gemini。

更多信息：[OpenRouter Models](https://openrouter.ai/docs#models)

## 给那些想少付出或不付出就免费使用某些东西的人

> [!WARNING]
>
> 请记住，免费的奶酪只会出现在捕鼠夹里。THIS APP IS OPEN-SOURCE CLIENT PROVIDED AS IS. ITSELF IT DOES NOT PROVIDE COMPLETELY FREE ACCESS TO THE PREMIUM FEATURES OF API PROVIDERS (LIKE FLAGSHIP AI MODELS AND SPECIAL FEATURES). IF YOU COME HERE TO USE OTHER'S WORK FOR FREE AND WITHOUT A CREDIT, IT'S BETTER YOU SKIP THIS APP AND LOOK FOR SOMETHING ELSE. I WILL NOT RESPOND TO YOUR "INCORRECT API KEY, WHY THIS APP REDIRECTS ME TO THE EXTERNAL SITE FOR API KEY?" QUESTIONS. THANK YOU FOR UNDERSTANDING.
> 所有其他理性用户都欢迎使用。

## 支持的 API 提供商

| Provider | Support level | Notes |
|---|---|---|
| OpenAI | Full support | Primary integration path |
| GROQ | Partial support | Some features may vary |
| Azure | Partial support | Endpoint/model specifics may differ |
| OpenRouter | Text generation only | Tested with Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI models |
| Other | Community-tested | Feedback is welcome |

> [!NOTE]
>
> 如需切换 API 提供商，请进入设置并选择 API endpoint。你也可以添加自定义 API 提供商。

## 基础功能

✅ 已实现能力：

- [x] Chat（本地保存，可按需导入/导出）
- [x] 图像生成
- [x] 图像识别（可将你的图片和照片与 ChatGPT 配合使用）
- [x] Activation prompt
- [x] System message
- [x] 语音输入（Whisper 和 Google）
- [x] Assistant
- [x] 在上下文菜单中使用 SpeakGPT
- [x] 在分享面板中使用 SpeakGPT
- [x] Function calling 功能
- [x] Prompts Library
- [x] 不同聊天布局
- [x] 自适应设计
- [x] 大量不同模型
- [x] 无验证码
- [x] 按量付费体系
- [x] 新手提示
- [x] 支持自定义微调模型
- [x] AMOLED 深色模式
- [x] 支持自定义 API 提供商
- [x] 可自定义 `temperature`、`topP`、`frequencyPenalty`、`presencePenalty` 和 `logit_bias` 等模型参数
- [x] Playground
- [x] 可访问 o1、o3、o4、gpt-4.1、gpt-4.5 和 gpt-image-1 等最新旗舰模型（其中部分模型可能要求你在 OpenAI 完成身份验证）

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

## 前置条件

- Android Studio（建议使用当前稳定版）
- 安装了 `compileSdk 36` 的 Android SDK
- JDK 21（项目 source/target 兼容 Java 21）
- Git
- 用于依赖解析和模型提供商 API 的网络访问

来自仓库配置的构建系统信息：

| 组件 | 版本 / 值 |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## 安装

### 1. 克隆仓库

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. 构建 debug APK

```bash
./gradlew assembleDebug
```

### 3. 安装到已连接设备/模拟器

```bash
./gradlew installDebug
```

### 4. 可选质量检查

```bash
./gradlew lint
```

## 使用

### 终端用户流程（应用内）

1. 从 Google Play 或本地 debug 构建安装应用。
2. 完成引导流程。
3. 打开 API 设置并选择或添加你的端点/提供商。
4. 输入 API key（本地存储在你的设备上）。
5. 选择模型并开始聊天、视觉、图像生成或语音工作流。

### 可用的 Android 集成

- Assistant 集成（`ASSIST` intent）
- Share sheet 集成（`SEND` 和 `SEND_MULTIPLE` intents）
- Process text 集成（`PROCESS_TEXT`）
- `assistant.teslasoft.org` 的深链接（`/chat`、`/prompts`、`/assistant`）

## 配置

### API endpoints 与 providers

- 在应用中打开 **Settings**。
- 选择 **API endpoint** 在预配置提供商之间切换。
- 如果你的提供商与 OpenAI 兼容，可添加自定义 endpoint。

### 模型与生成参数

SpeakGPT 支持在运行时调整以下生成设置：

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### 本地数据与安全

- 对话会存储在本地，并可导入/导出。
- API key 等敏感值通过加密偏好设置进行处理。

### 说明与假设

- 本仓库包含 `google-services.json`；如果你 fork 后移除该文件，某些集成功能可能需要你自行配置。
- 不同 endpoint 实现和模型系列的提供商兼容性可能不同。

## 示例

### 示例 1：构建 release APK

```bash
./gradlew assembleRelease
```

### 示例 2：清理后重新构建

```bash
./gradlew clean assembleDebug
```

### 示例 3：使用 OpenRouter 运行 Gemini 系列模型

1. 创建 OpenRouter API key。
2. 在 SpeakGPT 设置中选择/添加 OpenRouter endpoint。
3. 选择支持 Gemini 的 OpenRouter 模型。
4. 开始聊天并验证响应生成。

## 开发说明

- 这是一个多模块 Android 项目（`:app`、`:teslasoft-id`）。
- 在当前配置中，`debug` 与 `release` 构建类型都启用了 `minifyEnabled true` 和 `shrinkResources true`。
- ProGuard/R8 规则位于：
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 内置网页文档位于：
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- 本地化资源位于 `app/src/main/res/values-*`。
- README i18n 输出目录为 `i18n/`（各语言 README 文件在流水线步骤中单独生成）。

## 故障排查

| 问题 | 检查项 |
|---|---|
| “Incorrect API key” 或鉴权失败 | 确认你的 key 对所选提供商有效，确认所选模型对你的账号可用，并检查该提供商是否要求对旗舰模型进行额外验证。 |
| Endpoint/model 不匹配 | 若使用自定义 provider endpoint，请确保请求/响应格式与 OpenAI 兼容。尝试在设置中切换 endpoint 预设后重试。 |
| 构建问题 | 确认已启用 JDK 21，在 Android Studio 中同步 Gradle 项目，运行 `./gradlew --version` 并确认 wrapper 使用 Gradle `8.13`，然后重试 `./gradlew clean build`。 |
| 旧版 Android 上的运行时问题 | 项目当前支持 `minSdk 28`（Android 9）。项目提示由于 SDK/安全变化，未来可能会停止支持 Android 9/10/11。 |

## 路线图

### ❌ 计划添加（欢迎在 Issues 分享想法）

- [ ] 设备例程（如设置闹钟或打开应用）
- [ ] 同步聊天记录
- [ ] 增加类似 prompts 商店的模型交换门户
- [ ] 官方浏览能力（让 GPT AI 模型可访问互联网）

## API Key 安全

SpeakGPT 使用 OpenAI API 为你提供最佳体验。使用 API key 比使用用户名/密码更安全。你的个人信息无法通过 API key 获取。OpenAI 以较低成本提供其服务的 API 访问。你的 API key 仅存储在本地设备上，不会与任何人共享。SpeakGPT 不收集任何个人数据。SpeakGPT 是开源项目，你可以自行检查代码。SpeakGPT 的每个版本都会在 VirusTotal 上进行检测。
如果你有任何担忧，可以选择[吊销 API key](https://platform.openai.com/account/api-keys)，或为 SpeakGPT 单独使用一把 API key。

为保护你的 API key，请执行以下步骤：

1. 确保为 SpeakGPT 使用独立的 API key。
2. 设置账单上限。
3. 开启用量监控，以便查看 SpeakGPT 消耗了多少资源及对应成本。
4. 如有任何担忧，可吊销 API key。

> 为什么我们会在生产版本中进行代码混淆？
>
> 混淆和资源压缩可以帮助我们优化应用体积与性能，并提高其抗逆向和防篡改能力，确保你的 API key 等凭证处于更安全的状态。你可以申请未混淆构建，或自行编译以确认应用安全性。

> [!CAUTION]
>
> 小心恶意软件！你可以自行编译并修改 SpeakGPT，但如果他人提供构建包给你安装，请务必谨慎。此类构建可能包含恶意软件。官方构建不包含恶意软件，并且会通过 VirusTotal 上 60 多种不同杀毒引擎检测。你可以在每个发布页面找到 VirusTotal 报告，并比对二进制文件哈希值。

## 开发者身份信息

| Field | Value |
|---|---|
| Developer name | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Legal address | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Legal entity ID | 55545386 (D-U-N-S: 933739642) |
| Commercial activity license | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to the § 10 section 1 letter a) of the Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) as amended) |
| VAT ID | SK3121636045 |

（如果你决定在经济上支持本项目，或项目未来出现付费功能，你可以据此了解款项接收方信息）

## 贡献

欢迎贡献。

- 在 Issues 中报告 bug，并提供复现步骤。
- 请求新功能（请使用清晰的 issue 标签）。
- 如果你提交代码，请保持改动范围聚焦并附上改动理由。

## 支持

### 欢迎你

- 报告任何 bug
- 支持我 :)
- 请求新功能，别忘了给 issue 加标签

## 请我喝杯咖啡

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## 许可证

本项目采用 Apache License 2.0 许可证。详见 [LICENSE.md](LICENSE.md)。

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
