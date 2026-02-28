[English](README.md) · [العربية](i18n/README.ar.md) · [Español](i18n/README.es.md) · [Français](i18n/README.fr.md) · [日本語](i18n/README.ja.md) · [한국어](i18n/README.ko.md) · [Tiếng Việt](i18n/README.vi.md) · [中文 (简体)](i18n/README.zh-Hans.md) · [中文（繁體）](i18n/README.zh-Hant.md) · [Deutsch](i18n/README.de.md) · [Русский](i18n/README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Android-first, open-source AI assistant with chat, voice, vision, and image generation workflows.

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#quick-facts)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#prerequisites)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#prerequisites)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#license)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#prerequisites)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#prerequisites)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#prerequisites)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)

SpeakGPT is an advanced and highly intuitive open-source AI assistant for Android. It integrates modern large language model (LLM) providers and multimodal workflows (chat, voice, image generation, vision) into a single mobile app.

Officially it supports GPT models, LLAMA, MIXTRAL, GEMMA, Gemini (regular and pro) Vision, DALL-E and other models.

## Quick facts

| Quick facts | Details |
|---|---|
| 📱 Platform | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Core usage | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 App type | Open-source AI client (not an API provider) |
| 🌐 Web companion | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> This project is a part of my Bachelor Thesis. Attribution is required to use this work. Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
>
> Cite as: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> We are dropping support of the following Android versions soon: 9, 10, 11. It's related with recent changes in SDK and security. Older Android versions uses deprecated and unstable features like RenderScript.

## Table of contents

- [Download](#download)
- [SpeakGPT Web](#speakgpt-web)
- [Overview](#overview)
- [Screenshots](#screenshots)
- [Information for users who want to use Google Gemini models with this app](#information-for-users-who-want-to-use-google-gemini-models-with-this-app)
- [For those not-far people who want to use something for free making low or no effort](#for-those-not-far-people-who-want-to-use-something-for-free-making-low-or-no-effort)
- [API providers supported](#api-providers-supported)
- [Basic features](#basic-features)
- [Project structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Examples](#examples)
- [Development notes](#development-notes)
- [Troubleshooting](#troubleshooting)
- [Roadmap](#roadmap)
- [API key safety](#api-key-safety)
- [Developer identity](#developer-identity)
- [Contributing](#contributing)
- [❤️ Support](#-support)
- [License](#license)

## Download

📦 Install from Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Launch SpeakGPT Web: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub repo: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Overview

SpeakGPT is an Android-first client for AI APIs. It is designed around bring-your-own-endpoint and bring-your-own-key usage, so users can choose provider, model, and cost/performance profile.

### At a glance

| Area | Summary |
|---|---|
| 💬 Core experiences | Chat, image generation, image recognition, voice input, assistant integrations |
| 🔌 Provider strategy | OpenAI-compatible endpoints with configurable providers and custom endpoints |
| 🔐 Data handling | API keys stored locally; chats can be imported/exported |
| 🧱 Build stack | Android multi-module project using AGP `8.12.2`, Gradle `8.13`, Kotlin `2.2.10` |

Repository architecture:

- `app`: Android application module (`org.teslasoft.assistant`)
- `teslasoft-id`: internal Android library module for auth/client utilities (`org.teslasoft.core.auth`)
- JSON metadata at repository root (`ai_sets.json`, `explore.json`, `experiment.json`) used for model sets, discovery, and import/export style workflows
- `i18n/`: multilingual README output directory (present in repository)

## Screenshots

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

## Information for users who want to use Google Gemini models with this app

SpeakGPT does not support Google API keys itself, but you can still use Google Gemini using OpenRouter API.

More info: [OpenRouter Models](https://openrouter.ai/docs#models)

## For those not-far people who want to use something for free making low or no effort

> [!WARNING]
>
> Remember that free cheese could be only in a mousetrap. THIS APP IS OPEN-SOURCE CLIENT PROVIDED AS IS. ITSELF IT DOES NOT PROVIDE COMPLETELY FREE ACCESS TO THE PREMIUM FEATURES OF API PROVIDERS (LIKE FLAGSHIP AI MODELS AND SPECIAL FEATURES). IF YOU COME HERE TO USE OTHER'S WORK FOR FREE AND WITHOUT A CREDIT, IT'S BETTER YOU SKIP THIS APP AND LOOK FOR SOMETHING ELSE. I WILL NOT RESPOND TO YOUR "INCORRECT API KEY, WHY THIS APP REDIRECTS ME TO THE EXTERNAL SITE FOR API KEY?" QUESTIONS. THANK YOU FOR UNDERSTANDING.
> All other adequate people are welcome.

## API providers supported

| Provider | Support level | Notes |
|---|---|---|
| OpenAI | Full support | Primary integration path |
| GROQ | Partial support | Some features may vary |
| Azure | Partial support | Endpoint/model specifics may differ |
| OpenRouter | Text generation only | Tested with Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI models |
| Other | Community-tested | Feedback is welcome |

> [!NOTE]
>
> To change your API provider, go to settings and select the API endpoint. You can also add your custom API provider.

## Basic features

✅ Implemented capabilities:

- [x] Chat (saved locally but can be imported/exported if needed)
- [x] Images generation
- [x] Image recognition (use your images and photos with ChatGPT)
- [x] Activation prompt
- [x] System message
- [x] Voice input (Whisper and Google)
- [x] Assistant
- [x] SpeakGPT in context menu
- [x] SpeakGPT in Share sheet
- [x] Function calling features
- [x] Prompts Library
- [x] Different chat layout
- [x] Adaptive design
- [x] A lot of different models
- [x] No captcha
- [x] Pay as you go system
- [x] Tips for newbies
- [x] Custom fine-tuned models are supported
- [x] AMOLED dark mode
- [x] Custom API provider support
- [x] Customize model params like `temperature`, `topP`, `frequencyPenalty`, `presencePenalty` and `logit_bias`
- [x] Playground
- [x] Access to the latest flagship models like o1, o3, o4, gpt-4.1, gpt-4.5 and gpt-image-1 (Some of these models may require you to verify your identity with OpenAI)

## Project structure

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

## Prerequisites

- Android Studio (current stable recommended)
- Android SDK with `compileSdk 36`
- JDK 21 (project source/target compatibility is Java 21)
- Git
- Internet access for dependency resolution and model provider APIs

Build system facts from repo configuration:

| Component | Version / Value |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## Installation

### 1. Clone repository

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Build debug APK

```bash
./gradlew assembleDebug
```

### 3. Install to connected device/emulator

```bash
./gradlew installDebug
```

### 4. Optional quality checks

```bash
./gradlew lint
```

## Usage

### End-user flow (in app)

1. Install app from Google Play or local debug build.
2. Complete onboarding flow.
3. Open API settings and select or add your endpoint/provider.
4. Enter API key (stored locally on your device).
5. Select model and start chat, vision, image generation, or voice workflows.

### Android integrations available

- Assistant integration (`ASSIST` intent)
- Share sheet integration (`SEND` and `SEND_MULTIPLE` intents)
- Process text integration (`PROCESS_TEXT`)
- Deep links for `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Configuration

### API endpoints and providers

- Open **Settings** in app.
- Choose **API endpoint** to switch between preconfigured providers.
- Add custom endpoint if your provider is OpenAI-compatible.

### Model and generation parameters

SpeakGPT supports runtime tuning for generation settings such as:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Local data and security

- Conversations are stored locally and can be imported/exported.
- Sensitive values such as API keys are handled in encrypted preferences.

### Notes and assumptions

- `google-services.json` is present in this repository; if you fork and remove it, some integrations may require your own configuration.
- Provider compatibility can vary by endpoint implementation and model family.

## Examples

### Example 1: Build release APK

```bash
./gradlew assembleRelease
```

### Example 2: Clean rebuild

```bash
./gradlew clean assembleDebug
```

### Example 3: Use OpenRouter for Gemini-family models

1. Create OpenRouter API key.
2. In SpeakGPT settings, select/add OpenRouter endpoint.
3. Choose a Gemini-capable OpenRouter model.
4. Start a chat and verify response generation.

## Development notes

- This is a multi-module Android project (`:app`, `:teslasoft-id`).
- `debug` and `release` build types both have `minifyEnabled true` and `shrinkResources true` in current config.
- ProGuard/R8 rules are in:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- Embedded web docs are located at:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Localization resources are in `app/src/main/res/values-*`.
- README i18n output directory exists at `i18n/` (language-specific README files are generated separately in pipeline steps).

## Troubleshooting

| Issue | What to check |
|---|---|
| "Incorrect API key" or auth failures | Verify your key is valid for the selected provider, verify selected model is available to your account, and check whether provider requires additional verification for flagship models. |
| Endpoint/model mismatch | If using custom provider endpoint, ensure OpenAI-compatible request/response format. Try switching endpoint preset in settings and retest. |
| Build problems | Confirm JDK 21 is active, sync Gradle project in Android Studio, run `./gradlew --version` and verify wrapper uses Gradle `8.13`, then retry with `./gradlew clean build`. |
| Runtime issues on old Android versions | Project currently supports `minSdk 28` (Android 9). The project warns that support for Android 9/10/11 may be dropped in future due to SDK/security changes. |

## Roadmap

### ❌ Planned to add (Share your ideas in Issues)

- [ ] Device routines (like set alarm or open app)
- [ ] Sync chat history
- [ ] Add models exchange portal like prompts store
- [ ] Official browsing capabilities (make GPT AI models access the internet)

## API key safety

SpeakGPT uses OpenAI API to provide you with the best experience. Using API keys is more secure than using your username/password. Your personal info can't be obtained using API key. OpenAI provides cheap API access to their services. Your API key is stored locally on your device and is not shared with anyone. SpeakGPT does not collect any personal data. SpeakGPT is open-source and you can check the code yourself. Each release of SpeakGPT is checked on VirusTotal.
If you have any concerns you can secure either [revoke your API key](https://platform.openai.com/account/api-keys) or use a separate API key for SpeakGPT.

To secure your API key perform the following steps:

1. Make sure you have separate API key for SpeakGPT.
2. Set up billing limit.
3. Enable usage monitoring, so you can see how much resources SpeakGPT uses and how much it costs.
4. If you have any concerns you can revoke your API key.

> Why we obfuscate our code in production releases?
>
> Obfuscation and resources shrinking allows us to optimize app size, its performance and secure it against reverse engineering or tamper and make sure your credentials like API keys are in a safe place. You can request an unobfuscated build or compile it by yourself to make sure our app is safe.

> [!CAUTION]
>
> BE AWARE OF MALWARE! You are allowed to compile SpeakGPT and modify it but be very careful when someone else offers you to install their build. Such build may contain malware. Official builds do not contain any malware and are checked by more than 60 different antiviruses using VirusTotal. You can find VirusTotal report on each release page and compare the hash of the binary files.

## Developer identity

| Field | Value |
|---|---|
| Developer name | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Legal address | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Legal entity ID | 55545386 (D-U-N-S: 933739642) |
| Commercial activity license | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to the § 10 section 1 letter a) of the Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) as amended) |
| VAT ID | SK3121636045 |

(So you know where you are sending your money if you decide to support the project financially or if project will have paid features in future)

## Contributing

Contributions are welcome.

- Report bugs in Issues with reproduction steps.
- Request new features (please use clear issue tags/labels).
- If you submit code, keep changes scoped and include rationale.

## ❤️ Support

| Donate | PayPal | Stripe |
|---|---|---|
| [![Donate](https://img.shields.io/badge/Donate-LazyingArt-0EA5E9?style=for-the-badge&logo=ko-fi&logoColor=white)](https://chat.lazying.art/donate) | [![PayPal](https://img.shields.io/badge/PayPal-RongzhouChen-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/RongzhouChen) | [![Stripe](https://img.shields.io/badge/Stripe-Donate-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

### You are appreciated to

- Report any bugs
- Support me :)
- Request new features. Don't forget to mark issue with a tag

### Buy me a coffee

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## License

This project is licensed under Apache License 2.0. See [LICENSE.md](LICENSE.md).

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
