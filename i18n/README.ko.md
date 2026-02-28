[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Android-first, chat, voice, vision, image generation 워크플로를 지원하는 오픈 소스 AI 어시스턴트입니다.

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

| ✅ 항목 | 🔗 링크 |
|---|---|
| Android 앱 설치 | [Google Play](https://play.google.com/store/apps/details?id=org.teslasoft.assistant) |
| 웹 컴패니언 사용 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |
| 이슈 확인 | [GitHub Issues](https://github.com/AndraxDev/speak-gpt/issues) |
| 번역 보기 | [i18n/](i18n/) |

---

SpeakGPT는 Android용으로 만든 고급 오픈 소스 AI 어시스턴트입니다. 채팅, 음성, 이미지 생성, 비전 기능을 하나의 앱에 통합하여 OpenAI 호환 제공자 위에서 멀티모달 AI 경험을 제공합니다.

공식적으로 GPT, LLAMA, MIXTRAL, GEMMA, Gemini(일반/Pro) Vision, DALL-E 및 기타 모델군을 지원합니다.

## Quick facts

| 빠른 요약 | 상세 |
|---|---|
| 📱 플랫폼 | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 핵심 방식 | Bring-your-own-endpoint + Bring-your-own-key |
| 🧩 앱 유형 | 오픈 소스 AI 클라이언트(API 제공자 아님) |
| 🌐 웹 컴패니언 | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> 이 프로젝트는 제 학사 학위 논문의 일부입니다. 이 작업물을 사용하려면 출처를 명시해야 합니다. Copyright (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
> 
> 인용 예시: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> Android 9, 10, 11은 SDK/보안 변경으로 인해 곧 지원 중단 대상입니다. 기존 Android 버전은 RenderScript처럼 더 이상 권장되지 않는 API에 의존합니다.

## Table of contents

- [다운로드](#다운로드)
- [SpeakGPT Web](#speakgpt-web)
- [개요](#개요)
- [스크린샷](#스크린샷)
- [Google Gemini 모델 사용 안내](#google-gemini-모델-사용-안내)
- [저비용/무노력형 사용자를 위한 안내](#저비용무노력형-사용자를-위한-안내)
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

SpeakGPT는 API 스택을 사용자가 직접 제어하기 쉬운 플로우 기반으로 설계된 Android 우선 AI 클라이언트입니다.

### 한눈에 보기

| 영역 | 요약 |
|---|---|
| 💬 핵심 경험 | 채팅, 이미지 생성, 이미지 인식, 음성 입력, 어시스턴트 통합 |
| 🔌 제공자 전략 | OpenAI 호환 엔드포인트와 커스텀 제공자, 사용자 정의 엔드포인트 |
| 🔐 데이터 처리 | API 키는 기기 로컬에 저장됩니다. 대화 내용은 가져오기/내보내기 가능 |
| 🧱 빌드 스택 | AGP `8.12.2`, Gradle `8.13`, Kotlin `2.2.10`을 사용하는 Android 멀티 모듈 프로젝트 |

저장소 구조:

- `app`: Android 앱 모듈 (`org.teslasoft.assistant`)
- `teslasoft-id`: 인증/클라이언트 유틸용 내부 Android 라이브러리 모듈 (`org.teslasoft.core.auth`)
- `ai_sets.json`, `explore.json`, `experiment.json`: 모델 세트/탐색/워크플로 메타데이터를 위한 루트 메타데이터
- `i18n/`: 다국어 문서 폴더

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

## Google Gemini 모델 사용 안내

SpeakGPT는 Google API 키를 직접 지원하지 않지만, OpenRouter를 통해 Gemini를 사용할 수 있습니다.

자세한 내용: [OpenRouter Models](https://openrouter.ai/docs#models)

## 저비용/무노력형 사용자를 위한 안내

> [!WARNING]
> 
> 무료 기능은 종종 제약이 따릅니다. 이 앱은 오픈 소스이며 AS-IS로 제공합니다. 제3자 API의 프리미엄 접근을 무료로 전면 제공하지 않습니다.
> 
> 완전 무료 프리미엄 접근을 기대한다면 다른 제품을 사용하는 것이 안전합니다. "API 키가 잘못되었습니다" 같은 이슈는 보통 엔드포인트/모델 설정 점검으로 해결됩니다. 양해 부탁드립니다.
> 
> 그 외의 정상 사용자에게는 환영합니다.

## 지원되는 API 제공자

| 제공자 | 지원 수준 | 비고 |
|---|---|---|
| OpenAI | 전면 지원 | 기본 통합 경로 |
| GROQ | 부분 지원 | 일부 기능은 제공자마다 다름 |
| Azure | 부분 지원 | 엔드포인트/모델 특성에 따라 세부 동작 차이 가능 |
| OpenRouter | 텍스트 생성 전용 | Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI 모델로 테스트 |
| 기타 | 커뮤니티 테스트 기반 | 피드백 환영 |

> [!NOTE]
> 
> 제공자를 변경하려면 앱 설정에서 API endpoint를 선택하세요. OpenAI 호환이면 사용자 정의 엔드포인트도 추가할 수 있습니다.

## 기본 기능

✅ 현재 구현된 기능:

- [x] 채팅 (로컬 저장 및 가져오기/내보내기 지원)
- [x] 이미지 생성
- [x] 이미지 인식 (채팅에서 이미지/사진 첨부)
- [x] 활성화 프롬프트 및 시스템 메시지 워크플로
- [x] 음성 입력 (Whisper 및 Google)
- [x] 어시스턴트 통합
- [x] 컨텍스트 메뉴에서 SpeakGPT 사용
- [x] 공유 시트에서 SpeakGPT 사용
- [x] 함수 호출 기능
- [x] 프롬프트 라이브러리
- [x] 여러 채팅 레이아웃
- [x] 반응형 UI
- [x] 광범위한 모델 지원
- [x] 캡차 없음
- [x] 사용량 기반 과금 모델
- [x] 신규 사용자 가이드/온보딩
- [x] 파인튜닝/커스텀 모델 지원
- [x] AMOLED 다크 모드
- [x] 커스텀 API 제공자 지원
- [x] 모델 파라미터 커스터마이즈 (`temperature`, `topP`, `frequencyPenalty`, `presencePenalty`, `logit_bias`)
- [x] Playground
- [x] 최신 플래그십 계열(o1, o3, o4, gpt-4.1, gpt-4.5, gpt-image-1) 접근

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

- Android Studio (현재 안정판 권장)
- `compileSdk 36`가 포함된 Android SDK
- JDK 21 (`sourceCompatibility`/`targetCompatibility`는 Java 21과 정렬)
- Git
- Gradle 의존성 및 제공자 API 사용을 위한 인터넷

빌드 시스템 정보:

| 구성 요소 | 버전 / 값 |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
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

### 2. Android Studio로 열기

- Android Studio에서 `build.gradle` 열기
- Gradle 동기화 완료 대기

### 3. 디버그 APK 빌드

```bash
./gradlew assembleDebug
```

### 4. 연결된 기기/에뮬레이터에 설치

```bash
./gradlew installDebug
```

### 5. 선택적 품질 검사

```bash
./gradlew lint
```

## 사용법

### 엔드유저 플로우 (앱 내)

1. Google Play 또는 로컬 디버그 빌드로 앱 설치
2. 온보딩 흐름 완료
3. API 설정에서 제공자/엔드포인트 선택
4. 유효한 API 키 추가 (기기 로컬 저장)
5. 모델 선택 후 채팅/비전/이미지 생성/음성 워크플로 시작

### Android 통합 기능

- 어시스턴트 통합 (`ASSIST` 인텐트)
- 공유 시트 통합 (`SEND`, `SEND_MULTIPLE` 인텐트)
- 텍스트 처리 통합 (`PROCESS_TEXT`)
- `assistant.teslasoft.org` 딥 링크 (`/chat`, `/prompts`, `/assistant`)

## 설정

### API 엔드포인트와 제공자

- 앱의 **Settings**를 엽니다.
- 기본 제공자 간 전환은 **API endpoint**를 통해 수행합니다.
- 제공자가 OpenAI 호환이면 사용자 정의 엔드포인트를 추가할 수 있습니다.

### 모델 및 생성 파라미터

SpeakGPT는 실행 중 파라미터 조정이 가능합니다:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### 로컬 데이터와 보안

- 대화는 로컬 저장소에 보관되며 가져오기/내보내기가 가능합니다.
- API 키와 같은 민감 정보는 암호화된 preference로 관리합니다.

### 참고 및 가정

- 현재 레포에는 `google-services.json`이 포함되어 있습니다. 포크에서 제거된 경우 일부 통합에서 Firebase/App 서비스 동등 설정이 필요할 수 있습니다.
- 제공자 동작은 엔드포인트와 모델군에 따라 다를 수 있습니다.

## 예시

### 릴리스 APK 빌드

```bash
./gradlew assembleRelease
```

### 클린 빌드 후 디버그 APK

```bash
./gradlew clean assembleDebug
```

### Gemini 계열 모델에 OpenRouter 사용

1. OpenRouter API 키 생성
2. SpeakGPT 설정에서 OpenRouter 엔드포인트 선택/추가
3. Gemini 호환 모델 선택
4. 채팅 시작 후 응답 확인

### 전체 클린 빌드

```bash
./gradlew clean build
```

## 개발 노트

- 멀티 모듈 Android 프로젝트입니다 (`:app`, `:teslasoft-id`).
- 현재 구성에서 `debug`/`release` 빌드 타입 모두 `minifyEnabled true`, `shrinkResources true`입니다.
- ProGuard/R8 규칙:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- 내장 웹 문서 위치:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- 지역화 문자열 리소스: `app/src/main/res/values-*`
- README 번역 파일: `i18n/`

## 문제 해결

| 문제 | 점검 항목 |
|---|---|
| API 키/인증 실패 | 키 유효성, 제공자 호환성, 모델 사용 가능 여부 확인. 일부 플래그십 모델은 추가 계정 인증이 필요할 수 있습니다. |
| 엔드포인트 또는 모델 불일치 | 사용자 정의 엔드포인트가 OpenAI 호환 요청/응답 형식을 따르는지 확인하고, 설정에서 엔드포인트 프리셋을 변경한 뒤 재시도 |
| 빌드 실패 | JDK 21 활성화 확인, Gradle 동기화, `./gradlew --version`으로 wrapper가 `8.13`인지 확인 후 `./gradlew clean build` 실행 |
| 레거시 Android 런타임 이슈 | 프로젝트는 `minSdk 28`입니다. Android 9/10/11은 정책 변경으로 인해 경고가 예상됩니다. |

## 로드맵

### ❌ 예정 항목

- [ ] 디바이스 루틴(알람 설정/앱 실행)
- [ ] 채팅 기록 동기화
- [ ] 프롬프트 교환 포털 / 마켓플레이스형 흐름
- [ ] 인터넷 접근 워크플로를 위한 공식 브라우징/툴링

## API 키 보안

SpeakGPT는 API 요청용 키를 사용하므로, 계정/비밀번호 기반 방식보다 범위가 더 좁고 안전합니다.

- API 키는 로컬에 저장되며 앱이 외부에 공유하지 않습니다.
- 제공자 콘솔에서 언제든지 키를 회수할 수 있습니다.
- 원하면 SpeakGPT 전용 전용 키를 별도 발급해 사용하세요.

보안 체크리스트:

1. SpeakGPT 전용 키를 따로 준비합니다.
2. 결제 한도 설정
3. 사용량 모니터링으로 비용 관리
4. 의심 징후가 보이면 즉시 키 폐기

패키지 난독화 이유:

난독화와 리소스 축소는 패키지 크기 최적화, 성능 향상, 자격 증명 처리 시 역공학 위험을 낮추기 위해 사용됩니다. 원하면 난독화되지 않은 빌드를 요청하거나 직접 컴파일할 수 있습니다.

> [!CAUTION]
> 
> 신뢰할 수 없는 출처의 빌드는 설치하지 마세요. 제3자 빌드는 악성코드가 삽입될 위험이 있습니다. 공식 빌드는 VirusTotal 검사와 공식 채널 배포를 거칩니다.

## 개발자 정보

| 항목 | 값 |
|---|---|
| 개발자명 | Dmytro Ostapenko (AndraxDev) |
| 연락처 | dostapenko82@gmail.com, +421951829517 |
| 주소 | Južná trieda 4B, 04001 Košice, Slovakia |
| 법인 ID | 55545386 (D-U-N-S: 933739642) |
| 영업 활동 면허 | OU-KE-OZP1-2023/031005-2 (2023년 6월 14일 발급, 개정된 제455/1991 Coll. 무역 라이선스법 §10(1)(a) 근거) |
| VAT ID | SK3121636045 |

(후원 또는 향후 유료 기능이 생길 경우, 자금이 어디로 가는지 미리 알 수 있도록 공개했습니다.)

## 기여하기

기여를 환영합니다.

- Issues에 버그를 재현 단계와 함께 등록하세요.
- 새 기능은 제목과 맥락을 명확히 작성해 제안하세요.
- PR 범위를 명확히 하고 변경 사유 및 테스트 노트를 함께 넣어 주세요.

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


## ❤️ Support

| Donate | PayPal | Stripe |
| --- | --- | --- |
| [![Donate](https://camo.githubusercontent.com/24a4914f0b42c6f435f9e101621f1e52535b02c225764b2f6cc99416926004b7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f6e6174652d4c617a79696e674172742d3045413545393f7374796c653d666f722d7468652d6261646765266c6f676f3d6b6f2d6669266c6f676f436f6c6f723d7768697465)](https://chat.lazying.art/donate) | [![PayPal](https://camo.githubusercontent.com/d0f57e8b016517a4b06961b24d0ca87d62fdba16e18bbdb6aba28e978dc0ea21/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f50617950616c2d526f6e677a686f754368656e2d3030343537433f7374796c653d666f722d7468652d6261646765266c6f676f3d70617970616c266c6f676f436f6c6f723d7768697465)](https://paypal.me/RongzhouChen) | [![Stripe](https://camo.githubusercontent.com/1152dfe04b6943afe3a8d2953676749603fb9f95e24088c92c97a01a897b4942/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f5374726970652d446f6e6174652d3633354246463f7374796c653d666f722d7468652d6261646765266c6f676f3d737472697065266c6f676f436f6c6f723d7768697465)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |
