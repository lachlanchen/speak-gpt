[English](README.md) · [العربية](i18n/README.ar.md) · [Español](i18n/README.es.md) · [Français](i18n/README.fr.md) · [日本語](i18n/README.ja.md) · [한국어](i18n/README.ko.md) · [Tiếng Việt](i18n/README.vi.md) · [中文 (简体)](i18n/README.zh-Hans.md) · [中文（繁體）](i18n/README.zh-Hant.md) · [Deutsch](i18n/README.de.md) · [Русский](i18n/README.ru.md)



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
[![Translations](https://img.shields.io/badge/Translations-11-2563EB?style=flat-square&logo=googletranslate&logoColor=white)](#table-of-contents)
[![Contributions](https://img.shields.io/badge/Contributions-Welcome-10B981?style=flat-square&logo=github&logoColor=white)](#contributing)
[![Support](https://img.shields.io/badge/Support-Open%20in%202%20clicks-EC4899?style=flat-square&logo=ko-fi&logoColor=white)](#-support)

| ✅ What | 🔗 Link |
|---|---|
| Install Android app | [Google Play](https://play.google.com/store/apps/details?id=org.teslasoft.assistant) |
| Use web companion | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |
| Explore issues | [GitHub Issues](https://github.com/AndraxDev/speak-gpt/issues) |
| Read translations | [i18n/](i18n/) |

---

SpeakGPT is an advanced and intuitive open-source AI assistant for Android. It unifies multiple multimodal AI experiences (chat, voice, image generation, and vision) in a single app with OpenAI-compatible providers.

Officially it supports GPT models, LLAMA, MIXTRAL, GEMMA, Gemini (regular and pro) Vision, DALL-E, and other families.

## Quick facts

| Quick facts | Details |
|---|---|
| 📱 Platform | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Core usage | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 App type | Open-source AI client (not an API provider) |
| 🌐 Web companion | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> This project is part of my Bachelor Thesis. Attribution is required to use this work. Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
> 
> Cite as: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> Android versions 9, 10, and 11 are planned for deprecation due to SDK/security changes. Older Android versions rely on deprecated APIs such as RenderScript.

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

SpeakGPT is designed around a flexible provider workflow for users who want direct control over their API stack.

### At a glance

| Area | Summary |
|---|---|
| 💬 Core experiences | Chat, image generation, image recognition, voice input, assistant integrations |
| 🔌 Provider strategy | OpenAI-compatible endpoints with configurable providers and custom endpoints |
| 🔐 Data handling | API keys stored locally; conversations can be imported/exported |
| 🧱 Build stack | Android multi-module project using AGP `8.12.2`, Gradle `8.13`, Kotlin `2.2.10` |

Repository architecture:

- `app`: Android application module (`org.teslasoft.assistant`)
- `teslasoft-id`: internal Android library module for auth/client utilities (`org.teslasoft.core.auth`)
- JSON metadata at repository root (`ai_sets.json`, `explore.json`, `experiment.json`) used for model sets, discovery, and workflow metadata
- `i18n/`: multilingual documentation directory

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

SpeakGPT does not support Google API keys directly, but you can use Gemini through OpenRouter.

More info: [OpenRouter Models](https://openrouter.ai/docs#models)

## For those not-far people who want to use something for free making low or no effort

> [!WARNING]
> 
> Free features often come with constraints. This app is open-source and provided as-is. It does not provide free premium access to third-party API flagship services.
> 
> If you expect full free premium access, it is safer to use a different product. Questions like "incorrect API key" are usually answered by checking your endpoint and model configuration. Thank you for understanding.
>
> All other legitimate users are welcome.

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
> To change provider, open app settings and select API endpoint. You can also add a custom OpenAI-compatible endpoint.

## Basic features

✅ Implemented capabilities:

- [x] Chat (saved locally, import/export supported)
- [x] Image generation
- [x] Image recognition (attach images/photos in chat)
- [x] Activation prompt and system message workflows
- [x] Voice input (Whisper and Google)
- [x] Assistant integration
- [x] SpeakGPT in context menu
- [x] SpeakGPT in share sheet
- [x] Function calling features
- [x] Prompts library
- [x] Multiple chat layouts
- [x] Adaptive design
- [x] Broad model coverage
- [x] No captcha
- [x] Pay-as-you-go usage model
- [x] New-user tips and onboarding guidance
- [x] Fine-tuned/custom model support
- [x] AMOLED dark mode
- [x] Custom API provider support
- [x] Model parameters customization (`temperature`, `topP`, `frequencyPenalty`, `presencePenalty`, `logit_bias`)
- [x] Playground
- [x] Access to latest flagship families such as o1, o3, o4, gpt-4.1, gpt-4.5, gpt-image-1

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
- JDK 21 (`sourceCompatibility`/`targetCompatibility` aligned with Java 21 in project config)
- Git
- Internet access for Gradle dependencies and provider APIs

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

### 2. Open in Android Studio

- Open `build.gradle` via Android Studio.
- Let Gradle sync complete.

### 3. Build debug APK

```bash
./gradlew assembleDebug
```

### 4. Install on a connected device/emulator

```bash
./gradlew installDebug
```

### 5. Optional quality check

```bash
./gradlew lint
```

## Usage

### End-user flow (in app)

1. Install app from Google Play or local debug build.
2. Complete onboarding flow.
3. Open API settings and choose a provider/endpoint.
4. Add a valid API key (stored locally on device).
5. Select model and start chat, vision, image generation, or voice workflows.

### Android integrations available

- Assistant integration (`ASSIST` intent)
- Share sheet integration (`SEND`, `SEND_MULTIPLE` intents)
- Text processing integration (`PROCESS_TEXT`)
- Deep links for `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Configuration

### API endpoints and providers

- Open **Settings** in app.
- Choose **API endpoint** to switch between built-in providers.
- Add a custom endpoint if your provider is OpenAI-compatible.

### Model and generation parameters

SpeakGPT supports runtime tuning for:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Local data and security

- Conversations are stored locally and can be imported/exported.
- Sensitive values such as API keys are handled through encrypted preferences.

### Notes and assumptions

- `google-services.json` exists in this repository for current builds; if removed in forks, some integrations may need equivalent Firebase/App service setup.
- Provider behavior can differ by endpoint and model family.

## Examples

### Build release APK

```bash
./gradlew assembleRelease
```

### Clean rebuild

```bash
./gradlew clean assembleDebug
```

### Use OpenRouter for Gemini-family models

1. Create OpenRouter API key.
2. In SpeakGPT settings, select/add the OpenRouter endpoint.
3. Choose a Gemini-compatible model.
4. Start chat and verify responses.

### Build a full clean run

```bash
./gradlew clean build
```

## Development notes

- This is a multi-module Android project (`:app`, `:teslasoft-id`).
- Both `debug` and `release` build types use `minifyEnabled true` and `shrinkResources true` in the current configuration.
- ProGuard/R8 rules are in:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- Embedded web docs are located at:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Localized string resources are in `app/src/main/res/values-*`.
- README translations live in `i18n/` for language variants.

## Troubleshooting

| Issue | What to check |
|---|---|
| Incorrect API key / auth failure | Confirm key validity, provider compatibility, and model availability. Some flagship models require extra account verification. |
| Endpoint or model mismatch | Validate your custom endpoint follows OpenAI-compatible request/response formats. Try changing endpoint preset in Settings and retry. |
| Build failures | Confirm JDK 21 is active, sync Gradle, and verify Gradle wrapper is `8.13` with `./gradlew --version`, then run `./gradlew clean build`. |
| Runtime issues on legacy Android | Project is at `minSdk 28`. Deprecation warnings for Android 9/10/11 are expected as support policy evolves. |

## Roadmap

### ❌ Planned additions

- [ ] Device routines (set alarm or open app)
- [ ] Sync chat history
- [ ] Prompts exchange portal / marketplace style flow
- [ ] Official browsing/tooling for internet-access workflows

## API key safety

SpeakGPT uses API keys for provider requests so credentials are scoped and safer than account/password flows.

- Your API key is stored locally and is not shared by the app.
- You can revoke keys from your provider console at any time.
- If desired, use a key dedicated to SpeakGPT.

Security reminders:

1. Keep separate API key for SpeakGPT.
2. Set up billing limits.
3. Enable usage monitoring to control cost.
4. Revoke keys whenever suspicious usage appears.

Why app releases are obfuscated:

Obfuscation and resource shrinking improve package size, performance, and reduce reverse-engineering risk around credential handling. You may request an unobfuscated build or compile it yourself.

> [!CAUTION]
> 
> Do not install builds from untrusted sources. Third-party builds can be modified to inject malware. Official builds are checked with VirusTotal and published through the official channels.

## Developer identity

| Field | Value |
|---|---|
| Developer name | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Legal address | Južná trieda 4B, 04001 Košice, Slovakia |
| Legal entity ID | 55545386 (D-U-N-S: 933739642) |
| Commercial activity license | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to § 10(1)(a) of Act No. 455/1991 Coll. on Trade Licensing, as amended) |
| VAT ID | SK3121636045 |

(So you know where you are sending your money if you decide to support the project financially or if paid features appear in the future.)

## Contributing

Contributions are welcome.

- Report bugs in Issues with reproduction steps.
- Propose new features with clear title and context.
- Keep PRs scoped and include rationale plus testing notes.

## ❤️ Support

| Donate | PayPal | Stripe |
| --- | --- | --- |
| [![Donate](https://camo.githubusercontent.com/24a4914f0b42c6f435f9e101621f1e52535b02c225764b2f6cc99416926004b7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f6e6174652d4c617a79696e674172742d3045413545393f7374796c653d666f722d7468652d6261646765266c6f676f3d6b6f2d6669266c6f676f436f6c6f723d7768697465)](https://chat.lazying.art/donate) | [![PayPal](https://camo.githubusercontent.com/d0f57e8b016517a4b06961b24d0ca87d62fdba16e18bbdb6aba28e978dc0ea21/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f50617950616c2d526f6e677a686f754368656e2d3030343537433f7374796c653d666f722d7468652d6261646765266c6f676f3d70617970616c266c6f676f436f6c6f723d7768697465)](https://paypal.me/RongzhouChen) | [![Stripe](https://camo.githubusercontent.com/1152dfe04b6943afe3a8d2953676749603fb9f95e24088c92c97a01a897b4942/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f5374726970652d446f6e6174652d3633354246463f7374796c653d666f722d7468652d6261646765266c6f676f3d737472697065266c6f676f436f6c6f723d7768697465)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

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


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)
