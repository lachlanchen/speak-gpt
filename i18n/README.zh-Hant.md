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

SpeakGPT 是一款進階且高度直覺的 Android 開源 AI 助理。它將現代大型語言模型（LLM）供應商與多模態工作流程（聊天、語音、圖片生成、視覺）整合到單一行動 App 中。

目前官方支援 GPT 模型、LLAMA、MIXTRAL、GEMMA、Gemini（一般版與 Pro）Vision、DALL-E 以及其他模型。

| 快速資訊 | 詳細內容 |
|---|---|
| 📱 平台 | Android（`minSdk 28`、`targetSdk 36`） |
| 🧠 核心使用方式 | 自帶端點 + 自帶金鑰 |
| 🧩 App 類型 | 開源 AI 客戶端（非 API 供應商） |
| 🌐 Web 版本 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> 本專案是我學士論文的一部分。使用本作品需標註出處。Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
>
> 引用格式：Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> 我們即將停止支援以下 Android 版本：9、10、11。這與近期 SDK 與安全性變更有關。較舊的 Android 版本使用了已棄用且不穩定的功能（例如 RenderScript）。

## 目錄

- [下載](#下載)
- [SpeakGPT Web](#speakgpt-web)
- [概覽](#概覽)
- [截圖](#截圖)
- [給想在本 App 使用 Google Gemini 模型的使用者](#給想在本-app-使用-google-gemini-模型的使用者)
- [給那些想零成本或幾乎不花力氣就免費使用的人](#給那些想零成本或幾乎不花力氣就免費使用的人)
- [支援的 API 供應商](#支援的-api-供應商)
- [基本功能](#基本功能)
- [專案結構](#專案結構)
- [先決條件](#先決條件)
- [安裝](#安裝)
- [使用方式](#使用方式)
- [設定](#設定)
- [範例](#範例)
- [開發備註](#開發備註)
- [疑難排解](#疑難排解)
- [路線圖](#路線圖)
- [API 金鑰安全](#api-金鑰安全)
- [開發者身分資訊](#開發者身分資訊)
- [貢獻](#貢獻)
- [支援](#支援)
- [請我喝杯咖啡](#請我喝杯咖啡)
- [授權條款](#授權條款)

## 下載

📦 從 Google Play 安裝：

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 啟動 SpeakGPT Web：[https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub 倉庫：[https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## 概覽

SpeakGPT 是一個以 Android 為優先的 AI API 客戶端。其設計理念為自帶端點與自帶金鑰，讓使用者可自行選擇供應商、模型，以及成本與效能配置。

倉庫架構：

- `app`：Android 應用模組（`org.teslasoft.assistant`）
- `teslasoft-id`：內部 Android 函式庫模組，用於驗證/客戶端工具（`org.teslasoft.core.auth`）
- 倉庫根目錄的 JSON 中繼資料（`ai_sets.json`、`explore.json`、`experiment.json`），用於模型集合、探索，以及匯入/匯出類型的工作流程
- `i18n/`：多語系 README 輸出目錄（已存在於倉庫）

## 截圖

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

## 給想在本 App 使用 Google Gemini 模型的使用者

SpeakGPT 本身不支援直接使用 Google API key，但你仍可透過 OpenRouter API 使用 Google Gemini。

更多資訊：[OpenRouter Models](https://openrouter.ai/docs#models)

## 給那些想零成本或幾乎不花力氣就免費使用的人

> [!WARNING]
>
> 請記住，免費的起司通常只存在於捕鼠器裡。THIS APP IS OPEN-SOURCE CLIENT PROVIDED AS IS. ITSELF IT DOES NOT PROVIDE COMPLETELY FREE ACCESS TO THE PREMIUM FEATURES OF API PROVIDERS (LIKE FLAGSHIP AI MODELS AND SPECIAL FEATURES). IF YOU COME HERE TO USE OTHER'S WORK FOR FREE AND WITHOUT A CREDIT, IT'S BETTER YOU SKIP THIS APP AND LOOK FOR SOMETHING ELSE. I WILL NOT RESPOND TO YOUR "INCORRECT API KEY, WHY THIS APP REDIRECTS ME TO THE EXTERNAL SITE FOR API KEY?" QUESTIONS. THANK YOU FOR UNDERSTANDING.
> 其他理性使用者，歡迎你們。

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
> 若要切換 API 供應商，請前往設定並選擇 API endpoint。你也可以新增自訂 API 供應商。

## 基本功能

✅ 已實作能力：

- [x] Chat（本機儲存，但可依需求匯入/匯出）
- [x] 圖片生成
- [x] 圖片辨識（可將你的圖片與照片搭配 ChatGPT 使用）
- [x] 啟動提示詞（Activation prompt）
- [x] 系統訊息（System message）
- [x] 語音輸入（Whisper 與 Google）
- [x] 助理
- [x] 內容選單中的 SpeakGPT
- [x] 分享面板中的 SpeakGPT
- [x] Function calling 功能
- [x] Prompts Library
- [x] 不同聊天版面配置
- [x] 自適應設計
- [x] 多種不同模型
- [x] 無 captcha
- [x] 按用量付費機制
- [x] 新手提示
- [x] 支援自訂微調模型
- [x] AMOLED 深色模式
- [x] 支援自訂 API 供應商
- [x] 可自訂模型參數，如 `temperature`、`topP`、`frequencyPenalty`、`presencePenalty` 與 `logit_bias`
- [x] Playground
- [x] 可使用最新旗艦模型，例如 o1、o3、o4、gpt-4.1、gpt-4.5 與 gpt-image-1（其中部分模型可能要求你先完成 OpenAI 身分驗證）

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
- 含 `compileSdk 36` 的 Android SDK
- JDK 21（專案 source/target 相容性為 Java 21）
- Git
- 可存取網際網路（用於相依套件解析與模型供應商 API）

根據倉庫設定整理的建置系統資訊：

| Component | Version / Value |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## 安裝

### 1. 複製倉庫

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. 建置 debug APK

```bash
./gradlew assembleDebug
```

### 3. 安裝到已連接裝置/模擬器

```bash
./gradlew installDebug
```

### 4. 可選的品質檢查

```bash
./gradlew lint
```

## 使用方式

### 終端使用者流程（App 內）

1. 從 Google Play 或本機 debug build 安裝 App。
2. 完成初始導覽流程。
3. 開啟 API 設定並選擇或新增你的端點/供應商。
4. 輸入 API key（儲存在你的裝置本機）。
5. 選擇模型，開始聊天、視覺、圖片生成或語音工作流程。

### 可用的 Android 整合

- 助理整合（`ASSIST` intent）
- 分享面板整合（`SEND` 與 `SEND_MULTIPLE` intents）
- 文字處理整合（`PROCESS_TEXT`）
- `assistant.teslasoft.org` 深層連結（`/chat`、`/prompts`、`/assistant`）

## 設定

### API 端點與供應商

- 在 App 中開啟 **Settings**。
- 選擇 **API endpoint** 以切換預設供應商。
- 若供應商相容 OpenAI，可新增自訂端點。

### 模型與生成參數

SpeakGPT 支援在執行時調整生成設定，例如：

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### 本機資料與安全性

- 對話會儲存在本機，並可匯入/匯出。
- API key 等敏感資料會存放在加密偏好設定中。

### 備註與假設

- 本倉庫包含 `google-services.json`；若你 fork 後移除它，部分整合功能可能需要自行設定。
- 供應商相容性會因端點實作與模型家族而有所差異。

## 範例

### 範例 1：建置 release APK

```bash
./gradlew assembleRelease
```

### 範例 2：完整清理後重建

```bash
./gradlew clean assembleDebug
```

### 範例 3：用 OpenRouter 使用 Gemini 系列模型

1. 建立 OpenRouter API key。
2. 在 SpeakGPT 設定中選擇/新增 OpenRouter 端點。
3. 選擇支援 Gemini 的 OpenRouter 模型。
4. 開始聊天並確認可正常產生回應。

## 開發備註

- 這是多模組 Android 專案（`:app`、`:teslasoft-id`）。
- 目前設定中，`debug` 與 `release` 兩種 build type 都啟用了 `minifyEnabled true` 與 `shrinkResources true`。
- ProGuard/R8 規則位於：
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 內嵌網頁文件位於：
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- 在地化資源位於 `app/src/main/res/values-*`。
- README i18n 輸出目錄位於 `i18n/`（各語言 README 會在管線步驟中分別生成）。

## 疑難排解

| Issue | What to check |
|---|---|
| "Incorrect API key" or auth failures | Verify your key is valid for the selected provider, verify selected model is available to your account, and check whether provider requires additional verification for flagship models. |
| Endpoint/model mismatch | If using custom provider endpoint, ensure OpenAI-compatible request/response format. Try switching endpoint preset in settings and retest. |
| Build problems | Confirm JDK 21 is active, sync Gradle project in Android Studio, run `./gradlew --version` and verify wrapper uses Gradle `8.13`, then retry with `./gradlew clean build`. |
| Runtime issues on old Android versions | Project currently supports `minSdk 28` (Android 9). The project warns that support for Android 9/10/11 may be dropped in future due to SDK/security changes. |

## 路線圖

### ❌ 計畫新增（歡迎在 Issues 提出你的想法）

- [ ] 裝置例行操作（例如設鬧鐘或開啟 App）
- [ ] 同步聊天紀錄
- [ ] 新增模型交換入口（類似提示詞商店）
- [ ] 官方瀏覽能力（讓 GPT AI 模型可連網）

## API 金鑰安全

SpeakGPT 使用 OpenAI API 為你提供最佳體驗。使用 API key 比使用帳號/密碼更安全。個人資訊無法透過 API key 取得。OpenAI 以低成本提供其 API 服務。你的 API key 只會儲存在你的裝置本機，不會與任何人分享。SpeakGPT 不收集任何個人資料。SpeakGPT 為開源專案，你可以自行檢視程式碼。每個 SpeakGPT 發行版本都會在 VirusTotal 上進行檢查。
若你有任何疑慮，可以[撤銷你的 API key](https://platform.openai.com/account/api-keys)，或為 SpeakGPT 使用獨立 API key。

為了保護你的 API key，請執行下列步驟：

1. 確保你為 SpeakGPT 使用獨立 API key。
2. 設定帳單上限。
3. 啟用用量監控，以便查看 SpeakGPT 使用多少資源以及花費。
4. 如有疑慮，立即撤銷你的 API key。

> Why we obfuscate our code in production releases?
>
> 混淆與資源壓縮可協助我們最佳化 App 大小與效能，並降低被逆向或竄改的風險，同時保護像 API key 這類憑證。若你需要，可要求未混淆版本，或自行編譯以驗證 App 安全性。

> [!CAUTION]
>
> 注意惡意軟體！你可以自行編譯並修改 SpeakGPT，但若他人提供其自行打包版本，請務必提高警覺。該版本可能含有惡意程式。官方版本不含惡意軟體，並透過 VirusTotal 的 60+ 防毒引擎檢查。你可在每個發行頁面找到 VirusTotal 報告，並比對二進位檔案雜湊值。

## 開發者身分資訊

| Field | Value |
|---|---|
| Developer name | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Legal address | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Legal entity ID | 55545386 (D-U-N-S: 933739642) |
| Commercial activity license | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to the § 10 section 1 letter a) of the Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) as amended) |
| VAT ID | SK3121636045 |

（若你決定以金錢支持本專案，或未來專案出現付費功能，你可以清楚知道款項收款方資訊）

## 貢獻

歡迎貢獻。

- 在 Issues 回報 bug，並提供重現步驟。
- 請求新功能（請使用清楚的 issue 標籤）。
- 若你提交程式碼，請將變更範圍保持聚焦並附上理由。

## 支援

### 你可以透過以下方式支持

- 回報任何 bug
- 支持我 :)
- 請求新功能，別忘了為 issue 加上標籤

## 請我喝杯咖啡

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## 授權條款

本專案採用 Apache License 2.0 授權。請參閱 [LICENSE.md](LICENSE.md)。

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
