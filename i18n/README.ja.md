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

SpeakGPT は、Android 向けの高度で直感的なオープンソース AI アシスタントです。最新の大規模言語モデル（LLM）プロバイダーとマルチモーダルなワークフロー（チャット、音声、画像生成、画像認識）を 1 つのモバイルアプリに統合しています。

公式には、GPT モデル、LLAMA、MIXTRAL、GEMMA、Gemini（通常版および Pro）Vision、DALL-E などのモデルをサポートしています。

| クイック情報 | 詳細 |
|---|---|
| 📱 プラットフォーム | Android（`minSdk 28`, `targetSdk 36`） |
| 🧠 主な利用形態 | エンドポイント持ち込み + API キー持ち込み |
| 🧩 アプリ種別 | オープンソース AI クライアント（API プロバイダーではありません） |
| 🌐 Web 版 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> このプロジェクトは私の学士論文の一部です。この成果物を利用する場合は帰属表示が必要です。Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
>
> 引用形式: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> 次の Android バージョンのサポートは近日中に終了予定です: 9, 10, 11。これは SDK およびセキュリティの最近の変更に関連しています。古い Android バージョンでは RenderScript などの非推奨かつ不安定な機能が使われています。

## 目次

- [ダウンロード](#ダウンロード)
- [SpeakGPT Web](#speakgpt-web)
- [概要](#概要)
- [スクリーンショット](#スクリーンショット)
- [このアプリで Google Gemini モデルを使いたいユーザー向け情報](#このアプリで-google-gemini-モデルを使いたいユーザー向け情報)
- [ほとんど手間をかけずに無料で使いたい方へ](#ほとんど手間をかけずに無料で使いたい方へ)
- [対応 API プロバイダー](#対応-api-プロバイダー)
- [基本機能](#基本機能)
- [プロジェクト構成](#プロジェクト構成)
- [前提条件](#前提条件)
- [インストール](#インストール)
- [使い方](#使い方)
- [設定](#設定)
- [使用例](#使用例)
- [開発メモ](#開発メモ)
- [トラブルシューティング](#トラブルシューティング)
- [ロードマップ](#ロードマップ)
- [API キーの安全性](#api-キーの安全性)
- [開発者情報](#開発者情報)
- [コントリビュート](#コントリビュート)
- [サポート](#サポート)
- [Buy me a coffee](#buy-me-a-coffee)
- [ライセンス](#ライセンス)

## ダウンロード

📦 Google Play からインストール:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 SpeakGPT Web を開く: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub リポジトリ: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## 概要

SpeakGPT は AI API 向けの Android ファーストなクライアントです。エンドポイント持ち込み・キー持ち込みを前提に設計されており、ユーザーがプロバイダー、モデル、コスト/性能プロファイルを選べます。

リポジトリアーキテクチャ:

- `app`: Android アプリケーションモジュール（`org.teslasoft.assistant`）
- `teslasoft-id`: 認証/クライアントユーティリティ用の内部 Android ライブラリモジュール（`org.teslasoft.core.auth`）
- リポジトリルートの JSON メタデータ（`ai_sets.json`, `explore.json`, `experiment.json`）は、モデルセット、探索、インポート/エクスポート系ワークフローに利用
- `i18n/`: 多言語 README の出力ディレクトリ（このリポジトリに存在）

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

SpeakGPT 自体は Google API キーをサポートしていませんが、OpenRouter API を使うことで Google Gemini を利用できます。

詳細: [OpenRouter Models](https://openrouter.ai/docs#models)

## ほとんど手間をかけずに無料で使いたい方へ

> [!WARNING]
>
> 無料のうまい話には必ず注意してください。THIS APP IS OPEN-SOURCE CLIENT PROVIDED AS IS. ITSELF IT DOES NOT PROVIDE COMPLETELY FREE ACCESS TO THE PREMIUM FEATURES OF API PROVIDERS (LIKE FLAGSHIP AI MODELS AND SPECIAL FEATURES). IF YOU COME HERE TO USE OTHER'S WORK FOR FREE AND WITHOUT A CREDIT, IT'S BETTER YOU SKIP THIS APP AND LOOK FOR SOMETHING ELSE. I WILL NOT RESPOND TO YOUR "INCORRECT API KEY, WHY THIS APP REDIRECTS ME TO THE EXTERNAL SITE FOR API KEY?" QUESTIONS. THANK YOU FOR UNDERSTANDING.
> 常識的に利用してくださる方は歓迎します。

## 対応 API プロバイダー

| プロバイダー | 対応レベル | 注記 |
|---|---|---|
| OpenAI | フルサポート | 主要な統合先 |
| GROQ | 部分サポート | 一部機能に差異がある場合があります |
| Azure | 部分サポート | エンドポイント/モデル固有の差異がある場合があります |
| OpenRouter | テキスト生成のみ | Gemini、Claude、Perplexity、Llama、Gemma、Mistral、OpenAI モデルで検証済み |
| Other | コミュニティ検証 | フィードバック歓迎 |

> [!NOTE]
>
> API プロバイダーを変更するには、設定に移動して API エンドポイントを選択してください。カスタム API プロバイダーを追加することもできます。

## 基本機能

✅ 実装済み機能:

- [x] チャット（ローカル保存、必要に応じてインポート/エクスポート可能）
- [x] 画像生成
- [x] 画像認識（画像や写真を ChatGPT と一緒に利用）
- [x] Activation prompt
- [x] System message
- [x] 音声入力（Whisper および Google）
- [x] Assistant
- [x] コンテキストメニューでの SpeakGPT
- [x] Share シートでの SpeakGPT
- [x] Function calling features
- [x] Prompts Library
- [x] 異なるチャットレイアウト
- [x] アダプティブデザイン
- [x] 多数のモデル
- [x] CAPTCHA なし
- [x] 従量課金システム
- [x] 初心者向けヒント
- [x] カスタム微調整モデルをサポート
- [x] AMOLED ダークモード
- [x] カスタム API プロバイダー対応
- [x] `temperature`, `topP`, `frequencyPenalty`, `presencePenalty`, `logit_bias` などのモデルパラメータをカスタマイズ可能
- [x] Playground
- [x] o1、o3、o4、gpt-4.1、gpt-4.5、gpt-image-1 など最新フラッグシップモデルへのアクセス（これらの一部は OpenAI で本人確認が必要な場合があります）

## プロジェクト構成

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
- `compileSdk 36` を含む Android SDK
- JDK 21（プロジェクトの source/target 互換は Java 21）
- Git
- 依存関係解決およびモデルプロバイダー API 用のインターネット接続

リポジトリ設定に基づくビルド情報:

| コンポーネント | バージョン / 値 |
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

### 3. 接続済みデバイス/エミュレーターにインストール

```bash
./gradlew installDebug
```

### 4. 任意の品質チェック

```bash
./gradlew lint
```

## 使い方

### エンドユーザーフロー（アプリ内）

1. Google Play またはローカルのデバッグビルドからアプリをインストールします。
2. オンボーディングを完了します。
3. API 設定を開き、エンドポイント/プロバイダーを選択または追加します。
4. API キーを入力します（キーは端末内にローカル保存されます）。
5. モデルを選び、チャット、画像認識、画像生成、音声ワークフローを開始します。

### 利用可能な Android 連携

- Assistant 連携（`ASSIST` intent）
- Share シート連携（`SEND` および `SEND_MULTIPLE` intents）
- Process text 連携（`PROCESS_TEXT`）
- `assistant.teslasoft.org` 向けディープリンク（`/chat`, `/prompts`, `/assistant`）

## 設定

### API エンドポイントとプロバイダー

- アプリの **Settings** を開きます。
- **API endpoint** を選択して、事前設定済みプロバイダーを切り替えます。
- プロバイダーが OpenAI 互換であれば、カスタムエンドポイントを追加できます。

### モデルと生成パラメータ

SpeakGPT は、以下のような生成設定を実行時に調整できます:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### ローカルデータとセキュリティ

- 会話はローカルに保存され、インポート/エクスポートできます。
- API キーなどの機密値は暗号化された Preferences で扱われます。

### 補足と前提

- このリポジトリには `google-services.json` が含まれています。fork 時に削除した場合は、一部連携で独自設定が必要になる場合があります。
- プロバイダー互換性は、エンドポイント実装やモデルファミリーにより異なる場合があります。

## 使用例

### 例 1: リリース APK をビルド

```bash
./gradlew assembleRelease
```

### 例 2: クリーンリビルド

```bash
./gradlew clean assembleDebug
```

### 例 3: Gemini 系モデルに OpenRouter を使用

1. OpenRouter API キーを作成します。
2. SpeakGPT の設定で OpenRouter エンドポイントを選択/追加します。
3. Gemini 対応の OpenRouter モデルを選択します。
4. チャットを開始し、応答が生成されることを確認します。

## 開発メモ

- これはマルチモジュール Android プロジェクトです（`:app`, `:teslasoft-id`）。
- 現在の設定では、`debug` と `release` の両ビルドタイプで `minifyEnabled true` と `shrinkResources true` が有効です。
- ProGuard/R8 ルールの場所:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 同梱 Web ドキュメントの場所:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- ローカライズリソースは `app/src/main/res/values-*` にあります。
- README の i18n 出力ディレクトリは `i18n/` にあります（言語別 README はパイプライン手順で個別生成されます）。

## トラブルシューティング

| 問題 | 確認ポイント |
|---|---|
| "Incorrect API key" などの認証失敗 | 選択中プロバイダーでキーが有効か、選択モデルがアカウントで利用可能か、フラッグシップモデルに追加認証が必要かを確認してください。 |
| エンドポイント/モデル不一致 | カスタムプロバイダーを使う場合は OpenAI 互換の request/response 形式を満たしているか確認してください。設定でエンドポイントプリセットを切り替えて再テストしてください。 |
| ビルド問題 | JDK 21 が有効か確認し、Android Studio で Gradle を同期し、`./gradlew --version` で wrapper が Gradle `8.13` を使っていることを確認後、`./gradlew clean build` を再実行してください。 |
| 古い Android での実行問題 | 現在のサポートは `minSdk 28`（Android 9）です。SDK/セキュリティ変更により、将来 Android 9/10/11 のサポートが終了する可能性がある旨の警告があります。 |

## ロードマップ

### ❌ 追加予定（アイデアは Issues へ）

- [ ] デバイスルーチン（アラーム設定やアプリ起動など）
- [ ] チャット履歴の同期
- [ ] プロンプトストアのようなモデル交換ポータルの追加
- [ ] 公式ブラウジング機能（GPT 系モデルがインターネットにアクセス）

## API キーの安全性

SpeakGPT は、より良い体験を提供するために OpenAI API を使用します。API キー利用はユーザー名/パスワード利用より安全です。API キーだけで個人情報を取得されることはありません。OpenAI は自社サービスへの安価な API アクセスを提供しています。あなたの API キーは端末内にローカル保存され、他者と共有されません。SpeakGPT は個人データを収集しません。SpeakGPT はオープンソースであり、コードを自分で確認できます。SpeakGPT の各リリースは VirusTotal でチェックされています。
懸念がある場合は、[API キーを revoke](https://platform.openai.com/account/api-keys) するか、SpeakGPT 専用の別キーを使ってください。

API キーを保護するには、次の手順を実施してください:

1. SpeakGPT 用に別の API キーを用意する。
2. 課金上限を設定する。
3. 利用状況のモニタリングを有効にし、SpeakGPT のリソース使用量とコストを確認する。
4. 不安がある場合は API キーを revoke する。

> Why we obfuscate our code in production releases?
>
> Obfuscation and resources shrinking allows us to optimize app size, its performance and secure it against reverse engineering or tamper and make sure your credentials like API keys are in a safe place. You can request an unobfuscated build or compile it by yourself to make sure our app is safe.

> [!CAUTION]
>
> マルウェアに注意してください。SpeakGPT を自分でビルド・改変することは可能ですが、第三者が配布するビルドをインストールする場合は十分に注意してください。そのようなビルドにはマルウェアが含まれる可能性があります。公式ビルドにはマルウェアは含まれておらず、VirusTotal の 60 以上の異なるアンチウイルスでチェックされています。各リリースページで VirusTotal レポートを確認し、バイナリファイルのハッシュを比較できます。

## 開発者情報

| 項目 | 値 |
|---|---|
| Developer name | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Legal address | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Legal entity ID | 55545386 (D-U-N-S: 933739642) |
| Commercial activity license | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to the § 10 section 1 letter a) of the Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) as amended) |
| VAT ID | SK3121636045 |

（プロジェクトを金銭的に支援する場合、または将来有料機能が追加された場合に、送金先を明確にするための情報です）

## コントリビュート

コントリビュート歓迎です。

- 再現手順を添えて Issues でバグ報告してください。
- 新機能を提案してください（明確な issue タグ/ラベルの利用をお願いします）。
- コードを提出する場合は変更範囲を絞り、理由を含めてください。

## サポート

### ご協力いただけること

- バグ報告
- 応援していただけると助かります :)
- 新機能のリクエスト（issue にタグ付けを忘れずに）

## Buy me a coffee

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## ライセンス

このプロジェクトは Apache License 2.0 の下でライセンスされています。詳細は [LICENSE.md](LICENSE.md) を参照してください。

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
