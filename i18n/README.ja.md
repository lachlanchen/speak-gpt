[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Android-first、チャット、音声、ビジョン、画像生成ワークフローを備えたオープンソースAIアシスタント。

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
| Androidアプリをインストール | [Google Play](https://play.google.com/store/apps/details?id=org.teslasoft.assistant) |
| Webコンパニオンを使う | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |
| 問題を確認 | [GitHub Issues](https://github.com/AndraxDev/speak-gpt/issues) |
| 翻訳を読む | [i18n/](i18n/) |

---

SpeakGPT は、Android向けの高度で直感的なオープンソースAIアシスタントです。OpenAI互換の提供元を使って、チャット、音声、画像生成、ビジョン体験を1つのアプリに統合します。

公式には GPT、LLAMA、MIXTRAL、GEMMA、Gemini（標準版と Pro 版）の Vision、DALL-E、およびその他のファミリーをサポートします。

## Quick facts

| Quick facts | Details |
|---|---|
| 📱 Platform | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Core usage | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 App type | Open-source AI client (not an API provider) |
| 🌐 Web companion | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> このプロジェクトは私の学士論文の一部です。本作の使用時はクレジット（帰属）が必要です。Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
> 
> Cite as: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> Android 9、10、11 は SDK やセキュリティ変更により、サポート終了予定です。旧 Android では RenderScript など非推奨 API への依存があります。

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

📦 Google Play からインストール:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 SpeakGPT Web を起動: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHubリポジトリ: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Overview

SpeakGPT は、利用者が API 構成を直接コントロールしたい場合に向け、柔軟なプロバイダー連携を中心に設計されています。

### At a glance

| Area | Summary |
|---|---|
| 💬 Core experiences | チャット、画像生成、画像認識、音声入力、アシスタント連携 |
| 🔌 Provider strategy | OpenAI互換エンドポイントを使用し、プロバイダーとカスタムエンドポイントを構成可能 |
| 🔐 Data handling | APIキーはローカル保存。会話はインポート/エクスポート可能 |
| 🧱 Build stack | AGP `8.12.2`、Gradle `8.13`、Kotlin `2.2.10` を使用した Android マルチモジュール構成 |

Repository architecture:

- `app`: Androidアプリモジュール (`org.teslasoft.assistant`)
- `teslasoft-id`: 認証／クライアント用ユーティリティの内部 Android ライブラリモジュール (`org.teslasoft.core.auth`)
- リポジトリルートの JSON メタデータ（`ai_sets.json`、`explore.json`、`experiment.json`）
  - モデルセット、探索、ワークフローメタデータに使用
- `i18n/`: 多言語ドキュメントのディレクトリ

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

SpeakGPT は Google API キーを直接サポートしていませんが、OpenRouter を経由して Gemini を利用できます。

詳細: [OpenRouter Models](https://openrouter.ai/docs#models)

## For those not-far people who want to use something for free making low or no effort

> [!WARNING]
> 
> 無料機能にはしばしば制約があります。このアプリはオープンソースで、現状のまま提供されます。サードパーティの API フラッグシップサービスへの無料の全面的なプレミアムアクセスは提供しません。
> 
> もし完全無料のプレミアム利用を期待するなら、別の製品を検討するほうが安全です。「APIキーが正しくない」などの質問は、通常エンドポイントとモデル設定を確認すれば解消します。ご理解ください。
> 
> 正当な利用者には引き続き歓迎です。

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
> プロバイダーを変更するには、アプリ設定から API エンドポイントを選択します。OpenAI 互換のカスタムエンドポイントを追加することもできます。

## Basic features

✅ 実装済み機能:

- [x] チャット（ローカル保存、インポート/エクスポート対応）
- [x] 画像生成
- [x] 画像認識（チャットで画像・写真を添付）
- [x] アクティベーションプロンプトとシステムメッセージワークフロー
- [x] 音声入力（Whisper と Google）
- [x] アシスタント連携
- [x] コンテキストメニューに SpeakGPT
- [x] 共有シートに SpeakGPT
- [x] ファンクションコーリング機能
- [x] プロンプトライブラリ
- [x] 複数のチャットレイアウト
- [x] 適応デザイン
- [x] 広範なモデル対応
- [x] キャプチャ無し（No captcha）
- [x] 従量課金モデル
- [x] 新規ユーザー向けのヒントとオンボーディングガイダンス
- [x] Fine-tuned / カスタムモデル対応
- [x] AMOLED ダークモード
- [x] カスタム API プロバイダー対応
- [x] モデル生成パラメータのカスタム（`temperature`、`topP`、`frequencyPenalty`、`presencePenalty`、`logit_bias`）
- [x] Playground
- [x] o1、o3、o4、gpt-4.1、gpt-4.5、gpt-image-1 など最新フラッグシップモデルへのアクセス

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

- Android Studio（現行安定版を推奨）
- Android SDK（`compileSdk 36`）
- JDK 21（`sourceCompatibility`/`targetCompatibility` はプロジェクト設定で Java 21 に揃え）
- Git
- Gradle 依存関係とプロバイダー API 用のインターネット接続

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
# リポジトリを取得
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Open in Android Studio

- Android Studio で `build.gradle` を開く。
- Gradle sync を完了させる。

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

1. Google Play またはローカルのデバッグビルドでアプリをインストールします。
2. オンボーディングを完了します。
3. API 設定を開き、プロバイダー／エンドポイントを選択します。
4. 有効な API キーを追加します（デバイス内にローカル保存）。
5. モデルを選択して、チャット、ビジョン、画像生成、音声ワークフローを開始します。

### Android integrations available

- アシスタント連携（`ASSIST` intent）
- 共有シート連携（`SEND`、`SEND_MULTIPLE` intent）
- テキスト処理連携（`PROCESS_TEXT`）
- `assistant.teslasoft.org` のディープリンク（`/chat`、`/prompts`、`/assistant`）

## Configuration

### API endpoints and providers

- アプリ内の **Settings** を開きます。
- **API endpoint** を選択して、組み込みプロバイダーを切り替えます。
- プロバイダーが OpenAI 互換なら、カスタムエンドポイントを追加します。

### Model and generation parameters

SpeakGPT は実行時に以下を調整できます。

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Local data and security

- 会話はローカルに保存され、インポート/エクスポート可能です。
- API キーなどの機密値は暗号化された設定で管理されます。

### Notes and assumptions

- 本リポジトリには `google-services.json` が含まれます。フォーク時に削除した場合、同等の Firebase/App サービス設定が必要になることがあります。
- プロバイダーの挙動はエンドポイントやモデルファミリーで異なる場合があります。

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

1. OpenRouter API キーを作成します。
2. SpeakGPT の設定で OpenRouter エンドポイントを選択／追加します。
3. Gemini 互換モデルを選択します。
4. チャットを開始し、レスポンスを確認します。

### Build a full clean run

```bash
./gradlew clean build
```

## Development notes

- このプロジェクトは Android マルチモジュール構成です（`:app`、`:teslasoft-id`）。
- 現在の構成では `debug` と `release` の両方の build type で `minifyEnabled true` と `shrinkResources true` が有効です。
- ProGuard/R8 のルールは以下にあります。
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 埋め込み Web ドキュメントは以下です。
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- ローカライズ文字列は `app/src/main/res/values-*` にあります。
- README の多言語版は `i18n/` ディレクトリに置かれます。

## Troubleshooting

| Issue | What to check |
|---|---|
| Incorrect API key / auth failure | キーの有効性、プロバイダー適合性、モデルの提供可否を確認します。フラッグシップモデルは追加のアカウント認証が必要な場合があります。 |
| Endpoint or model mismatch | カスタムエンドポイントが OpenAI 互換の request/response 形式か確認します。設定でエンドポイントのプリセットを変更して再試行してください。 |
| Build failures | JDK 21 が有効か確認し、Gradle を sync して、`./gradlew --version` で wrapper が `8.13` であることを確認後、`./gradlew clean build` を実行します。 |
| Runtime issues on legacy Android | 本プロジェクトは `minSdk 28` です。Android 9/10/11 のサポートは SDK・セキュリティ変更に伴って段階的に廃止される見込みです。 |

## Roadmap

### ❌ Planned additions

- [ ] Device routines（アラーム設定やアプリ起動）
- [ ] チャット履歴の同期
- [ ] プロンプト交換ポータル / マーケットプレイス形式フロー
- [ ] インターネットアクセス対応ワークフローの公式ブラウジング／ツール実装

## API key safety

SpeakGPT はプロバイダーリクエストに API キーを使用するため、認証情報はアカウント/パスワード方式より扱いやすいです。

- API キーはローカル保存され、アプリ側で第三者共有されません。
- いつでもプロバイダーコンソールでキーを無効化できます。
- 必要なら、SpeakGPT 専用のキーを使うことを推奨します。

Security reminders:

1. SpeakGPT 用に別の API キーを用意
2. 課金上限を設定
3. 使用量監視を有効化してコストを確認
4. 不審な使用が見られたらキーを無効化

Why app releases are obfuscated:

難読化とリソース圧縮は、パッケージサイズとパフォーマンスを改善し、認証情報周辺のリバースエンジニアリングリスクを下げるために行われます。難読化なしビルドを希望する場合は、無効化の要望を出すか、手元でビルドしてください。

> [!CAUTION]
> 
> 信頼できないソースからのビルドはインストールしないでください。サードパーティ製ビルドはマルウェアを含む可能性があります。公式ビルドは公式チャネルで公開され、VirusTotal で検証されています。

## Developer identity

| Field | Value |
|---|---|
| Developer name | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Legal address | Južná trieda 4B, 04001 Košice, Slovakia |
| Legal entity ID | 55545386 (D-U-N-S: 933739642) |
| Commercial activity license | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to § 10(1)(a) of Act No. 455/1991 Coll. on Trade Licensing, as amended) |
| VAT ID | SK3121636045 |

(開発者を支援する際に送金先を確認するため、また将来このプロジェクトで有料機能が追加された場合に有効です。)

## Contributing

Contributions are welcome.

- バグは再現手順を含めて Issues で報告してください。
- 明確なタイトルと背景とともに新機能を提案してください。
- PR は範囲を限定し、意図と確認事項を明記してください。

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
