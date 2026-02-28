[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> 專為 Android 設計的開源 AI 助理，整合聊天、語音、視覺與影像生成工作流程。

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#quick-facts)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#prerequisites)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#prerequisites)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#license)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#prerequisites)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#prerequisites)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#prerequisites)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)

SpeakGPT 是一款進階且高度直覺的 Android 開源 AI 助理。它將現代大型語言模型（LLM）供應商與多模態工作流程（聊天、語音、圖片生成、視覺）整合到單一行動應用中。

官方支援 GPT 模型、LLAMA、MIXTRAL、GEMMA、Gemini（標準版與 Pro）Vision、DALL-E 及其他模型。

## Quick facts

| Quick facts | Details |
|---|---|
| 📱 平台 | Android（`minSdk 28`，`targetSdk 36`） |
| 🧠 核心用法 | 自備端點（BYOE）＋自備金鑰（BYOK） |
| 🧩 應用類型 | 開源 AI 用戶端（非 API 提供者） |
| 🌐 Web companion | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> 本專案是我學士論文的一部分。使用此作品時需要標示出處。Copyright (c) 2023-2025 Dmytro Ostapenko。保留所有權利。
> 
> 引用方式：Dmytro Ostapenko（2024），"Review Program Automation Using Copilot Services" Bachelor Thesis，Technical University of Košice, 2024。

> [!CAUTION]
> 
> 我們即將停止支援以下 Android 版本：9、10、11。這與近期 SDK 與安全性變更有關。較舊 Android 版本使用的是已棄用且不穩定的功能，例如 RenderScript。

## 目錄

- [下載](#下載)
- [SpeakGPT Web](#speakgpt-web)
- [概覽](#概覽)
- [螢幕截圖](#螢幕截圖)
- [想要在本應用使用 Google Gemini 模型的注意事項](#想要在本應用使用-google-gemini-模型的注意事項)
- [想要免費、低成本又輕鬆使用的人](#想要免費、低成本又輕鬆使用的人)
- [支援的 API 供應商](#支援的-api-供應商)
- [基本功能](#基本功能)
- [專案結構](#專案結構)
- [先決條件](#先決條件)
- [安裝](#安裝)
- [使用方式](#使用方式)
- [設定](#設定)
- [範例](#範例)
- [開發筆記](#開發筆記)
- [疑難排解](#疑難排解)
- [規劃路線](#規劃路線)
- [API 金鑰安全](#api-金鑰安全)
- [開發者身分](#開發者身分)
- [參與貢獻](#參與貢獻)
- [❤️ Support](#-support)
- [授權條款](#授權條款)

## 下載

📦 從 Google Play 安裝：

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 前往 SpeakGPT Web：[https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub 專案庫：[https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## 概覽

SpeakGPT 是一個以 Android 為優先的平台 AI API 用戶端，採用自備端點 + 自備金鑰的設計，讓使用者可自行選擇供應商、模型，以及成本/效能的組合。

### 一眼看懂

| 領域 | 重點 |
|---|---|
| 💬 核心體驗 | 聊天、圖片生成、圖片辨識、語音輸入、助理整合 |
| 🔌 供應商策略 | 支援 OpenAI 相容端點，可配置供應商與自訂端點 |
| 🔐 資料處理 | API 金鑰本地儲存；可匯入/匯出對話 |
| 🧱 技術架構 | 使用 AGP `8.12.2`、Gradle `8.13`、Kotlin `2.2.10` 的 Android 多模組專案 |

Repository 架構：

- `app`：Android 應用模組（`org.teslasoft.assistant`）
- `teslasoft-id`：內部 Android 函式庫模組，提供認證與客戶端工具（`org.teslasoft.core.auth`）
- 倉庫根目錄的 JSON 中繼資料（`ai_sets.json`、`explore.json`、`experiment.json`）用於模型集合、探索與匯入/匯出類型的流程
- `i18n/`：多語系 README 輸出目錄（於本儲存庫內）

## 螢幕截圖

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

## 想要在本應用使用 Google Gemini 模型的注意事項

SpeakGPT 本身不直接支援 Google API key，但你仍可透過 OpenRouter API 來使用 Google Gemini。

更多資訊：[OpenRouter Models](https://openrouter.ai/docs#models)

## 想要免費、低成本又輕鬆使用的人

> [!WARNING]
> 
> 記住，免費起司常常只在老鼠夾裡。**本應用為「原樣」提供的開源用戶端**，本身不會提供 API 供應商的高階功能與旗艦模型之免費完整存取權。如果你是為了完全白嫖他人的工作而來，建議你直接換其他方案。本專案不會回答「API key 顯示錯誤，為什麼我被導向外部站點申請金鑰？」之類問題，謝謝理解。
> 其他能夠理性使用的朋友都很歡迎。

## 支援的 API 供應商

| Provider | Support level | Notes |
|---|---|---|
| OpenAI | Full support | Primary integration path |
| GROQ | Partial support | Some features may vary |
| Azure | Partial support | Endpoint/model specifics may differ |
| OpenRouter | Text generation only | Tested with Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI models |
| Other | Community-tested | Feedback is welcome |

> [!NOTE]
> 
> 若要切換 API 供應商，請前往「設定」並選擇 API endpoint，也可新增自訂 API 供應商。

## 基本功能

✅ 已實作功能：

- [x] 聊天（預設本機儲存，必要時可匯入/匯出）
- [x] 圖片生成
- [x] 圖片辨識（搭配 ChatGPT 使用你的照片與圖片）
- [x] 啟動提示詞
- [x] 系統訊息
- [x] 語音輸入（Whisper 與 Google）
- [x] 助理
- [x] 內容選單中的 SpeakGPT
- [x] 分享表單中的 SpeakGPT
- [x] Function calling 功能
- [x] Prompts Library
- [x] 多種聊天版面
- [x] 自適應設計
- [x] 許多不同模型
- [x] 無 captcha
- [x] 按量計費機制
- [x] 新手提示
- [x] 支援自訂微調模型
- [x] AMOLED 深色模式
- [x] 支援自訂 API 供應商
- [x] 可調整 `temperature`、`topP`、`frequencyPenalty`、`presencePenalty`、`logit_bias` 等模型參數
- [x] Playground
- [x] 存取最新旗艦模型，例如 o1、o3、o4、gpt-4.1、gpt-4.5 與 gpt-image-1（部分模型可能需要你先在 OpenAI 驗證身分）

## 專案結構

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

## 先決條件

- Android Studio（建議使用目前穩定版）
- Android SDK，具備 `compileSdk 36`
- JDK 21（本專案的 source/target compatibility 為 Java 21）
- Git
- 可存取網路（用於相依套件解析與模型供應商 API）

Build system 版本資訊：

| Component | Version / Value |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## 安裝

### 1. 複製儲存庫

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. 建置 debug APK

```bash
./gradlew assembleDebug
```

### 3. 安裝至已連接的裝置或模擬器

```bash
./gradlew installDebug
```

### 4. 可選的品質檢查

```bash
./gradlew lint
```

## 使用方式

### 終端使用者流程（在應用內）

1. 從 Google Play 或本地 debug 版本安裝應用。
2. 完成 onboarding 流程。
3. 開啟 API 設定並選擇或新增你的端點/供應商。
4. 輸入 API key（存放於你自己的裝置）
5. 選擇模型，開始聊天、視覺、圖片生成或語音流程。

### 可用的 Android 整合

- 助理整合（`ASSIST` intent）
- 分享表單整合（`SEND`、`SEND_MULTIPLE` intent）
- 文字處理整合（`PROCESS_TEXT`）
- `assistant.teslasoft.org` 深層連結（`/chat`、`/prompts`、`/assistant`）

## 設定

### API 端點與供應商

- 在應用內開啟 **Settings**。
- 選擇 **API endpoint** 可在預設供應商間切換。
- 若你的供應商相容 OpenAI，可新增自訂端點。

### 模型與生成參數

SpeakGPT 支援執行時調整下列生成參數：

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### 本機資料與安全

- 對話保留在本機，且可匯入/匯出。
- 像 API key 這類敏感資料會存放在加密設定中。

### 注意事項與前提

- 倉庫中包含 `google-services.json`；若你 fork 並移除它，部分整合可能需要你提供個別設定。
- 供應商相容性會依端點實作與模型家族不同而變化。

## 範例

### 範例 1：建立 release APK

```bash
./gradlew assembleRelease
```

### 範例 2：清理重建

```bash
./gradlew clean assembleDebug
```

### 範例 3：使用 OpenRouter 的 Gemini 系列模型

1. 建立 OpenRouter API key。
2. 在 SpeakGPT 設定中選擇或新增 OpenRouter 端點。
3. 選擇能支援 Gemini 的 OpenRouter 模型。
4. 開始聊天並確認回覆是否正常產生。

## 開發筆記

- 這是一個多模組 Android 專案（`:app`、`:teslasoft-id`）。
- 在目前設定中，`debug` 與 `release` 兩種 build type 都有 `minifyEnabled true` 與 `shrinkResources true`。
- ProGuard / R8 規則檔位於：
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 內嵌網頁文件位於：
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- 本地化資源位於 `app/src/main/res/values-*`。
- i18n 輸出目錄位於 `i18n/`（語系 README 檔案會在流水線步驟中分別產生）。

## 疑難排解

| 問題 | 檢查重點 |
|---|---|
| "Incorrect API key" 或驗證失敗 | 檢查你的金鑰是否對應所選供應商有效、模型是否可用於你的帳號，以及該模型是否需要額外身份驗證。 |
| 端點/模型不符 | 若使用自訂端點，請確認符合 OpenAI 相容的請求/回應格式。可嘗試在設定中切換預設端點並重新測試。 |
| 編譯問題 | 確認已啟用 JDK 21、在 Android Studio 重新同步 Gradle、執行 `./gradlew --version` 並確認 wrapper 為 Gradle `8.13`，再重試 `./gradlew clean build`。 |
| 舊版 Android 執行問題 | 專案目前支援 `minSdk 28`（Android 9）。文件已提醒未來可能因 SDK/安全變更而停止支援 Android 9/10/11。 |

## 規劃路線

### ❌ 預計新增（歡迎在 Issues 分享想法）

- [ ] 裝置例行作業（例如設定鬧鐘或開啟應用）
- [ ] 同步聊天紀錄
- [ ] 新增模型交換入口（類似提示詞商店）
- [ ] 官方瀏覽能力（讓 GPT 模型可存取網路）

## API 金鑰安全

SpeakGPT 使用 OpenAI API 提供最佳體驗。使用 API key 比使用帳號密碼更安全；你的個人資料不能透過 API key 取得。OpenAI 提供低成本 API 存取。你的 API key 僅儲存在本機，不會與任何人共享。SpeakGPT 不會收集個人資料；它是開源程式碼，你可以自行檢視。每個版本都會在 VirusTotal 檢查。
若你有疑慮，可直接 [撤銷 API key](https://platform.openai.com/account/api-keys)，或為 SpeakGPT 使用獨立的 API key。

要保護你的 API key，請依照以下步驟：

1. 為 SpeakGPT 準備獨立的 API key。
2. 設定帳單上限。
3. 開啟使用量監控，了解資源消耗與費用。
4. 有疑慮時可隨時撤銷 API key。

> 為何在正式版本中要對程式進行混淆？
>
> 混淆與資源縮減可最佳化應用大小與效能，並增強對逆向工程或竄改的防護，也能確保像 API key 這類憑證更安全。我們可提供未混淆版本，或你也可自行編譯以確認安全性。

> [!CAUTION]
> 
> 請注意惡意軟體！你可以自行編譯並修改 SpeakGPT，但當有人提供可執行安裝檔給你時請務必小心，該版本可能夾帶惡意程式。官方版本不含惡意軟體，並透過 VirusTotal 的 60+ 防毒軟體掃描。每個發行頁面都可查看 VirusTotal 報告並比對二進位檔雜湊。

## 開發者身分

| Field | Value |
|---|---|
| Developer name | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Legal address | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Legal entity ID | 55545386 (D-U-N-S: 933739642) |
| Commercial activity license | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to the § 10 section 1 letter a) of the Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) as amended) |
| VAT ID | SK3121636045 |

（你如果要直接捐款支持這個專案，或未來專案有任何付費功能，可以透過下方資訊清楚知道資金收款方。）

## 參與貢獻

歡迎參與貢獻。

- 在 Issues 回報錯誤並附上重現步驟。
- 提出新功能需求（請用清楚的 Issue 標籤）。
- 若提交程式碼，請保持變更範圍聚焦，並附上修改原因。

## ❤️ Support

| Donate | PayPal | Stripe |
|---|---|---|
| [![Donate](https://img.shields.io/badge/Donate-LazyingArt-0EA5E9?style=for-the-badge&logo=ko-fi&logoColor=white)](https://chat.lazying.art/donate) | [![PayPal](https://img.shields.io/badge/PayPal-RongzhouChen-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/RongzhouChen) | [![Stripe](https://img.shields.io/badge/Stripe-Donate-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

### 你可以支持我

- 回報任何問題
- 幫助我繼續開發 :) 
- 提出新功能需求，記得為 Issue 加上標籤

### Buy me a coffee

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## 授權條款

本專案採用 Apache License 2.0 授權。詳情請見 [LICENSE.md](LICENSE.md)。

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
