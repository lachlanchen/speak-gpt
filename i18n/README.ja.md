[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Android を第一にした、チャット、音声、画像認識、画像生成ワークフローを備えたオープンソース AI アシスタントです。

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#quick-facts)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#prerequisites)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#prerequisites)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#license)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#prerequisites)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#prerequisites)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#prerequisites)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)

SpeakGPT は、Android 向けの高度で直感的なオープンソース AI アシスタントです。最新の大規模言語モデル（LLM）プロバイダーと、チャット、音声、画像生成、ビジョン機能などのマルチモーダルワークフローを 1 つのモバイルアプリに統合しています。

公式には、GPT モデル、LLAMA、MIXTRAL、GEMMA、Gemini（通常版と Pro 版）の Vision、DALL-E、ほかのモデルをサポートしています。

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
> 以下の Android バージョンのサポートはまもなく終了します: 9, 10, 11。これは SDK とセキュリティの最近の変更に関連しています。古い Android では RenderScript などの非推奨で不安定な機能が使われています。

## 目次

- [ダウンロード](#ダウンロード)
- [SpeakGPT Web](#speakgpt-web)
- [概要](#概要)
- [スクリーンショット](#スクリーンショット)
- [このアプリで Google Gemini モデルを使いたいユーザー向け情報](#このアプリで-google-gemini-モデルを使いたいユーザー向け情報)
- [手間をかけずに無料で使いたい方向け](#手間をかけずに無料で使いたい方向け)
- [対応 API プロバイダー](#対応-api-プロバイダー)
- [基本機能](#基本機能)
- [プロジェクト構造](#プロジェクト構造)
- [前提条件](#前提条件)
- [インストール](#インストール)
- [利用方法](#利用方法)
- [設定](#設定)
- [利用例](#利用例)
- [開発メモ](#開発メモ)
- [トラブルシューティング](#トラブルシューティング)
- [ロードマップ](#ロードマップ)
- [API キーの安全性](#api-キーの安全性)
- [開発者情報](#開発者情報)
- [コントリビュート](#コントリビュート)
- [❤️ Support](#-support)
- [ライセンス](#ライセンス)

## ダウンロード

📦 Google Play からインストール:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 SpeakGPT Web を起動: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub リポジトリ: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## 概要

SpeakGPT は、AI API 向けの Android ファーストクライアントです。Bring-your-own-endpoint と Bring-your-own-key を前提に設計されており、ユーザーはプロバイダー、モデル、コスト/性能プロファイルを選択できます。

### サマリー

| 項目 | 概要 |
|---|---|
| 💬 コア体験 | チャット、画像生成、画像認識、音声入力、アシスタント連携 |
| 🔌 プロバイダー戦略 | OpenAI 互換のエンドポイント。プロバイダーと独自エンドポイントを設定可能 |
| 🔐 データ処理 | API キーは端末内に保存。会話はインポート/エクスポート可能 |
| 🧱 ビルドスタック | AGP `8.12.2`、Gradle `8.13`、Kotlin `2.2.10` を使う Android マルチモジュール構成 |

リポジトリ構成:

- `app`: Android アプリケーションモジュール（`org.teslasoft.assistant`）
- `teslasoft-id`: 認証/クライアントユーティリティ向けの内部 Android ライブラリモジュール（`org.teslasoft.core.auth`）
- リポジトリルートにある JSON メタデータ（`ai_sets.json`、`explore.json`、`experiment.json`）はモデルセット、探索、インポート/エクスポート型ワークフローに使用
- `i18n/`: 多言語 README 出力ディレクトリ（リポジトリ内に存在）

## スクリーンショット

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

## このアプリで Google Gemini モデルを使いたいユーザー向け情報

SpeakGPT 自体は Google API キーをサポートしていませんが、OpenRouter API を利用すれば Google Gemini を使うことができます。

詳細: [OpenRouter Models](https://openrouter.ai/docs#models)

## 手間をかけずに無料で使いたい方向け

> [!WARNING]
>
> 無料には落とし穴があることを忘れないでください。THIS APP IS OPEN-SOURCE CLIENT PROVIDED AS IS. ITSELF IT DOES NOT PROVIDE COMPLETELY FREE ACCESS TO THE PREMIUM FEATURES OF API PROVIDERS (LIKE FLAGSHIP AI MODELS AND SPECIAL FEATURES). IF YOU COME HERE TO USE OTHER'S WORK FOR FREE AND WITHOUT A CREDIT, IT'S BETTER YOU SKIP THIS APP AND LOOK FOR SOMETHING ELSE. I WILL NOT RESPOND TO YOUR "INCORRECT API KEY, WHY THIS APP REDIRECTS ME TO THE EXTERNAL SITE FOR API KEY?" QUESTIONS. THANK YOU FOR UNDERSTANDING.
> 常識的に使う人向けの内容です。  
> 無駄な期待をせず、適切な利用規約の範囲内で使ってください。

## 対応 API プロバイダー

| Provider | Support level | Notes |
|---|---|---|
| OpenAI | Full support | Primary integration path |
| GROQ | Partial support | Some features may vary |
| Azure | Partial support | Endpoint/model specifics may differ |
| OpenRouter | Text generation only | Tested with Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI models |
| Other | Community-tested | Feedback is welcome |

> [!NOTE]
>
> API プロバイダーを変更するには、設定から API エンドポイントを選択します。独自 API プロバイダーも追加できます。

## 基本機能

✅ 実装済み:

- [x] チャット（ローカル保存。必要に応じてインポート/エクスポート可能）
- [x] 画像生成
- [x] 画像認識（画像や写真を ChatGPT で使用）
- [x] Activation prompt
- [x] System message
- [x] 音声入力（Whisper と Google）
- [x] Assistant
- [x] コンテキストメニュー内の SpeakGPT
- [x] 共有シート内の SpeakGPT
- [x] Function calling features
- [x] Prompts Library
- [x] 複数のチャットレイアウト
- [x] 適応型デザイン
- [x] 多数のモデル
- [x] キャプチャなし
- [x] 従量課金システム
- [x] 初心者向けチュートリアル
- [x] カスタムファインチューニングモデル対応
- [x] AMOLED ダークモード
- [x] カスタム API プロバイダー対応
- [x] `temperature`、`topP`、`frequencyPenalty`、`presencePenalty`、`logit_bias` などのモデルパラメータをカスタマイズ
- [x] Playground
- [x] o1、o3、o4、gpt-4.1、gpt-4.5、gpt-image-1 など最新フラッグシップモデルへのアクセス（これらのモデルは OpenAI の本人確認が必要な場合があります）

## プロジェクト構造

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

## 前提条件

- Android Studio（最新安定版推奨）
- Android SDK（`compileSdk 36`）
- JDK 21（プロジェクトの source/target 互換性は Java 21）
- Git
- 依存関係の解決とモデル API 利用のためのインターネット接続

Build system facts from repo configuration:

| Component | Version / Value |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## インストール

### 1. リポジトリをクローン

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. デバッグ APK をビルド

```bash
./gradlew assembleDebug
```

### 3. 接続済みデバイスまたはエミュレーターへインストール

```bash
./gradlew installDebug
```

### 4. 任意の品質チェック

```bash
./gradlew lint
```

## 利用方法

### エンドユーザーの流れ（アプリ内）

1. Google Play またはローカルのデバッグビルドからアプリをインストールします。
2. オンボーディングを完了します。
3. API 設定を開いて、エンドポイント/プロバイダーを選択または追加します。
4. API キーを入力します（キーは端末にローカル保存されます）。
5. モデルを選んでチャット、ビジョン、画像生成、音声ワークフローを開始します。

### 利用可能な Android 連携

- Assistant 連携（`ASSIST` intent）
- 共有シート連携（`SEND` と `SEND_MULTIPLE` intent）
- Process text 連携（`PROCESS_TEXT`）
- `assistant.teslasoft.org` のディープリンク (`/chat`, `/prompts`, `/assistant`)

## 設定

### API エンドポイントとプロバイダー

- アプリの **Settings** を開きます。
- **API endpoint** を選択し、事前設定済みプロバイダーを切り替えます。
- 選択したプロバイダーが OpenAI 互換なら、独自エンドポイントを追加できます。

### モデルと生成パラメータ

SpeakGPT は実行時に以下の生成パラメータを調整できます:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### ローカルデータとセキュリティ

- 会話はローカル保存され、インポート/エクスポートできます。
- API キーなどの機密情報は暗号化された preference で扱われます。

### 補足と前提

- このリポジトリには `google-services.json` が含まれます。フォーク時に削除すると、いくつかの連携で独自設定が必要になる場合があります。
- プロバイダー互換性は、エンドポイント実装とモデルファミリーで差が出る場合があります。

## 利用例

### 例 1: リリース APK をビルド

```bash
./gradlew assembleRelease
```

### 例 2: クリーンビルド

```bash
./gradlew clean assembleDebug
```

### 例 3: OpenRouter で Gemini 系モデルを利用

1. OpenRouter API キーを作成します。
2. SpeakGPT の設定で OpenRouter エンドポイントを選択または追加します。
3. Gemini 対応の OpenRouter モデルを選択します。
4. チャットを開始し、応答生成を確認します。

## 開発メモ

- これは Android のマルチモジュールプロジェクトです（`:app`、`:teslasoft-id`）。
- 現在の設定では、`debug` と `release` の両ビルドタイプで `minifyEnabled true` と `shrinkResources true` が有効です。
- ProGuard/R8 設定は次にあります:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 組み込み Web ドキュメント:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- ローカライズリソースは `app/src/main/res/values-*` にあります。
- README i18n 出力ディレクトリは `i18n/`（言語別の README はこのパイプライン手順で別々に生成）

## トラブルシューティング

| Issue | What to check |
|---|---|
| "Incorrect API key" や認証失敗 | 選択したプロバイダーでキーが有効か、選択したモデルがアカウントで利用可能か、プレミアムモデルには追加認証が必要か確認します。 |
| エンドポイント/モデル不一致 | 独自プロバイダーを使う場合、OpenAI 互換の request/response 形式か確認してください。設定でエンドポイントプリセットを切り替えて再テストします。 |
| ビルド問題 | JDK 21 を有効にし、Android Studio で Gradle を同期し、`./gradlew --version` で wrapper が Gradle `8.13` か確認後、`./gradlew clean build` で再実行します。 |
| 古い Android での実行問題 | 現在は `minSdk 28`（Android 9）をサポートしています。SDK とセキュリティ変更により、将来 Android 9/10/11 のサポートが終了する可能性があります。 |

## ロードマップ

### ❌ 追加予定（Issue でアイデア募集）

- [ ] デバイスルーチン（アラーム設定やアプリ起動など）
- [ ] チャット履歴同期
- [ ] プロンプトストアのようなモデル交換ポータル
- [ ] 公式ブラウジング機能（GPT 系モデルにインターネットアクセスを許可）

## API キーの安全性

SpeakGPT は最良の体験を提供するために OpenAI API を利用しています。API キーの利用はユーザー名とパスワードより安全です。API キーだけで個人情報を取得することはできません。OpenAI は自社サービスへの安価な API アクセスを提供しています。API キーはデバイス内にローカル保存され、第三者と共有されません。SpeakGPT は個人情報を収集しません。SpeakGPT はオープンソースで、コードを自分で確認できます。SpeakGPT の各リリースは VirusTotal でチェックされています。
懸念がある場合は、[API キーを取り消し](https://platform.openai.com/account/api-keys) するか、SpeakGPT 用の別キーを使用してください。

API キーを保護する手順:

1. SpeakGPT 専用のキーを用意します。
2. 課金上限を設定します。
3. 利用状況監視を有効にして、SpeakGPT が使用するリソースとコストを確認します。
4. 不安があれば API キーを取り消します。

> Why we obfuscate our code in production releases?
>
> Obfuscation and resources shrinking allows us to optimize app size, its performance and secure it against reverse engineering or tamper and make sure your credentials like API keys are in a safe place. You can request an unobfuscated build or compile it by yourself to make sure our app is safe.

> [!CAUTION]
>
> マルウェアに注意してください。SpeakGPT は自分でビルド・改変できますが、他者が配布するビルドをインストールする際は特に注意してください。そうしたビルドにはマルウェアが含まれている可能性があります。公式ビルドにはマルウェアは含まれておらず、VirusTotal の 60 以上の異なるアンチウイルスで検査されています。各リリースページで VirusTotal レポートを確認し、バイナリのハッシュを比較できます。

## 開発者情報

| Field | Value |
|---|---|
| Developer name | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Legal address | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Legal entity ID | 55545386 (D-U-N-S: 933739642) |
| Commercial activity license | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to the § 10 section 1 letter a) of the Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) as amended) |
| VAT ID | SK3121636045 |

（必要に応じて、プロジェクト支援時の送金先を明確にするために使用されます。）

## コントリビュート

コントリビューションを歓迎します。

- バグは再現手順を添えて Issues で報告してください。
- 新機能の要望（分かりやすい issue タグ/ラベルを使ってください）。
- コードを提出する場合、変更範囲を絞り、意図を明記してください。

## ❤️ Support

| Donate | PayPal | Stripe |
|---|---|---|
| [![Donate](https://img.shields.io/badge/Donate-LazyingArt-0EA5E9?style=for-the-badge&logo=ko-fi&logoColor=white)](https://chat.lazying.art/donate) | [![PayPal](https://img.shields.io/badge/PayPal-RongzhouChen-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/RongzhouChen) | [![Stripe](https://img.shields.io/badge/Stripe-Donate-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

### You are appreciated to

- バグの報告
- サポートしていただけると嬉しいです :)
- 新機能の要望。issue にはタグを付けるのを忘れずに

### Buy me a coffee

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## ライセンス

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
