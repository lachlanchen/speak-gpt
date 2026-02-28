[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> 專為 Android 打造的開源 AI 助理，整合聊天、語音、視覺與影像生成工作流程。

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#快速資訊)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#先決條件)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#先決條件)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#授權條款)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#先決條件)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#先決條件)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#先決條件)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)
[![Translations](https://img.shields.io/badge/Translations-11-2563EB?style=flat-square&logo=googletranslate&logoColor=white)](#目錄)
[![Contributions](https://img.shields.io/badge/Contributions-Welcome-10B981?style=flat-square&logo=github&logoColor=white)](#貢獻)
[![Support](https://img.shields.io/badge/Support-Open%20in%202%20clicks-EC4899?style=flat-square&logo=ko-fi&logoColor=white)](#-support)

| ✅ 項目 | 🔗 連結 |
|---|---|
| 安裝 Android 應用 | [Google Play](https://play.google.com/store/apps/details?id=org.teslasoft.assistant) |
| 使用網頁版伴侶 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |
| 查看問題與建議 | [GitHub Issues](https://github.com/AndraxDev/speak-gpt/issues) |
| 查閱其他語言說明 | [i18n/](i18n/) |

---

SpeakGPT 是一款進階且直覺的 Android 開源 AI 助理。它在單一應用中整合聊天、語音、影像生成與影像辨識等多模態 AI 體驗，並使用 OpenAI 相容的供應商與端點。

官方支援 GPT 模型、LLAMA、MIXTRAL、GEMMA、Gemini（一般版與 Pro）Vision、DALL-E，以及其他模型家族。

## 快速資訊

| 快速資訊 | 細節 |
|---|---|
| 📱 平台 | Android（`minSdk 28`、`targetSdk 36`） |
| 🧠 核心用法 | 自備端點 + 自備金鑰 |
| 🧩 應用類型 | 開源 AI 客戶端（非 API 提供方） |
| 🌐 Web 伴侶 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> 本專案是我學士論文的一部分。使用本作品需註明來源。Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
> 
> 引用方式：Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> 因應 SDK 與安全性變更，Android 9、10、11 預計將停止支援。較舊的 Android 版本依賴的 RenderScript 等 API 已被棄用。

## 目錄

- [下載](#下載)
- [SpeakGPT Web](#speakgpt-web)
- [概覽](#概覽)
- [螢幕截圖](#螢幕截圖)
- [想在本應用中使用 Google Gemini 模型的說明](#想在本應用中使用-google-gemini-模型的說明)
- [想用低成本、低門檻免費使用的方式](#想用低成本、低門檻免費使用的方式)
- [支援的 API 供應商](#支援的-api-供應商)
- [基本功能](#基本功能)
- [專案結構](#專案結構)
- [先決條件](#先決條件)
- [安裝](#安裝)
- [使用](#使用)
- [設定](#設定)
- [範例](#範例)
- [開發筆記](#開發筆記)
- [故障排解](#故障排解)
- [路線圖](#路線圖)
- [API 金鑰安全](#api-金鑰安全)
- [開發者身份](#開發者身份)
- [貢獻](#貢獻)
- [❤️ Support](#-support)
- [授權條款](#授權條款)

## 下載

📦 從 Google Play 安裝：

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 啟動 SpeakGPT Web：[https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub 儲存庫：[https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## 概覽

SpeakGPT 以彈性供應商流程設計，給希望直接掌控 API 串接與模型的人使用。

### 一覽

| 領域 | 摘要 |
|---|---|
| 💬 核心體驗 | 聊天、影像生成、影像辨識、語音輸入、助理整合 |
| 🔌 供應商策略 | OpenAI 相容端點，可設定供應商並新增自訂端點 |
| 🔐 資料處理 | API 金鑰儲存在本機；對話可匯入/匯出 |
| 🧱 技術堆疊 | 使用 AGP `8.12.2`、Gradle `8.13`、Kotlin `2.2.10` 的 Android 多模組專案 |

專案架構：

- `app`：Android 應用模組（`org.teslasoft.assistant`）
- `teslasoft-id`：內部 Android 函式庫模組，負責驗證與客戶端工具（`org.teslasoft.core.auth`）
- 倉庫根目錄 JSON 元資料（`ai_sets.json`、`explore.json`、`experiment.json`）用於模型集、探索與工作流程中繼資料
- `i18n/`：多語系文件目錄

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

## 想在本應用中使用 Google Gemini 模型的說明

SpeakGPT 不直接支援 Google API Key，但你可以透過 OpenRouter 使用 Gemini。

更多資訊：[OpenRouter Models](https://openrouter.ai/docs#models)

## 想用低成本、低門檻免費使用的方式

> [!WARNING]
> 
> 免費功能通常都有限制。此應用為開源專案，依「現況提供」提供，不提供第三方 API 旗艦服務的完整免費高階存取權。
> 
> 如果你希望的是幾乎零成本、低門檻就能取得完整高階功能，建議改用其他產品。像是「API Key 錯誤」這類問題，通常是端點與模型設定未設定正確，建議先檢查這兩項。
> 
> 其餘合法使用者皆歡迎使用。

## 支援的 API 供應商

| 供應商 | 支援程度 | 備註 |
|---|---|---|
| OpenAI | 完整支援 | 主要整合路徑 |
| GROQ | 部分支援 | 部分功能可能有差異 |
| Azure | 部分支援 | 端點與模型細節可能不同 |
| OpenRouter | 僅文字生成 | 已測試 Gemini、Claude、Perplexity、Llama、Gemma、Mistral、OpenAI 模型 |
| 其他 | 社群測試 | 歡迎提供回饋 |

> [!NOTE]
> 
> 要切換供應商，請於應用設定中選擇 API endpoint。你也可以新增自訂的 OpenAI 相容端點。

## 基本功能

✅ 已實作能力：

- [x] 聊天（本機儲存，支援匯入/匯出）
- [x] 影像生成
- [x] 影像辨識（可在聊天中附加圖片）
- [x] 啟動提示詞與系統訊息流程
- [x] 語音輸入（Whisper 與 Google）
- [x] 助理整合
- [x] 於內容功能表使用 SpeakGPT
- [x] 於分享面板使用 SpeakGPT
- [x] Function calling 功能
- [x] 提示詞庫
- [x] 多種聊天版面
- [x] 自適應設計
- [x] 廣泛模型支援
- [x] 無驗證碼
- [x] 按用量付費
- [x] 新手提示與上手導覽
- [x] 微調/自訂模型支援
- [x] AMOLED 深色模式
- [x] 自訂 API 供應商支援
- [x] 模型參數自訂（`temperature`、`topP`、`frequencyPenalty`、`presencePenalty`、`logit_bias`）
- [x] Playground
- [x] 可存取最新旗艦模型，例如 o1、o3、o4、gpt-4.1、gpt-4.5、gpt-image-1

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
- Android SDK（`compileSdk 36`）
- JDK 21（`sourceCompatibility` / `targetCompatibility` 需與專案設定中的 Java 21 一致）
- Git
- 能夠連線網路下載 Gradle 相依與呼叫供應商 API

來自儲存庫設定的建置系統資訊：

| 元件 | 版本 / 值 |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin 外掛 | `2.2.10` |
| Gradle wrapper | `8.13` |
| 應用套件 ID | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## 安裝

### 1. 複製儲存庫

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. 在 Android Studio 開啟

- 透過 Android Studio 開啟 `build.gradle`。
- 等待 Gradle 同步完成。

### 3. 建置 debug APK

```bash
./gradlew assembleDebug
```

### 4. 安裝至連接中的裝置／模擬器

```bash
./gradlew installDebug
```

### 5. 可選的品質檢查

```bash
./gradlew lint
```

## 使用

### 應用內使用流程

1. 從 Google Play 或本機 debug build 安裝應用。
2. 完成新手引導流程。
3. 開啟 API 設定並選擇供應商／端點。
4. 新增有效 API Key（會本機保存）。
5. 選擇模型，開始聊天、影像辨識、影像生成或語音工作流程。

### 可用的 Android 整合

- 助理整合（`ASSIST` intent）
- 分享頁整合（`SEND`、`SEND_MULTIPLE` intents）
- 文字處理整合（`PROCESS_TEXT`）
- `assistant.teslasoft.org` 深層連結（`/chat`、`/prompts`、`/assistant`）

## 設定

### API 端點與供應商

- 在應用中開啟 **設定**。
- 選擇 **API endpoint**，即可在內建供應商間切換。
- 若你的供應商為 OpenAI 相容，可新增自訂 endpoint。

### 模型與生成參數

SpeakGPT 支援執行時調整：

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### 本機資料與安全

- 對話資料保存在本機，可匯入/匯出。
- 像 API Key 這類敏感值透過加密偏好設定存放。

### 注意與假設

- 本儲存庫目前包含 `google-services.json`；若在你的分支中移除，部分整合可能需要等效的 Firebase / App Service 設定。
- 不同的 endpoint 與模型家族行為可能會不同。

## 範例

### 建置 release APK

```bash
./gradlew assembleRelease
```

### 清除後重新編譯

```bash
./gradlew clean assembleDebug
```

### 使用 OpenRouter 的 Gemini 家族模型

1. 建立 OpenRouter API Key。
2. 在 SpeakGPT 設定中選擇或新增 OpenRouter endpoint。
3. 選取兼容 Gemini 的模型。
4. 開始聊天並驗證回覆。

### 完整清理編譯

```bash
./gradlew clean build
```

## 開發筆記

- 這是個 Android 多模組專案（`:app`、`:teslasoft-id`）。
- 目前設定下，`debug` 與 `release` 皆使用 `minifyEnabled true` 與 `shrinkResources true`。
- ProGuard/R8 規則位於：
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 嵌入式網頁文件位於：
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- 本地化字串資源位在 `app/src/main/res/values-*`。
- README 多語言版本放在 `i18n/`。

## 故障排解

| 問題 | 建議檢查 |
|---|---|
| API Key 錯誤 / 認證失敗 | 確認金鑰是否有效、供應商是否相容、模型是否可用。部分旗艦模型需要額外帳戶驗證。 |
| Endpoint 或模型不相符 | 確認自訂 endpoint 符合 OpenAI 相容的請求/回應格式。可嘗試切換設定中的 endpoint 預設後重試。 |
| 建置失敗 | 確認 JDK 21 已啟用、重新同步 Gradle，並用 `./gradlew --version` 驗證 wrapper 為 `8.13`，再執行 `./gradlew clean build`。 |
| 舊版 Android 執行問題 | 專案最低要求 `minSdk 28`。因支援策略調整，Android 9、10、11 的棄用警告在預期範圍內。 |

## 路線圖

### ❌ 預計新增

- [ ] 裝置自動化流程（設定鬧鐘或開啟應用）
- [ ] 同步聊天記錄
- [ ] 提示詞交換入口 / 類似市集流程
- [ ] 支援正式上線的上網與工具工作流

## API 金鑰安全

SpeakGPT 使用 API Key 與供應商溝通，因此憑證範圍更可控，較帳號/密碼登入更安全。

- 你的 API Key 儲存在本機，應用不會共用。
- 你可以隨時在供應商後台撤銷金鑰。
- 若有需要，請為 SpeakGPT 使用獨立金鑰。

安全提醒：

1. 為 SpeakGPT 保留獨立 API Key。
2. 設定帳單額度上限。
3. 開啟使用量監控以控管成本。
4. 只要出現可疑使用，立即撤銷金鑰。

為何需要混淆發佈：

混淆與資源收縮能縮小安裝檔、提升效能，並降低憑證處理的逆向工程風險。你可以要求未混淆版本，或自行編譯。

> [!CAUTION]
> 
> 請勿安裝來自不可信來源的 build。第三方 build 可能被修改並注入惡意程式。正式 build 會經由 VirusTotal 檢查後，並透過官方管道發佈。

## 開發者身份

| 欄位 | 內容 |
|---|---|
| 開發者名稱 | Dmytro Ostapenko (AndraxDev) |
| 聯絡方式 | dostapenko82@gmail.com, +421951829517 |
| 法人住址 | Južná trieda 4B, 04001 Košice, Slovakia |
| 法人 ID | 55545386 (D-U-N-S: 933739642) |
| 商業執照號碼 | OU-KE-OZP1-2023/031005-2（依照 455/1991《商業許可條例》第 10(1)(a)條修訂條文，於 2023 年 6 月 14 日簽發） |
| VAT 編號 | SK3121636045 |

（這有助於你在未來決定金流贊助，或未來出現付費功能時確認收款資訊。）

## 貢獻

歡迎貢獻。

- 於 Issues 回報錯誤並附上重現步驟。
- 提出新功能時請提供清楚標題與背景。
- 讓 PR 的範圍保持精簡，並包含原因與測試備註。

## 授權條款

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



## ❤️ Support

| Donate | PayPal | Stripe |
| --- | --- | --- |
| [![Donate](https://camo.githubusercontent.com/24a4914f0b42c6f435f9e101621f1e52535b02c225764b2f6cc99416926004b7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f6e6174652d4c617a79696e674172742d3045413545393f7374796c653d666f722d7468652d6261646765266c6f676f3d6b6f2d6669266c6f676f436f6c6f723d7768697465)](https://chat.lazying.art/donate) | [![PayPal](https://camo.githubusercontent.com/d0f57e8b016517a4b06961b24d0ca87d62fdba16e18bbdb6aba28e978dc0ea21/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f50617950616c2d526f6e677a686f754368656e2d3030343537433f7374796c653d666f722d7468652d6261646765266c6f676f3d70617970616c266c6f676f436f6c6f723d7768697465)](https://paypal.me/RongzhouChen) | [![Stripe](https://camo.githubusercontent.com/1152dfe04b6943afe3a8d2953676749603fb9f95e24088c92c97a01a897b4942/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f5374726970652d446f6e6174652d3633354246463f7374796c653d666f722d7468652d6261646765266c6f676f3d737472697065266c6f676f436f6c6f723d7768697465)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |
