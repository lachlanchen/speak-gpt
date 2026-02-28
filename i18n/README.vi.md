[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Trợ lý AI mã nguồn mở ưu tiên Android với các luồng chat, giọng nói, thị giác và tạo ảnh.

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

| ✅ Mục | 🔗 Liên kết |
|---|---|
| Cài đặt ứng dụng Android | [Google Play](https://play.google.com/store/apps/details?id=org.teslasoft.assistant) |
| Dùng công cụ web đi kèm | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |
| Theo dõi issue | [GitHub Issues](https://github.com/AndraxDev/speak-gpt/issues) |
| Đọc bản dịch | [i18n/](i18n/) |

---

SpeakGPT là một trợ lý AI mã nguồn mở hiện đại, trực quan dành cho Android. Nó gói ghém nhiều trải nghiệm AI đa phương thức (chat, giọng nói, tạo ảnh và thị giác) trong một ứng dụng duy nhất, sử dụng các nhà cung cấp tương thích OpenAI.

Chính thức nó hỗ trợ GPT, LLAMA, MIXTRAL, GEMMA, Gemini Vision (phiên bản thường và pro), DALL-E và các gia đình mô hình khác.

## Thông tin nhanh <a id="quick-facts"></a>

| Thông tin nhanh | Chi tiết |
|---|---|
| 📱 Nền tảng | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Cách dùng chính | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 Loại ứng dụng | Client AI mã nguồn mở (không phải nhà cung cấp API) |
| 🌐 Công cụ web đi kèm | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> Dự án này là một phần của luận văn tốt nghiệp của tôi. Việc ghi nhận tác giả là bắt buộc khi sử dụng tác phẩm này. Bản quyền (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
> 
> Trích dẫn: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> Android 9, 10, và 11 dự kiến ngừng hỗ trợ do thay đổi SDK/bảo mật. Android cũ phụ thuộc vào API đã lỗi thời như RenderScript.

## Mục lục <a id="table-of-contents"></a>

- [Tải xuống](#download)
- [SpeakGPT Web](#speakgpt-web)
- [Tổng quan](#overview)
- [Ảnh chụp màn hình](#screenshots)
- [Thông tin cho người dùng muốn dùng Google Gemini trong ứng dụng này](#information-for-users-who-want-to-use-google-gemini-models-with-this-app)
- [Dành cho người dùng muốn dùng miễn phí với tối thiểu công sức](#for-those-not-far-people-who-want-to-use-something-for-free-making-low-or-no-effort)
- [Nhà cung cấp API được hỗ trợ](#api-providers-supported)
- [Tính năng cơ bản](#basic-features)
- [Cấu trúc dự án](#project-structure)
- [Yêu cầu trước](#prerequisites)
- [Cài đặt](#installation)
- [Sử dụng](#usage)
- [Cấu hình](#configuration)
- [Ví dụ](#examples)
- [Ghi chú phát triển](#development-notes)
- [Khắc phục sự cố](#troubleshooting)
- [Lộ trình](#roadmap)
- [An toàn khóa API](#api-key-safety)
- [Danh tính nhà phát triển](#developer-identity)
- [Đóng góp](#contributing)
- [❤️ Support](#-support)
- [Giấy phép](#license)

## Tải xuống <a id="download"></a>

📦 Cài đặt từ Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web <a id="speakgpt-web"></a>

🌍 Khởi chạy SpeakGPT Web: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub repo: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Tổng quan <a id="overview"></a>

SpeakGPT được thiết kế quanh quy trình linh hoạt cho người dùng muốn kiểm soát trực tiếp stack API của mình.

### Tóm tắt nhanh

| Phạm vi | Tóm tắt |
|---|---|
| 💬 Trải nghiệm cốt lõi | Chat, tạo ảnh, nhận diện ảnh, nhập giọng nói, tích hợp trợ lý |
| 🔌 Chiến lược nhà cung cấp | Endpoint tương thích OpenAI với nhà cung cấp và endpoint có thể cấu hình |
| 🔐 Xử lý dữ liệu | Khóa API được lưu cục bộ; hội thoại có thể import/export |
| 🧱 Ngăn xếp xây dựng | Dự án Android multi-module dùng AGP `8.12.2`, Gradle `8.13`, Kotlin `2.2.10` |

Kiến trúc repository:

- `app`: module ứng dụng Android (`org.teslasoft.assistant`)
- `teslasoft-id`: module thư viện nội bộ Android cho tiện ích xác thực/client (`org.teslasoft.core.auth`)
- metadata JSON ở gốc repo (`ai_sets.json`, `explore.json`, `experiment.json`) dùng cho bộ model, khám phá và metadata workflow
- `i18n/`: thư mục tài liệu đa ngôn ngữ

## Ảnh chụp màn hình <a id="screenshots"></a>

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

## Thông tin cho người muốn dùng Google Gemini với ứng dụng này <a id="information-for-users-who-want-to-use-google-gemini-models-with-this-app"></a>

SpeakGPT không hỗ trợ trực tiếp khóa API Google, nhưng bạn có thể dùng Gemini thông qua OpenRouter.

Chi tiết hơn: [OpenRouter Models](https://openrouter.ai/docs#models)

## Dành cho người muốn dùng miễn phí với công sức rất thấp hoặc gần như không tốn công <a id="for-those-not-far-people-who-want-to-use-something-for-free-making-low-or-no-effort"></a>

> [!WARNING]
> 
> Tính năng miễn phí thường đi kèm giới hạn. Ứng dụng này là mã nguồn mở và được cung cấp theo trạng thái hiện có. Nó không cung cấp quyền truy cập premium miễn phí đầy đủ tới các API flagship của bên thứ ba.
> 
> Nếu bạn mong đợi quyền truy cập miễn phí premium đầy đủ, an toàn hơn khi dùng sản phẩm khác. Những câu hỏi như “api key không đúng” thường chỉ cần kiểm tra endpoint và cấu hình model của bạn. Cảm ơn bạn đã hiểu.
>
> Tất cả người dùng hợp lệ khác đều được chào đón.

## Nhà cung cấp API được hỗ trợ <a id="api-providers-supported"></a>

| Nhà cung cấp | Mức độ hỗ trợ | Ghi chú |
|---|---|---|
| OpenAI | Hỗ trợ đầy đủ | Đường tích hợp chính |
| GROQ | Hỗ trợ một phần | Một số tính năng có thể khác |
| Azure | Hỗ trợ một phần | Endpoint/model có thể khác theo nhà cung cấp |
| OpenRouter | Chỉ tạo văn bản | Đã kiểm thử với Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI |
| Khác | Được kiểm thử bởi cộng đồng | Ý kiến đóng góp luôn được hoan nghênh |

> [!NOTE]
> 
> Để đổi nhà cung cấp, mở cài đặt ứng dụng và chọn API endpoint. Bạn cũng có thể thêm endpoint OpenAI-compatible tùy chỉnh.

## Tính năng cơ bản <a id="basic-features"></a>

✅ Khả năng đã triển khai:

- [x] Chat (lưu nội bộ, hỗ trợ import/export)
- [x] Tạo ảnh
- [x] Nhận diện ảnh (đính kèm ảnh trong chat)
- [x] Prompt kích hoạt và workflow tin nhắn hệ thống
- [x] Nhập giọng nói (Whisper và Google)
- [x] Tích hợp trợ lý
- [x] SpeakGPT trong menu ngữ cảnh
- [x] SpeakGPT trong share sheet
- [x] Tính năng gọi hàm
- [x] Thư viện Prompts
- [x] Nhiều bố cục chat
- [x] Thiết kế thích ứng
- [x] Độ phủ rộng về mô hình
- [x] Không captcha
- [x] Mô hình dùng theo dung lượng
- [x] Hướng dẫn người dùng mới và onboarding
- [x] Hỗ trợ mô hình fine-tuned/custom
- [x] Chế độ tối AMOLED
- [x] Hỗ trợ nhà cung cấp API tùy chỉnh
- [x] Tùy chỉnh tham số mô hình (`temperature`, `topP`, `frequencyPenalty`, `presencePenalty`, `logit_bias`)
- [x] Playground
- [x] Truy cập các dòng flagship mới nhất như o1, o3, o4, gpt-4.1, gpt-4.5, gpt-image-1

## Cấu trúc dự án <a id="project-structure"></a>

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

## Yêu cầu trước <a id="prerequisites"></a>

- Android Studio (khuyến nghị bản stable hiện tại)
- Android SDK với `compileSdk 36`
- JDK 21 (`sourceCompatibility`/`targetCompatibility` đồng bộ với Java 21 trong cấu hình dự án)
- Git
- Kết nối internet cho dependencies Gradle và API provider

Thông tin hệ thống build từ cấu hình repo:

| Thành phần | Phiên bản / Giá trị |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Plugin Kotlin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## Cài đặt <a id="installation"></a>

### 1. Clone repository

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Mở trong Android Studio

- Mở `build.gradle` trong Android Studio.
- Đợi Gradle sync hoàn tất.

### 3. Build debug APK

```bash
./gradlew assembleDebug
```

### 4. Cài lên thiết bị/emulator đã kết nối

```bash
./gradlew installDebug
```

### 5. Kiểm tra chất lượng tùy chọn

```bash
./gradlew lint
```

## Sử dụng <a id="usage"></a>

### Luồng người dùng cuối (trong app)

1. Cài đặt app từ Google Play hoặc bản debug cục bộ.
2. Hoàn tất luồng onboarding.
3. Mở cài đặt API và chọn nhà cung cấp/endpoint.
4. Thêm API key hợp lệ (được lưu cục bộ trên thiết bị).
5. Chọn model và bắt đầu chat, vision, tạo ảnh, hoặc luồng giọng nói.

### Tích hợp Android có sẵn

- Tích hợp trợ lý (`ASSIST` intent)
- Tích hợp share sheet (`SEND`, `SEND_MULTIPLE` intents)
- Tích hợp xử lý văn bản (`PROCESS_TEXT`)
- Deep links cho `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Cấu hình <a id="configuration"></a>

### API endpoint và nhà cung cấp

- Mở **Settings** trong app.
- Chọn **API endpoint** để chuyển đổi giữa các nhà cung cấp tích hợp sẵn.
- Thêm endpoint tùy chỉnh nếu nhà cung cấp của bạn tương thích OpenAI.

### Tham số tạo câu trả lời

SpeakGPT hỗ trợ tinh chỉnh runtime cho:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Dữ liệu cục bộ và bảo mật

- Các cuộc hội thoại được lưu cục bộ và có thể import/export.
- Các giá trị nhạy cảm như API key được xử lý qua encrypted preferences.

### Ghi chú và giả định

- `google-services.json` tồn tại trong repo cho các bản build hiện tại; nếu bị xóa trong fork, một số tích hợp có thể cần cấu hình Firebase/App service tương đương.
- Hành vi nhà cung cấp có thể khác theo endpoint và dòng model.

## Ví dụ <a id="examples"></a>

### Build release APK

```bash
./gradlew assembleRelease
```

### Clean rebuild

```bash
./gradlew clean assembleDebug
```

### Sử dụng OpenRouter cho model family Gemini

1. Tạo API key OpenRouter.
2. Trong cài đặt SpeakGPT, chọn/thêm endpoint OpenRouter.
3. Chọn model tương thích Gemini.
4. Bắt đầu chat và kiểm tra phản hồi.

### Build toàn bộ từ sạch

```bash
./gradlew clean build
```

## Ghi chú phát triển <a id="development-notes"></a>

- Đây là dự án Android multi-module (`:app`, `:teslasoft-id`).
- Cả hai build type `debug` và `release` đều dùng `minifyEnabled true` và `shrinkResources true` trong cấu hình hiện tại.
- Quy tắc ProGuard/R8 nằm ở:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- Tài liệu web nhúng nằm tại:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Tài nguyên chuỗi đã localize nằm ở `app/src/main/res/values-*`.
- Bản dịch README nằm trong `i18n/` cho các ngôn ngữ.

## Khắc phục sự cố <a id="troubleshooting"></a>

| Vấn đề | Cần kiểm tra |
|---|---|
| Sai API key / lỗi xác thực | Xác nhận tính hợp lệ của key, khả năng tương thích nhà cung cấp và khả dụng model. Một số model flagship đòi hỏi xác minh tài khoản bổ sung. |
| Không khớp endpoint hoặc model | Kiểm tra custom endpoint của bạn tuân theo định dạng request/response tương thích OpenAI. Thử đổi preset endpoint trong Settings rồi thử lại. |
| Build bị lỗi | Xác nhận JDK 21 đang hoạt động, sync Gradle, kiểm tra Gradle wrapper là `8.13` bằng `./gradlew --version`, sau đó chạy `./gradlew clean build`. |
| Vấn đề runtime trên Android cũ | Dự án đặt `minSdk 28`. Cảnh báo lỗi thời cho Android 9/10/11 là mong đợi khi chính sách hỗ trợ thay đổi. |

## Lộ trình <a id="roadmap"></a>

### ❌ Kế hoạch sắp tới

- [ ] Tự động hóa theo thiết bị (đặt báo thức hoặc mở app)
- [ ] Đồng bộ lịch sử chat
- [ ] Cổng trao đổi prompts / luồng kiểu marketplace
- [ ] Hỗ trợ duyệt web/tools cho workflow truy cập internet chính thức

## An toàn khóa API <a id="api-key-safety"></a>

SpeakGPT dùng API key cho các request tới nhà cung cấp nên thông tin đăng nhập được giới hạn phạm vi và an toàn hơn so với luồng tài khoản/mật khẩu.

- Khóa API của bạn được lưu cục bộ và không được chia sẻ bởi app.
- Bạn có thể thu hồi key từ bảng điều khiển nhà cung cấp bất cứ lúc nào.
- Nếu cần, dùng một key riêng cho SpeakGPT.

Nhắc nhở bảo mật:

1. Giữ API key riêng cho SpeakGPT.
2. Thiết lập giới hạn thanh toán.
3. Bật theo dõi sử dụng để kiểm soát chi phí.
4. Thu hồi key khi phát hiện hoạt động đáng ngờ.

Tại sao bản build của ứng dụng bị obfuscate:

Obfuscation và resource shrinking giúp giảm kích thước package, cải thiện hiệu năng và giảm nguy cơ đảo ngược mã nguồn xung quanh xử lý credential. Bạn có thể yêu cầu bản build không bị obfuscate hoặc tự build.

> [!CAUTION]
> 
> Không cài bản build từ nguồn không đáng tin cậy. Bản build bên thứ ba có thể bị sửa đổi để chèn malware. Build chính thức được kiểm tra qua VirusTotal và phát hành qua kênh chính thống.

## Danh tính nhà phát triển <a id="developer-identity"></a>

| Trường | Giá trị |
|---|---|
| Tên nhà phát triển | Dmytro Ostapenko (AndraxDev) |
| Liên hệ | dostapenko82@gmail.com, +421951829517 |
| Địa chỉ pháp lý | Južná trieda 4B, 04001 Košice, Slovakia |
| Mã pháp nhân | 55545386 (D-U-N-S: 933739642) |
| Giấy phép hoạt động thương mại | OU-KE-OZP1-2023/031005-2 (Ban hành ngày 14/06/2023 theo Điều 10(1)(a) của Luật số 455/1991 về giấy phép thương mại, được sửa đổi) |
| Mã VAT | SK3121636045 |

(Bạn sẽ biết mình đang gửi tiền tới đâu nếu quyết định hỗ trợ dự án bằng tiền hoặc khi có tính năng trả phí trong tương lai.)

## Đóng góp <a id="contributing"></a>

Đóng góp được chào đón.

- Báo lỗi trong Issues với các bước tái hiện.
- Đề xuất tính năng mới với tiêu đề rõ ràng và bối cảnh.
- Giữ PR gọn, có lý do và ghi chú kiểm thử.

## ❤️ Support

| Donate | PayPal | Stripe |
| --- | --- | --- |
| [![Donate](https://camo.githubusercontent.com/24a4914f0b42c6f435f9e101621f1e52535b02c225764b2f6cc99416926004b7/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f446f6e6174652d4c617a79696e674172742d3045413545393f7374796c653d666f722d7468652d6261646765266c6f676f3d6b6f2d6669266c6f676f436f6c6f723d7768697465)](https://chat.lazying.art/donate) | [![PayPal](https://camo.githubusercontent.com/d0f57e8b016517a4b06961b24d0ca87d62fdba16e18bbdb6aba28e978dc0ea21/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f50617950616c2d526f6e677a686f754368656e2d3030343537433f7374796c653d666f722d7468652d6261646765266c6f676f3d70617970616c266c6f676f436f6c6f723d7768697465)](https://paypal.me/RongzhouChen) | [![Stripe](https://camo.githubusercontent.com/1152dfe04b6943afe3a8d2953676749603fb9f95e24088c92c97a01a897b4942/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f5374726970652d446f6e6174652d3633354246463f7374796c653d666f722d7468652d6261646765266c6f676f3d737472697065266c6f676f436f6c6f723d7768697465)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

## License <a id="license"></a>

Dự án này được cấp phép theo Apache License 2.0. Xem [LICENSE.md](LICENSE.md).

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
