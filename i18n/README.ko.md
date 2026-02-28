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

SpeakGPT는 Android를 위한 고급 오픈소스 AI 어시스턴트로, 매우 직관적인 사용성을 제공합니다. 최신 대규모 언어 모델(LLM) 제공자와 멀티모달 워크플로(채팅, 음성, 이미지 생성, 비전)를 하나의 모바일 앱에 통합했습니다.

공식적으로 GPT 모델, LLAMA, MIXTRAL, GEMMA, Gemini(일반/Pro) Vision, DALL-E 및 기타 모델을 지원합니다.

| 빠른 정보 | 세부 내용 |
|---|---|
| 📱 플랫폼 | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 핵심 사용 방식 | 사용자가 엔드포인트와 키를 직접 제공 |
| 🧩 앱 유형 | 오픈소스 AI 클라이언트(API 제공자 아님) |
| 🌐 웹 컴패니언 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> 이 프로젝트는 제 학사 논문의 일부입니다. 이 작업물을 사용할 때는 출처 표기가 필요합니다. Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
>
> 인용: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> 다음 Android 버전에 대한 지원을 곧 중단할 예정입니다: 9, 10, 11. 이는 최근 SDK 및 보안 변경과 관련이 있습니다. 구형 Android 버전은 RenderScript 같은 deprecated 및 불안정 기능을 사용합니다.

## 목차

- [다운로드](#다운로드)
- [SpeakGPT Web](#speakgpt-web)
- [개요](#개요)
- [스크린샷](#스크린샷)
- [이 앱에서 Google Gemini 모델을 사용하려는 사용자를 위한 안내](#이-앱에서-google-gemini-모델을-사용하려는-사용자를-위한-안내)
- [적은 노력으로 무료 사용만 원하시는 분들께](#적은-노력으로-무료-사용만-원하시는-분들께)
- [지원되는 API 제공자](#지원되는-api-제공자)
- [기본 기능](#기본-기능)
- [프로젝트 구조](#프로젝트-구조)
- [사전 요구사항](#사전-요구사항)
- [설치](#설치)
- [사용법](#사용법)
- [설정](#설정)
- [예시](#예시)
- [개발 노트](#개발-노트)
- [문제 해결](#문제-해결)
- [로드맵](#로드맵)
- [API 키 안전](#api-키-안전)
- [개발자 정보](#개발자-정보)
- [기여](#기여)
- [지원](#지원)
- [Buy me a coffee](#buy-me-a-coffee)
- [라이선스](#라이선스)

## 다운로드

📦 Google Play에서 설치:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 SpeakGPT Web 실행: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub 저장소: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## 개요

SpeakGPT는 AI API를 위한 Android 우선 클라이언트입니다. 사용자가 엔드포인트와 키를 직접 제공하는 방식(BYO endpoint + BYO key)을 중심으로 설계되어, 제공자/모델/비용-성능 프로파일을 직접 선택할 수 있습니다.

저장소 아키텍처:

- `app`: Android 애플리케이션 모듈 (`org.teslasoft.assistant`)
- `teslasoft-id`: 인증/클라이언트 유틸리티용 내부 Android 라이브러리 모듈 (`org.teslasoft.core.auth`)
- 저장소 루트의 JSON 메타데이터(`ai_sets.json`, `explore.json`, `experiment.json`): 모델 세트, 탐색, import/export 스타일 워크플로에 사용
- `i18n/`: 다국어 README 출력 디렉터리(저장소에 포함)

## 스크린샷

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

## 이 앱에서 Google Gemini 모델을 사용하려는 사용자를 위한 안내

SpeakGPT 자체는 Google API 키를 직접 지원하지 않지만, OpenRouter API를 통해 Google Gemini를 사용할 수 있습니다.

자세한 정보: [OpenRouter Models](https://openrouter.ai/docs#models)

## 적은 노력으로 무료 사용만 원하시는 분들께

> [!WARNING]
>
> 무료에는 항상 대가가 따를 수 있습니다. 이 앱은 오픈소스 클라이언트이며 있는 그대로 제공됩니다. 앱 자체가 API 제공자의 프리미엄 기능(플래그십 AI 모델 및 특수 기능 등)에 대한 완전 무료 접근을 제공하지는 않습니다. 다른 사람의 작업물을 무료로, 결제 없이 사용하려는 목적이라면 이 앱 대신 다른 대안을 찾으시기 바랍니다. "API 키가 왜 틀렸나요, 왜 외부 사이트로 이동하나요?" 같은 질문에는 답변하지 않습니다. 이해해 주셔서 감사합니다.
> 그 외의 합리적인 사용자분들은 언제나 환영합니다.

## 지원되는 API 제공자

| Provider | Support level | Notes |
|---|---|---|
| OpenAI | Full support | Primary integration path |
| GROQ | Partial support | Some features may vary |
| Azure | Partial support | Endpoint/model specifics may differ |
| OpenRouter | Text generation only | Tested with Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI models |
| Other | Community-tested | Feedback is welcome |

> [!NOTE]
>
> API 제공자를 변경하려면 설정으로 이동해 API endpoint를 선택하세요. 사용자 지정 API 제공자도 추가할 수 있습니다.

## 기본 기능

✅ 구현된 기능:

- [x] 채팅(로컬 저장, 필요 시 가져오기/내보내기 가능)
- [x] 이미지 생성
- [x] 이미지 인식(이미지/사진을 ChatGPT와 함께 사용)
- [x] Activation prompt
- [x] System message
- [x] 음성 입력(Whisper 및 Google)
- [x] Assistant
- [x] 컨텍스트 메뉴의 SpeakGPT
- [x] 공유 시트의 SpeakGPT
- [x] Function calling 기능
- [x] Prompts Library
- [x] 다양한 채팅 레이아웃
- [x] 적응형 디자인
- [x] 다양한 모델
- [x] 캡차 없음
- [x] 종량제(pay as you go) 시스템
- [x] 초보자 팁
- [x] 커스텀 파인튜닝 모델 지원
- [x] AMOLED 다크 모드
- [x] 커스텀 API 제공자 지원
- [x] `temperature`, `topP`, `frequencyPenalty`, `presencePenalty`, `logit_bias` 같은 모델 파라미터 커스터마이즈
- [x] Playground
- [x] o1, o3, o4, gpt-4.1, gpt-4.5, gpt-image-1 같은 최신 플래그십 모델 접근 지원(일부 모델은 OpenAI 신원 인증이 필요할 수 있음)

## 프로젝트 구조

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

## 사전 요구사항

- Android Studio(최신 안정 버전 권장)
- `compileSdk 36`이 포함된 Android SDK
- JDK 21(프로젝트 source/target 호환성은 Java 21)
- Git
- 의존성 해석 및 모델 제공자 API 사용을 위한 인터넷 연결

저장소 설정 기준 빌드 시스템 정보:

| Component | Version / Value |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## 설치

### 1. 저장소 클론

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. 디버그 APK 빌드

```bash
./gradlew assembleDebug
```

### 3. 연결된 기기/에뮬레이터에 설치

```bash
./gradlew installDebug
```

### 4. 선택적 품질 검사

```bash
./gradlew lint
```

## 사용법

### 최종 사용자 흐름(앱 내)

1. Google Play 또는 로컬 디버그 빌드로 앱을 설치합니다.
2. 온보딩 과정을 완료합니다.
3. API 설정을 열고 엔드포인트/제공자를 선택하거나 추가합니다.
4. API 키를 입력합니다(기기 로컬에 저장).
5. 모델을 선택하고 채팅, 비전, 이미지 생성, 음성 워크플로를 시작합니다.

### 사용 가능한 Android 통합

- Assistant 통합(`ASSIST` intent)
- 공유 시트 통합(`SEND`, `SEND_MULTIPLE` intents)
- 텍스트 처리 통합(`PROCESS_TEXT`)
- `assistant.teslasoft.org`용 딥 링크(`/chat`, `/prompts`, `/assistant`)

## 설정

### API 엔드포인트 및 제공자

- 앱에서 **Settings**를 엽니다.
- **API endpoint**를 선택해 사전 구성된 제공자 간 전환합니다.
- 제공자가 OpenAI 호환이면 커스텀 엔드포인트를 추가할 수 있습니다.

### 모델 및 생성 파라미터

SpeakGPT는 다음과 같은 생성 설정의 런타임 튜닝을 지원합니다:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### 로컬 데이터 및 보안

- 대화는 로컬에 저장되며 가져오기/내보내기가 가능합니다.
- API 키 같은 민감 정보는 암호화된 preferences에 저장됩니다.

### 참고 및 가정

- 이 저장소에는 `google-services.json`이 포함되어 있습니다. 포크 후 이를 제거하면 일부 통합 기능에 자체 설정이 필요할 수 있습니다.
- 제공자 호환성은 엔드포인트 구현 및 모델 계열에 따라 달라질 수 있습니다.

## 예시

### 예시 1: 릴리스 APK 빌드

```bash
./gradlew assembleRelease
```

### 예시 2: 클린 리빌드

```bash
./gradlew clean assembleDebug
```

### 예시 3: Gemini 계열 모델에 OpenRouter 사용

1. OpenRouter API 키를 생성합니다.
2. SpeakGPT 설정에서 OpenRouter 엔드포인트를 선택/추가합니다.
3. Gemini를 지원하는 OpenRouter 모델을 선택합니다.
4. 채팅을 시작하고 응답 생성이 되는지 확인합니다.

## 개발 노트

- 이 프로젝트는 멀티 모듈 Android 프로젝트입니다(`:app`, `:teslasoft-id`).
- 현재 설정에서 `debug`와 `release` 빌드 타입 모두 `minifyEnabled true`, `shrinkResources true`를 사용합니다.
- ProGuard/R8 규칙 위치:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 내장 웹 문서 위치:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- 현지화 리소스는 `app/src/main/res/values-*`에 있습니다.
- README i18n 출력 디렉터리는 `i18n/`이며(언어별 README 파일은 파이프라인 단계에서 별도 생성).

## 문제 해결

| 문제 | 확인 사항 |
|---|---|
| "Incorrect API key" 또는 인증 실패 | 선택한 제공자에 키가 유효한지, 계정에서 선택 모델 사용이 가능한지, 플래그십 모델에 추가 인증이 필요한지 확인하세요. |
| 엔드포인트/모델 불일치 | 커스텀 제공자 엔드포인트 사용 시 OpenAI 호환 요청/응답 형식인지 확인하세요. 설정에서 엔드포인트 프리셋을 바꿔 재테스트하세요. |
| 빌드 문제 | JDK 21 활성화 여부를 확인하고, Android Studio에서 Gradle 동기화 후 `./gradlew --version`으로 wrapper가 Gradle `8.13`을 사용하는지 확인한 다음 `./gradlew clean build`를 다시 실행하세요. |
| 구형 Android 버전 런타임 문제 | 현재 프로젝트는 `minSdk 28`(Android 9)을 지원합니다. SDK/보안 변경으로 Android 9/10/11 지원이 향후 중단될 수 있다는 경고가 있습니다. |

## 로드맵

### ❌ 추가 예정 (Issues에서 아이디어를 공유해 주세요)

- [ ] 디바이스 루틴(알람 설정, 앱 열기 등)
- [ ] 채팅 기록 동기화
- [ ] 프롬프트 스토어 같은 모델 교환 포털 추가
- [ ] 공식 브라우징 기능(AI 모델이 인터넷에 접근)

## API 키 안전

SpeakGPT는 최적의 사용자 경험 제공을 위해 OpenAI API를 사용합니다. API 키 사용은 아이디/비밀번호 사용보다 안전합니다. API 키만으로는 개인 정보를 획득할 수 없습니다. OpenAI는 서비스에 대한 저렴한 API 접근을 제공합니다. API 키는 기기에 로컬 저장되며 누구와도 공유되지 않습니다. SpeakGPT는 어떠한 개인 데이터도 수집하지 않습니다. SpeakGPT는 오픈소스이므로 직접 코드를 확인할 수 있습니다. SpeakGPT의 각 릴리스는 VirusTotal에서 검사됩니다.
우려 사항이 있다면 [API 키를 폐기](https://platform.openai.com/account/api-keys)하거나 SpeakGPT 전용 별도 API 키를 사용하세요.

API 키를 안전하게 관리하려면 다음 단계를 따르세요:

1. SpeakGPT용 별도 API 키를 준비하세요.
2. 결제 한도를 설정하세요.
3. 사용량 모니터링을 활성화해 SpeakGPT가 얼마나 리소스를 사용하고 비용이 얼마나 발생하는지 확인하세요.
4. 우려 사항이 있으면 API 키를 폐기하세요.

> Why we obfuscate our code in production releases?
>
> 난독화와 리소스 축소는 앱 크기와 성능을 최적화하고, 리버스 엔지니어링/변조 위험을 줄여 API 키 같은 자격 증명을 안전하게 보호하는 데 도움이 됩니다. 원하면 비난독화 빌드를 요청하거나 직접 컴파일하여 앱의 안전성을 확인할 수 있습니다.

> [!CAUTION]
>
> 악성코드를 주의하세요! SpeakGPT를 직접 컴파일하고 수정하는 것은 허용되지만, 타인이 제공하는 빌드를 설치할 때는 특히 주의해야 합니다. 해당 빌드에는 악성코드가 포함될 수 있습니다. 공식 빌드에는 악성코드가 없으며 VirusTotal에서 60개 이상의 백신 엔진으로 검사합니다. 각 릴리스 페이지에서 VirusTotal 리포트를 확인하고 바이너리 파일 해시를 비교할 수 있습니다.

## 개발자 정보

| Field | Value |
|---|---|
| Developer name | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Legal address | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Legal entity ID | 55545386 (D-U-N-S: 933739642) |
| Commercial activity license | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to the § 10 section 1 letter a) of the Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) as amended) |
| VAT ID | SK3121636045 |

(향후 프로젝트를 재정적으로 후원하거나 프로젝트에 유료 기능이 추가될 경우, 비용이 어디로 전달되는지 확인할 수 있도록 제공합니다)

## 기여

기여를 환영합니다.

- 재현 단계와 함께 Issues에 버그를 제보해 주세요.
- 신규 기능을 요청해 주세요(명확한 이슈 태그/레이블 사용 권장).
- 코드를 제출할 때는 변경 범위를 작게 유지하고 근거를 포함해 주세요.

## 지원

### 다음과 같은 도움을 부탁드립니다

- 버그 제보
- 프로젝트 후원 :)
- 신규 기능 요청(이슈에 태그를 꼭 지정)

## Buy me a coffee

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## 라이선스

이 프로젝트는 Apache License 2.0에 따라 라이선스됩니다. 자세한 내용은 [LICENSE.md](LICENSE.md)를 확인하세요.

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
