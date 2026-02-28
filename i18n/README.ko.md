[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Android 우선(First), 채팅·음성·비전·이미지 생성 워크플로를 통합한 오픈소스 AI 어시스턴트입니다.

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#quick-facts)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#prerequisites)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#prerequisites)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#license)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#prerequisites)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#prerequisites)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#prerequisites)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)

SpeakGPT는 Android용 고급 오픈소스 AI 어시스턴트로, 현대적인 대규모 언어 모델(LLM) 제공자와 멀티모달 워크플로(채팅, 음성, 이미지 생성, 비전)를 하나의 모바일 앱으로 통합했습니다.

공식적으로 GPT 모델, LLAMA, MIXTRAL, GEMMA, Gemini(일반/Pro) Vision, DALL-E 및 기타 모델을 지원합니다.

## Quick facts

| 간단 요약 | 상세 내용 |
|---|---|
| 📱 플랫폼 | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 주요 사용 방식 | Bring-your-own-endpoint + Bring-your-own-key |
| 🧩 앱 유형 | 오픈소스 AI 클라이언트(API 제공자 아님) |
| 🌐 웹 컴패니언 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> 이 프로젝트는 제 학위 논문의 일부입니다. 이 작업물을 사용할 때는 출처 표기가 필요합니다. Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
> 
> 인용 예시: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> 다음 Android 버전에 대한 지원을 곧 중단할 예정입니다: 9, 10, 11. 이는 최근 SDK 및 보안 변경과 관련이 있습니다. 구형 Android 버전은 RenderScript와 같은 더 이상 권장되지 않거나 불안정한 기능을 사용합니다.

## 목차

- [다운로드](#다운로드)
- [SpeakGPT Web](#speakgpt-web)
- [개요](#개요)
- [스크린샷](#스크린샷)
- [Google Gemini 모델 사용 가이드](#google-gemini-모델-사용-가이드)
- [적은 비용으로 무료로 시작하고 싶은 분들](#적은-비용으로-무료로-시작하고-싶은-분들)
- [지원되는 API 제공자](#지원되는-api-제공자)
- [기본 기능](#기본-기능)
- [프로젝트 구조](#프로젝트-구조)
- [사전 조건](#사전-조건)
- [설치](#설치)
- [사용법](#사용법)
- [설정](#설정)
- [예시](#예시)
- [개발 노트](#개발-노트)
- [문제 해결](#문제-해결)
- [로드맵](#로드맵)
- [API 키 보안](#api-키-보안)
- [개발자 정보](#개발자-정보)
- [기여하기](#기여하기)
- [❤️ Support](#-support)
- [라이선스](#라이선스)

## 다운로드

📦 Google Play에서 설치:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 SpeakGPT Web 실행: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub 저장소: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## 개요

SpeakGPT는 AI API용 Android 우선 클라이언트입니다. 사용자가 엔드포인트와 키를 직접 제공하는 방식으로 설계되어 있으며, 사용자가 제공자, 모델, 비용/성능 프로필을 직접 선택할 수 있습니다.

### 한눈에 보기

| 영역 | 요약 |
|---|---|
| 💬 핵심 경험 | 채팅, 이미지 생성, 이미지 인식, 음성 입력, 어시스턴트 통합 |
| 🔌 제공자 전략 | 구성 가능한 제공자와 사용자 지정 엔드포인트를 지원하는 OpenAI 호환 엔드포인트 |
| 🔐 데이터 처리 | API 키는 로컬 저장, 대화는 가져오기/내보내기 가능 |
| 🧱 빌드 스택 | AGP `8.12.2`, Gradle `8.13`, Kotlin `2.2.10`을 사용하는 Android 멀티 모듈 프로젝트 |

저장소 아키텍처:

- `app`: Android 애플리케이션 모듈 (`org.teslasoft.assistant`)
- `teslasoft-id`: 인증/클라이언트 유틸리티용 내부 Android 라이브러리 모듈 (`org.teslasoft.core.auth`)
- 루트의 JSON 메타데이터(`ai_sets.json`, `explore.json`, `experiment.json`) — 모델 세트, 탐색, import/export 방식 워크플로에 사용
- `i18n/`: 다국어 README 출력 디렉터리(현재 레포지토리에 존재)

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

## Google Gemini 모델 사용 가이드

SpeakGPT는 Google API 키를 직접 지원하지 않지만 OpenRouter API를 통해 Google Gemini를 사용할 수 있습니다.

자세한 내용: [OpenRouter Models](https://openrouter.ai/docs#models)

## 적은 비용으로 무료로 시작하고 싶은 분들

> [!WARNING]
> 
> 무료 기능은 보통 덫이 될 수 있습니다. 이 앱은 있는 그대로 제공되는 오픈소스 클라이언트이며, API 제공자의 프리미엄 기능(플래그십 AI 모델 및 특수 기능 포함)에 대한 완전 무료 접근을 보장하지 않습니다.
> 
> "다른 사람의 작업물을 공짜로, 거의 공짜로 쓰고 싶다"면 이 앱보다 다른 대안을 찾는 편이 낫습니다. `Incorrect API key` 오류 후 외부 사이트로 리디렉션되는 이유를 묻는 질문에는 더 이상 답변하지 않습니다.
> 
> 이해해 주셔서 감사합니다. 그 밖의 정상적인 사용자는 모두 환영합니다.

## 지원되는 API 제공자

| 제공자 | 지원 수준 | 메모 |
|---|---|---|
| OpenAI | 완전 지원 | 기본 통합 경로 |
| GROQ | 부분 지원 | 일부 기능은 다를 수 있음 |
| Azure | 부분 지원 | 엔드포인트/모델 세부사항이 다를 수 있음 |
| OpenRouter | 텍스트 생성만 | Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI 모델로 테스트됨 |
| 기타 | 커뮤니티 검증 | 의견 환영 |

> [!NOTE]
> 
> API 제공자를 변경하려면 설정에서 API 엔드포인트를 선택하세요. 사용자 지정 API 제공자를 추가할 수도 있습니다.

## 기본 기능

✅ 현재 구현된 기능:

- [x] 채팅(기본적으로 로컬 저장되며 필요 시 가져오기/내보내기 가능)
- [x] 이미지 생성
- [x] 이미지 인식(ChatGPT와 함께 이미지·사진 사용)
- [x] Activation prompt
- [x] System message
- [x] 음성 입력 (Whisper와 Google)
- [x] Assistant
- [x] 컨텍스트 메뉴의 SpeakGPT
- [x] 공유 시트의 SpeakGPT
- [x] 함수 호출(Function calling) 기능
- [x] Prompts Library
- [x] 다양한 채팅 레이아웃
- [x] 반응형 디자인
- [x] 다양한 모델 지원
- [x] 캡챠 없음
- [x] 종량제 요금제
- [x] 초보자 팁
- [x] 사용자 정의 미세 조정 모델 지원
- [x] AMOLED 다크 모드
- [x] 사용자 지정 API 제공자 지원
- [x] `temperature`, `topP`, `frequencyPenalty`, `presencePenalty`, `logit_bias` 같은 모델 파라미터 조정
- [x] Playground
- [x] o1, o3, o4, gpt-4.1, gpt-4.5, gpt-image-1 등 최신 플래그십 모델 사용(일부 모델은 OpenAI 신원 검증 필요)

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

## 사전 조건

- Android Studio(최신 안정 버전 권장)
- `compileSdk 36`가 포함된 Android SDK
- JDK 21 (프로젝트의 source/target 호환성은 Java 21)
- Git
- 의존성 해석과 모델 제공자 API 접근을 위한 인터넷 연결

빌드 시스템 정보:

| 구성 요소 | 버전 / 값 |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin 플러그인 | `2.2.10` |
| Gradle wrapper | `8.13` |
| 앱 패키지 ID | `org.teslasoft.assistant` |
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
3. API 설정으로 이동해 엔드포인트/제공자를 선택하거나 추가합니다.
4. API 키를 입력합니다(기기 로컬에 저장됨).
5. 모델을 선택하고 채팅, 비전, 이미지 생성, 음성 워크플로우를 시작합니다.

### Android 통합 항목

- Assistant 통합 (`ASSIST` intent)
- 공유 시트 통합 (`SEND`, `SEND_MULTIPLE` intent)
- 텍스트 처리 통합 (`PROCESS_TEXT`)
- `assistant.teslasoft.org`의 딥 링크 (`/chat`, `/prompts`, `/assistant`)
- `assistant.teslasoft.org`의 딥 링크 (`/chat`, `/prompts`, `/assistant`)

## 설정

### API 엔드포인트 및 제공자

- 앱에서 **Settings**를 엽니다.
- 사전 설정된 제공자 간 전환을 위해 **API endpoint**를 선택합니다.
- 제공자가 OpenAI 호환이면 사용자 지정 엔드포인트를 추가할 수 있습니다.

### 모델 및 생성 파라미터

SpeakGPT는 다음과 같은 생성 설정의 런타임 튜닝을 지원합니다:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### 로컬 데이터 및 보안

- 대화는 로컬에 저장되며 가져오기/내보내기가 가능합니다.
- API 키 같은 민감한 값은 암호화된 환경설정에 저장됩니다.

### 참고 및 가정

- 이 저장소에는 `google-services.json`이 포함되어 있습니다. 포크 시 제거한다면 일부 통합에 추가 구성 파일이 필요할 수 있습니다.
- 제공자 호환성은 엔드포인트 구현과 모델군에 따라 달라질 수 있습니다.

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
3. Gemini 사용 가능한 OpenRouter 모델을 선택합니다.
4. 채팅을 시작하고 응답 생성을 확인합니다.

## 개발 노트

- 이 프로젝트는 멀티 모듈 Android 프로젝트입니다 (`:app`, `:teslasoft-id`).
- 현재 설정에서 `debug`와 `release` 빌드 타입 모두 `minifyEnabled true`, `shrinkResources true` 입니다.
- ProGuard/R8 규칙 위치:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 내장 웹 문서 위치:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- 로컬라이제이션 리소스는 `app/src/main/res/values-*`에 위치합니다.
- README i18n 출력 디렉터리는 `i18n/`입니다(언어별 README 파일은 이 파이프라인에서 별도 생성).

## 문제 해결

| 문제 | 확인 사항 |
|---|---|
| "Incorrect API key" 또는 인증 실패 | 선택한 제공자에 대해 키가 유효한지 확인하고, 계정에서 선택한 모델 사용이 가능한지, 플래그십 모델에 추가 검증이 필요한지 점검하세요. |
| 엔드포인트/모델 불일치 | 사용자 지정 제공자 엔드포인트를 쓰는 경우 OpenAI 호환 요청/응답 형식인지 확인합니다. 설정에서 엔드포인트 프리셋을 변경한 뒤 재테스트하세요. |
| 빌드 문제 | JDK 21이 활성화되어 있는지 확인하고, Android Studio에서 Gradle 동기화 후 `./gradlew --version`으로 Gradle 버전이 `8.13`인지 확인한 뒤 `./gradlew clean build`로 재시도하세요. |
| 구형 Android 실행 이슈 | 현재 프로젝트는 `minSdk 28`(Android 9)을 지원합니다. SDK/보안 변경으로 인해 Android 9/10/11 지원이 향후 중단될 수 있습니다. |

## 로드맵

### ❌ 추가 예정 (아이디어는 Issue에서 제안해 주세요)

- [ ] 디바이스 자동화(알람 설정, 앱 실행 등)
- [ ] 채팅 기록 동기화
- [ ] 프롬프트 스토어 같은 모델 교환 포털 추가
- [ ] 공식 브라우징 기능(AI 모델에서 인터넷 접근)

## API 키 보안

SpeakGPT는 최적의 사용 경험을 위해 OpenAI API를 사용합니다. API 키는 사용자명/비밀번호보다 안전하며, 개인 정보를 API 키만으로 가져올 수 없습니다. OpenAI는 저렴한 API 접근을 제공합니다. API 키는 기기 로컬에 저장되며 누구와도 공유되지 않습니다.
SpeakGPT는 개인 데이터를 수집하지 않으며, 오픈소스 코드가 공개되어 있어 직접 확인할 수 있습니다. 각 릴리스는 VirusTotal에서 검사됩니다.
우려가 있다면 [API 키 폐기](https://platform.openai.com/account/api-keys)를 하거나 SpeakGPT 전용 별도 키를 사용하세요.

API 키를 안전하게 사용하려면 다음 단계를 따르세요:

1. SpeakGPT 전용 개별 API 키를 준비합니다.
2. 결제 한도를 설정합니다.
3. 사용량 모니터링을 켜어 API 사용량과 비용을 추적합니다.
4. 우려가 있으면 API 키를 폐기합니다.

> Why we obfuscate our code in production releases?
>
> 난독화와 리소스 축소는 앱 용량 최적화, 성능 개선, 리버스 엔지니어링·변조 방지 및 API 키 같은 인증 정보의 안전한 저장을 위해 필요합니다. 비난독화 빌드를 요청하거나 직접 컴파일해 안전성을 직접 확인할 수 있습니다.

> [!CAUTION]
> 
> 악성코드에 주의하세요! SpeakGPT는 직접 컴파일하고 수정할 수 있지만, 타인이 제공한 빌드를 설치할 때는 반드시 주의해야 합니다. 해당 빌드에는 악성코드가 들어 있을 수 있습니다. 공식 빌드는 악성코드가 없으며, VirusTotal에서 60개 이상의 백신으로 검사합니다. 각 릴리스 페이지에서 VirusTotal 보고서를 확인해 바이너리 해시를 비교할 수 있습니다.

## 개발자 정보

| 항목 | 값 |
|---|---|
| 개발자 이름 | Dmytro Ostapenko (AndraxDev) |
| 연락처 | dostapenko82@gmail.com, +421951829517 |
| 주소 | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| 사업자 등록번호 | 55545386 (D-U-N-S: 933739642) |
| 영업 활동 허가증 | OU-KE-OZP1-2023/031005-2 (2023년 6월 14일, 법률 No. 455/1991 Coll. 개정 본안 §10조 1항 a호에 따라 발급) |
| VAT ID | SK3121636045 |

(향후 후원 또는 유료 기능이 생겼을 때 자금이 어디로 가는지 알 수 있도록 기입했습니다.)

## 기여하기

기여를 환영합니다.

- 이슈에 재현 단계와 함께 버그를 보고해 주세요.
- 새 기능을 요청해 주세요(명확한 태그/라벨 사용 권장).
- 코드를 기여할 경우 변경 범위를 작게 잡고 이유를 함께 설명해 주세요.

## ❤️ Support

| Donate | PayPal | Stripe |
|---|---|---|
| [![Donate](https://img.shields.io/badge/Donate-LazyingArt-0EA5E9?style=for-the-badge&logo=ko-fi&logoColor=white)](https://chat.lazying.art/donate) | [![PayPal](https://img.shields.io/badge/PayPal-RongzhouChen-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/RongzhouChen) | [![Stripe](https://img.shields.io/badge/Stripe-Donate-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

### 후원 안내

- 버그를 신고해 주세요
- 후원을 환영합니다 :)
- 새 기능을 요청해 주세요. 이슈에 태그를 꼭 추가해 주세요

### Buy me a coffee

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## 라이선스

이 프로젝트는 Apache License 2.0으로 라이선스됩니다. 자세한 내용은 [LICENSE.md](LICENSE.md)를 참고하세요.

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
