[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Android-first、开源 AI 助手，内置聊天、语音、视觉与图像生成功能。

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#quick-facts)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#prerequisites)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#prerequisites)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#license)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#prerequisites)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#prerequisites)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#prerequisites)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)

SpeakGPT 是一款高级且非常直观的 Android 开源 AI 助手。它将现代大型语言模型（LLM）供应商与多模态工作流（聊天、语音、图像生成、视觉）整合到一个移动应用中。

官方支持 GPT、LLAMA、MIXTRAL、GEMMA、Gemini（常规版和 Pro）、DALL-E 等模型。

## 快速信息

| 快速信息 | 详情 |
|---|---|
| 📱 平台 | Android（`minSdk 28`、`targetSdk 36`） |
| 🧠 核心用法 | 自带端点 + 自带密钥 |
| 🧩 应用类型 | 开源 AI 客户端（非 API 提供方） |
| 🌐 Web 配套应用 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> 本项目是我本科论文的一部分。使用本作品需注明出处。Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
>
> 引用方式：Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> 我们即将停止支持以下 Android 版本：9、10、11。原因是近期 SDK 与安全策略变更。旧版 Android 使用了已弃用且不稳定的功能，例如 RenderScript。

## 目录

- [下载](#下载)
- [SpeakGPT Web](#speakgpt-web)
- [概览](#概览)
- [截图](#截图)
- [想在本应用使用 Google Gemini 模型的说明](#想在本应用使用-google-gemini-模型的说明)
- [希望低成本、低门槛免费试用的人](#希望低成本低门槛免费试用的人)
- [支持的 API 提供方](#支持的-api-提供方)
- [基础功能](#基础功能)
- [项目结构](#项目结构)
- [先决条件](#先决条件)
- [安装](#安装)
- [使用方法](#使用方法)
- [配置](#配置)
- [示例](#示例)
- [开发说明](#开发说明)
- [故障排查](#故障排查)
- [路线图](#路线图)
- [API 密钥安全](#api-密钥安全)
- [开发者身份](#开发者身份)
- [贡献](#贡献)
- [❤️ Support](#-support)
- [许可证](#许可证)

## 下载

📦 通过 Google Play 安装：

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 启动 SpeakGPT Web：[https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub 仓库：[https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## 概览

SpeakGPT 是一个以 Android 为优先的 AI API 客户端。它采用「自带端点 + 自带密钥」模型，用户可以自行选择服务商、模型以及成本/性能配置。

### 一览

| 范畴 | 概述 |
|---|---|
| 💬 核心体验 | 聊天、图像生成、图像识别、语音输入、助手集成 |
| 🔌 提供方策略 | OpenAI 兼容端点，可配置供应商与自定义端点 |
| 🔐 数据处理 | API 密钥本地存储；聊天支持导入/导出 |
| 🧱 技术栈 | 使用 AGP `8.12.2`、Gradle `8.13`、Kotlin `2.2.10` 的 Android 多模块项目 |

仓库架构：

- `app`：Android 应用模块（`org.teslasoft.assistant`）
- `teslasoft-id`：用于鉴权/客户端工具的内部 Android 库模块（`org.teslasoft.core.auth`）
- 仓库根目录下的 JSON 元数据文件（`ai_sets.json`、`explore.json`、`experiment.json`）用于模型集合、发现流程以及导入/导出风格的工作流
- `i18n/`：仓库中的多语言 README 输出目录

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

## 想在本应用使用 Google Gemini 模型的说明

SpeakGPT 本身不直接支持 Google API Key，但你仍可通过 OpenRouter API 使用 Google Gemini。

更多信息：[OpenRouter Models](https://openrouter.ai/docs#models)

## 希望低成本低门槛免费试用的人

> [!WARNING]
>
> 记住，免费的奶酪很可能在捕鼠器里。该应用是按“原样”提供的开源客户端。它本身不提供 API 提供方的高级功能（例如旗舰 AI 模型和特殊能力）的完全免费访问。
> 如果你来这里只想白嫖他人的工作而不付费，建议直接跳过本应用并寻找其他选择。对于“API key 错误，为什么这个应用重定向我到外部网站获取 API key？”这类问题，我不会回答。感谢理解。
> 其他正常使用的朋友，欢迎。

## 支持的 API 提供方

| 提供方 | 支持级别 | 说明 |
|---|---|---|
| OpenAI | 完整支持 | 主要集成路径 |
| GROQ | 部分支持 | 部分功能可能有差异 |
| Azure | 部分支持 | 端点/模型细节可能不同 |
| OpenRouter | 仅文本生成 | 已使用 Gemini、Claude、Perplexity、Llama、Gemma、Mistral、OpenAI 模型测试 |
| 其他 | 社区测试 | 欢迎反馈 |

> [!NOTE]
>
> 要更改 API 提供方，请前往设置并选择 API 端点。你也可以添加自定义的 API 提供方。

## 基础功能

✅ 已实现的能力：

- [x] 聊天（本地保存，可按需导入/导出）
- [x] 图像生成
- [x] 图像识别（可将图片和照片与 ChatGPT 一起使用）
- [x] 激活提示词
- [x] 系统消息
- [x] 语音输入（Whisper 与 Google）
- [x] 助手
- [x] 上下文菜单中的 SpeakGPT
- [x] 分享表单中的 SpeakGPT
- [x] Function calling 功能
- [x] 提示词库
- [x] 多种聊天布局
- [x] 自适应设计
- [x] 大量不同模型
- [x] 无验证码
- [x] 按量计费系统
- [x] 新手提示
- [x] 支持自定义微调模型
- [x] AMOLED 黑暗模式
- [x] 自定义 API 提供方支持
- [x] 自定义模型参数，如 `temperature`、`topP`、`frequencyPenalty`、`presencePenalty` 和 `logit_bias`
- [x] PlayGround
- [x] 可访问最新旗舰模型（如 o1、o3、o4、gpt-4.1、gpt-4.5 和 gpt-image-1；部分模型可能需要你在 OpenAI 完成身份验证）

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
- Android SDK（含 `compileSdk 36`）
- JDK 21（项目 source/target 兼容性为 Java 21）
- Git
- 依赖解析和模型供应商 API 访问需要网络

仓库配置中的构建信息：

| 组件 | 版本 / 值 |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin 插件 | `2.2.10` |
| Gradle wrapper | `8.13` |
| 应用包名 | `org.teslasoft.assistant` |
| 最低 SDK | `28` |
| 目标 SDK | `36` |

## 安装

### 1. 克隆仓库

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. 构建调试 APK

```bash
./gradlew assembleDebug
```

### 3. 安装到已连接设备/模拟器

```bash
./gradlew installDebug
```

### 4. 可选的质量检查

```bash
./gradlew lint
```

## 使用方法

### 终端用户流程（应用内）

1. 从 Google Play 或本地调试构建安装应用。
2. 完成引导流程。
3. 打开 API 设置并选择或添加你的端点/供应商。
4. 输入 API Key（本地保存在你的设备）。
5. 选择模型并开始聊天、视觉、图像生成或语音流程。

### 可用的 Android 集成

- 助手集成（`ASSIST` intent）
- 分享面板集成（`SEND` 与 `SEND_MULTIPLE` intents）
- 文本处理集成（`PROCESS_TEXT`）
- `assistant.teslasoft.org` 深链接（`/chat`、`/prompts`、`/assistant`）

## 配置

### API 端点与供应方

- 在应用中打开 **设置**。
- 选择 **API endpoint** 以切换预配置的供应方。
- 如果你的供应方兼容 OpenAI，可添加自定义端点。

### 模型与生成参数

SpeakGPT 支持在运行时调整以下生成参数：

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### 本地数据与安全

- 会话记录保存在本地，可导入/导出。
- 像 API key 这类敏感值会存储于加密偏好。

### 说明与假设

- 仓库中包含 `google-services.json`；如果你 Fork 并移除了它，部分集成功能可能需要你自行配置。
- 供应方兼容性可能因端点实现和模型家族而异。

## 示例

### 示例 1：构建 release APK

```bash
./gradlew assembleRelease
```

### 示例 2：清理并重建

```bash
./gradlew clean assembleDebug
```

### 示例 3：通过 OpenRouter 使用 Gemini 系列模型

1. 创建 OpenRouter API Key。
2. 在 SpeakGPT 设置中选择/添加 OpenRouter 端点。
3. 选择支持 Gemini 的 OpenRouter 模型。
4. 开始对话并验证响应是否正常。

## 开发说明

- 这是一个多模块 Android 项目（`:app`、`:teslasoft-id`）。
- 当前配置中，`debug` 与 `release` 构建类型都启用了 `minifyEnabled true` 和 `shrinkResources true`。
- ProGuard/R8 规则位于：
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 嵌入式网页文档位于：
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- 本地化资源位于 `app/src/main/res/values-*`。
- README i18n 输出目录位于 `i18n/`（各语言 README 文件由流水线步骤分别生成）。

## 故障排查

| 问题 | 排查项 |
|---|---|
| “API key 错误”或鉴权失败 | 确认你的密钥对所选供应方有效，确认你所选模型对账户可用，并检查该供应方是否对旗舰模型有额外验证要求。 |
| 端点/模型不匹配 | 若使用自定义供应方端点，请确保兼容 OpenAI 的请求/响应格式。可尝试在设置中切换端点预设并重新测试。 |
| 构建问题 | 确认使用 JDK 21，先在 Android Studio 同步 Gradle 工程，执行 `./gradlew --version` 并确认 wrapper 使用的是 Gradle `8.13`，然后重试 `./gradlew clean build`。 |
| 旧版 Android 运行问题 | 项目当前支持 `minSdk 28`（Android 9）。项目说明未来可能因 SDK / 安全变更而移除 Android 9/10/11 支持。 |

## 路线图

### ❌ 计划新增（欢迎在 Issue 中提出你的想法）

- [ ] 设备例程（如设置闹钟或打开应用）
- [ ] 聊天历史同步
- [ ] 添加类似提示词商店的模型交流入口
- [ ] 官方联网能力（让 GPT 类模型可访问互联网）

## API 密钥安全

SpeakGPT 使用 OpenAI API 为你提供最佳体验。与账号密码相比，使用 API key 更安全。个人信息无法通过 API key 获取。OpenAI 提供了低价的 API 访问。你的 API key 本地保存在设备上，不会共享给任何人。SpeakGPT 不会收集任何个人数据。该应用开源，你可自行查看代码。每个发布版本都会在 VirusTotal 上检查。
如果你有任何担忧，可以选择 [撤销你的 API key](https://platform.openai.com/account/api-keys) 或为 SpeakGPT 使用独立密钥。

要安全管理你的 API key，请按以下步骤操作：

1. 为 SpeakGPT 准备独立的 API key。
2. 设置计费上限。
3. 启用用量监控，以便查看 SpeakGPT 的资源使用量和花费。
4. 若仍有担忧，可撤销你的 API key。

> 为什么我们在正式版本中混淆代码？
>
> 混淆与资源裁剪可优化应用体积与性能，并增强逆向工程和篡改防护，确保你的 API key 等凭据安全。你可以要求提供未混淆构建，或自行编译以验证安全性。

> [!CAUTION]
>
> 请注意防范恶意软件！你可以自行编译和修改 SpeakGPT，但请谨慎安装他人提供的构建版本。此类构建可能包含恶意代码。官方构建不含任何恶意软件，并且每个发布页面都会通过 VirusTotal 检测，采用 60 多个杀毒引擎。你可在每个发布页面查看 VirusTotal 报告，并比对二进制文件哈希。

## 开发者身份

| 字段 | 数值 |
|---|---|
| 开发者名称 | Dmytro Ostapenko (AndraxDev) |
| 联系方式 | dostapenko82@gmail.com, +421951829517 |
| 法定地址 | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| 法人识别码 | 55545386 (D-U-N-S: 933739642) |
| 商业活动许可 | OU-KE-OZP1-2023/031005-2（依据《商贸许可法》第455/1991号法典第10条第1款a项，于2023年6月14日签发） |

（如果你决定经济支持本项目，或未来项目出现付费功能，可从这里确认资金去向。）

## 贡献

欢迎提交贡献。

- 在 Issue 中提交 bug，并提供复现步骤。
- 提出新功能请求（请使用明确的标签/标记）。
- 如果提交代码，请保持变更范围清晰并给出说明。

## ❤️ Support

| Donate | PayPal | Stripe |
|---|---|---|
| [![Donate](https://img.shields.io/badge/Donate-LazyingArt-0EA5E9?style=for-the-badge&logo=ko-fi&logoColor=white)](https://chat.lazying.art/donate) | [![PayPal](https://img.shields.io/badge/PayPal-RongzhouChen-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/RongzhouChen) | [![Stripe](https://img.shields.io/badge/Stripe-Donate-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

### 我希望你能帮忙

- 反馈任何 bug
- 支持我 :)
- 提交新功能需求，记得给 issue 打上标签

### 请我喝杯咖啡

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## 许可证

本项目使用 Apache License 2.0 授权。详见 [LICENSE.md](LICENSE.md)。

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
