[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Trợ lý AI mã nguồn mở ưu tiên Android với các luồng trò chuyện, giọng nói, thị giác và tạo ảnh.

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#quick-facts)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#prerequisites)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#prerequisites)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#license)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#prerequisites)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#prerequisites)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#prerequisites)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)

SpeakGPT là một trợ lý AI mã nguồn mở tiên tiến và trực quan cho Android. Nó tích hợp các nhà cung cấp mô hình ngôn ngữ lớn (LLM) hiện đại cùng các luồng đa phương thức (chat, giọng nói, tạo ảnh, nhận diện hình ảnh) vào một ứng dụng di động duy nhất.

Nói chung, nó hỗ trợ các mô hình GPT, LLAMA, MIXTRAL, GEMMA, Gemini Vision (thường và pro), DALL-E và các mô hình khác.

## Quick facts

| Thông tin nhanh | Chi tiết |
|---|---|
| 📱 Nền tảng | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Sử dụng cốt lõi | Bring-your-own-endpoint + Bring-your-own-key |
| 🧩 Loại ứng dụng | Khách hàng AI mã nguồn mở (không phải nhà cung cấp API) |
| 🌐 Phiên bản web đi kèm | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> Dự án này là một phần của luận văn tốt nghiệp của tôi. Cần ghi nhận tác giả khi sử dụng công trình này. Bản quyền (c) 2023-2025 Dmytro Ostapenko. All rights reserved.
>
> Trích dẫn: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> Chúng tôi sẽ ngừng hỗ trợ các phiên bản Android sau này trong thời gian tới: 9, 10, 11. Việc này liên quan tới các thay đổi gần đây của SDK và bảo mật. Các phiên bản Android cũ dùng các tính năng đã lỗi thời và không ổn định như RenderScript.

## Mục lục

- [Tải xuống](#tải-xuống)
- [SpeakGPT Web](#speakgpt-web)
- [Tổng quan](#tổng-quan)
- [Ảnh chụp màn hình](#ảnh-chụp-màn-hình)
- [Thông tin cho người muốn dùng Google Gemini với ứng dụng này](#thông-tin-cho-người-muốn-dùng-google-gemini-với-ứng-dụng-này)
- [Dành cho ai muốn dùng miễn phí với công sức rất thấp hoặc không phải tốn sức](#dành-cho-ai-muốn-dùng-miễn-phí-với-công-sức-rất-thấp-hoặc-không-phải-tốn-sức)
- [Nhà cung cấp API được hỗ trợ](#nhà-cung-cấp-api-được-hỗ-trợ)
- [Tính năng cơ bản](#tính-năng-cơ-bản)
- [Cấu trúc dự án](#cấu-trúc-dự-án)
- [Yêu cầu trước](#yêu-cầu-trước)
- [Cài đặt](#cài-đặt)
- [Cách sử dụng](#cách-sử-dụng)
- [Cấu hình](#cấu-hình)
- [Ví dụ](#ví-dụ)
- [Ghi chú phát triển](#ghi-chú-phát-triển)
- [Khắc phục sự cố](#khắc-phục-sự-cố)
- [Lộ trình](#lộ-trình)
- [An toàn API key](#an-toàn-api-key)
- [Danh tính nhà phát triển](#danh-tính-nhà-phát-triển)
- [Đóng góp](#đóng-góp)
- [❤️ Support](#-support)
- [Giấy phép](#giấy-phép)

## Tải xuống

📦 Cài đặt từ Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Mở SpeakGPT Web: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub repo: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Tổng quan

SpeakGPT là một client Android-first cho các API AI. Ứng dụng được thiết kế theo mô hình bring-your-own-endpoint và bring-your-own-key, để người dùng có thể chọn nhà cung cấp, mô hình và hồ sơ chi phí/hiệu năng phù hợp.

### Tóm tắt nhanh

| Phạm vi | Tóm tắt |
|---|---|
| 💬 Trải nghiệm chính | Chat, tạo ảnh, nhận diện ảnh, nhập giọng nói, tích hợp trợ lý |
| 🔌 Chiến lược nhà cung cấp | Các endpoint tương thích OpenAI với nhà cung cấp và endpoint tùy chỉnh |
| 🔐 Xử lý dữ liệu | API key được lưu cục bộ; cuộc trò chuyện có thể import/export |
| 🧱 Ngăn xếp xây dựng | Dự án Android multi-module dùng AGP `8.12.2`, Gradle `8.13`, Kotlin `2.2.10` |

Kiến trúc repository:

- `app`: module ứng dụng Android (`org.teslasoft.assistant`)
- `teslasoft-id`: module thư viện nội bộ Android cho các tiện ích xác thực/khách hàng (`org.teslasoft.core.auth`)
- Metadata dạng JSON ở gốc repository (`ai_sets.json`, `explore.json`, `experiment.json`) dùng cho bộ mô hình, khám phá và luồng import/export
- `i18n/`: thư mục đầu ra README đa ngôn ngữ (có trong repository)

## Ảnh chụp màn hình

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

## Thông tin cho người muốn dùng Google Gemini với ứng dụng này

SpeakGPT bản thân không hỗ trợ Google API key, nhưng bạn vẫn có thể dùng Google Gemini qua OpenRouter API.

Thông tin thêm: [OpenRouter Models](https://openrouter.ai/docs#models)

## Dành cho ai muốn dùng miễn phí với công sức rất thấp hoặc không phải tốn sức

> [!WARNING]
>
> Nhớ rằng phô mai miễn phí thường chỉ có trong bẫy chuột. ỨNG DỤNG NÀY LÀ CLIENT MÃ NGUỒN MỞ VÀ ĐƯỢC CUNG CẤP NGUYÊN TRẠNG. CHÍNH NÓ KHÔNG CẤP QUYỀN TRUY CẬP MIỄN PHÍ HOÀN TOÀN VÀO CÁC TÍNH NĂNG CAO CẤP CỦA CÁC NHÀ CUNG CẤP API (NHƯ MỘT SỐ MÔ HÌNH AI HÀNG ĐẦU VÀ TÍNH NĂNG ĐẶC BIỆT). NẾU BẠN ĐẾN ĐÂY ĐỂ DÙNG CÔNG CỤ CỦA NGƯỜI KHÁC HOÀN TOÀN MIỄN PHÍ VÀ KHÔNG THANH TOÁN, TỐT NHẤT BẠN HÃY BỎ QUA ỨNG DỤNG NÀY VÀ TÌM GIẢI PHÁP KHÁC. TÔI SẼ KHÔNG TRẢ LỜI CÁC CÂU HỎI NHƯ “API KEY SAI, TẠI SAO ỨNG DỤNG ĐƯỢC CHUYỂN HƯỚNG TỚI SITE NGOÀI ĐỂ LẤY API KEY?”. CẢM ƠN BẠN ĐÃ HIỂU.
> Tất cả các bạn dùng nghiêm túc khác đều được hoan nghênh.

## Nhà cung cấp API được hỗ trợ

| Nhà cung cấp | Mức hỗ trợ | Ghi chú |
|---|---|---|
| OpenAI | Hỗ trợ đầy đủ | Đường dẫn tích hợp chính |
| GROQ | Hỗ trợ một phần | Một số tính năng có thể thay đổi |
| Azure | Hỗ trợ một phần | Endpoint/mô hình có thể khác nhau tùy cài đặt |
| OpenRouter | Chỉ tạo văn bản | Đã kiểm thử với Gemini, Claude, Perplexity, Llama, Gemma, Mistral, mô hình OpenAI |
| Khác | Được cộng đồng kiểm tra | Ý kiến phản hồi luôn được chào đón |

> [!NOTE]
>
> Để đổi nhà cung cấp API, vào Cài đặt và chọn API endpoint. Bạn cũng có thể thêm endpoint API tùy chỉnh.

## Tính năng cơ bản

✅ Khả năng đã triển khai:

- [x] Chat (lưu cục bộ, nhưng có thể import/export khi cần)
- [x] Tạo ảnh
- [x] Nhận diện ảnh (dùng ảnh và ảnh chụp của bạn cùng ChatGPT)
- [x] Mẫu kích hoạt (activation prompt)
- [x] Tin nhắn hệ thống (system message)
- [x] Nhập giọng nói (Whisper và Google)
- [x] Assistant
- [x] SpeakGPT trong menu ngữ cảnh
- [x] SpeakGPT trong Share sheet
- [x] Tính năng gọi hàm (function calling)
- [x] Thư viện Prompts
- [x] Bố cục chat khác nhau
- [x] Giao diện thích ứng
- [x] Rất nhiều mô hình khác nhau
- [x] Không captcha
- [x] Mô hình thanh toán theo mức sử dụng
- [x] Mẹo cho người mới
- [x] Hỗ trợ mô hình fine-tuned tùy chỉnh
- [x] Chế độ tối AMOLED
- [x] Hỗ trợ nhà cung cấp API tùy chỉnh
- [x] Tùy chỉnh tham số mô hình như `temperature`, `topP`, `frequencyPenalty`, `presencePenalty` và `logit_bias`
- [x] Playground
- [x] Truy cập các mô hình flagship mới nhất như o1, o3, o4, gpt-4.1, gpt-4.5 và gpt-image-1 (một số mô hình có thể yêu cầu xác minh danh tính với OpenAI)

## Cấu trúc dự án

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

## Yêu cầu trước

- Android Studio (khuyến nghị phiên bản stable hiện tại)
- Android SDK với `compileSdk 36`
- JDK 21 (dự án đặt source/target compatibility là Java 21)
- Git
- Kết nối internet để giải quyết dependency và gọi API của nhà cung cấp mô hình

Thông tin build system từ cấu hình repository:

| Thành phần | Phiên bản / Giá trị |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Plugin Kotlin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## Cài đặt

### 1. Clone repository

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Build debug APK

```bash
./gradlew assembleDebug
```

### 3. Cài đặt lên thiết bị/emulator đã kết nối

```bash
./gradlew installDebug
```

### 4. Kiểm tra chất lượng tùy chọn

```bash
./gradlew lint
```

## Cách sử dụng

### Luồng cho người dùng cuối (trong app)

1. Cài app từ Google Play hoặc bản debug build cục bộ.
2. Hoàn tất luồng onboarding.
3. Mở cài đặt API và chọn hoặc thêm endpoint/provider.
4. Nhập API key (được lưu cục bộ trên thiết bị).
5. Chọn mô hình và bắt đầu chat, thị giác, tạo ảnh hoặc luồng giọng nói.

### Tích hợp Android có sẵn

- Tích hợp Assistant (`ASSIST` intent)
- Tích hợp Share sheet (`SEND` và `SEND_MULTIPLE` intents)
- Tích hợp xử lý văn bản (`PROCESS_TEXT`)
- Deep links cho `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Cấu hình

### API endpoints và nhà cung cấp

- Mở **Settings** trong app.
- Chọn **API endpoint** để chuyển giữa các nhà cung cấp đã cấu hình sẵn.
- Thêm endpoint tùy chỉnh nếu nhà cung cấp của bạn tương thích với OpenAI.

### Mô hình và tham số tạo sinh

SpeakGPT hỗ trợ tinh chỉnh thời gian chạy cho các tham số tạo sinh như:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Dữ liệu cục bộ và bảo mật

- Cuộc trò chuyện được lưu cục bộ và có thể import/export.
- Các giá trị nhạy cảm như API key được xử lý bằng encrypted preferences.

### Ghi chú và giả định

- `google-services.json` có trong repository này; nếu bạn fork rồi xóa nó, một số tích hợp có thể cần cấu hình riêng của bạn.
- Khả năng tương thích của nhà cung cấp có thể khác nhau theo từng implement endpoint và họ mô hình.

## Ví dụ

### Ví dụ 1: Build release APK

```bash
./gradlew assembleRelease
```

### Ví dụ 2: Rebuild sạch

```bash
./gradlew clean assembleDebug
```

### Ví dụ 3: Dùng OpenRouter cho các mô hình họ Gemini

1. Tạo OpenRouter API key.
2. Trong cài đặt SpeakGPT, chọn/thêm endpoint OpenRouter.
3. Chọn mô hình OpenRouter hỗ trợ Gemini.
4. Mở chat và kiểm tra đầu ra phản hồi.

## Ghi chú phát triển

- Đây là dự án Android đa module (`:app`, `:teslasoft-id`).
- `debug` và `release` build types đều có `minifyEnabled true` và `shrinkResources true` trong cấu hình hiện tại.
- Quy tắc ProGuard/R8 nằm trong:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- Tài liệu web nhúng nằm tại:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Tài nguyên bản địa hóa nằm trong `app/src/main/res/values-*`.
- Thư mục đầu ra README i18n nằm ở `i18n/` (các file README theo ngôn ngữ được sinh riêng trong từng bước pipeline).

## Khắc phục sự cố

| Sự cố | Việc cần kiểm tra |
|---|---|
| "Incorrect API key" hoặc lỗi xác thực | Kiểm tra key của bạn có hợp lệ cho nhà cung cấp đã chọn, mô hình đã chọn có sẵn cho tài khoản của bạn, và nhà cung cấp có yêu cầu xác minh thêm cho các mô hình flagship hay không. |
| Endpoint/model không khớp | Nếu dùng endpoint tùy chỉnh, đảm bảo định dạng request/response tương thích OpenAI. Hãy thử đổi preset endpoint trong cài đặt và kiểm tra lại. |
| Vấn đề build | Xác nhận JDK 21 đang hoạt động, đồng bộ dự án Gradle trong Android Studio, chạy `./gradlew --version` và kiểm tra wrapper đang dùng Gradle `8.13`, sau đó thử lại với `./gradlew clean build`. |
| Vấn đề runtime trên Android cũ | Dự án hiện hỗ trợ `minSdk 28` (Android 9). Dự án cảnh báo sẽ ngừng hỗ trợ Android 9/10/11 trong tương lai do thay đổi SDK/bảo mật. |

## Lộ trình

### ❌ Dự kiến bổ sung (chia sẻ ý tưởng của bạn trong Issues)

- [ ] Các quy trình thiết bị (như đặt báo thức hoặc mở app)
- [ ] Đồng bộ lịch sử chat
- [ ] Thêm cổng trao đổi mô hình như kho prompts
- [ ] Khả năng duyệt web chính thức (cho phép mô hình GPT AI truy cập internet)

## An toàn API key

SpeakGPT sử dụng OpenAI API để mang lại trải nghiệm tốt nhất cho bạn. Dùng API key an toàn hơn việc dùng username/password. Thông tin cá nhân của bạn không thể bị lấy thông qua API key. OpenAI cung cấp quyền truy cập API với chi phí thấp cho dịch vụ của họ. API key của bạn được lưu cục bộ trên thiết bị và không được chia sẻ cho bất kỳ ai. SpeakGPT không thu thập dữ liệu cá nhân. SpeakGPT là mã nguồn mở và bạn có thể kiểm tra mã nguồn trực tiếp. Mỗi bản phát hành của SpeakGPT đều được kiểm tra trên VirusTotal.
Nếu bạn có lo ngại nào, bạn có thể [thu hồi API key](https://platform.openai.com/account/api-keys) hoặc dùng API key riêng cho SpeakGPT.

Để bảo mật API key, thực hiện theo các bước sau:

1. Đảm bảo bạn có một API key riêng cho SpeakGPT.
2. Thiết lập giới hạn thanh toán.
3. Bật giám sát sử dụng, để bạn thấy SpeakGPT sử dụng bao nhiêu tài nguyên và tốn bao nhiêu chi phí.
4. Nếu còn băn khoăn, bạn có thể thu hồi API key.

> Why we obfuscate our code in production releases?
>
> Việc obfuscate và thu gọn tài nguyên giúp tối ưu dung lượng app, hiệu năng và bảo vệ trước reverse engineering hoặc chỉnh sửa trái phép, đồng thời đảm bảo thông tin đăng nhập như API key được lưu ở nơi an toàn. Bạn có thể yêu cầu bản build không obfuscate hoặc tự biên dịch để tự kiểm tra app của chúng tôi an toàn.

> [!CAUTION]
>
> CẨN THẬN MÃ ĐỘC! Bạn có quyền biên dịch và chỉnh sửa SpeakGPT, nhưng hãy cực kỳ cẩn thận khi ai đó đề nghị bạn cài bản build do họ làm. Bản build như vậy có thể chứa mã độc. Bản build chính thức không chứa mã độc và được kiểm tra bởi hơn 60 phần mềm diệt virus khác nhau qua VirusTotal. Bạn có thể xem báo cáo VirusTotal trên từng trang phát hành và so sánh hash của tệp nhị phân.

## Danh tính nhà phát triển

| Trường | Giá trị |
|---|---|
| Tên nhà phát triển | Dmytro Ostapenko (AndraxDev) |
| Liên hệ | dostapenko82@gmail.com, +421951829517 |
| Địa chỉ pháp lý | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Mã pháp nhân | 55545386 (D-U-N-S: 933739642) |
| Giấy phép hoạt động thương mại | OU-KE-OZP1-2023/031005-2 (Phát hành ngày 14 June 2023 theo Điều 10 khoản 1 điểm a) của Luật số 455/1991 Coll. về cấp phép thương mại (Trade Licensing Act) theo sửa đổi) |
| Mã số VAT | SK3121636045 |

(Nhằm giúp bạn biết tiền của mình đang gửi cho ai nếu quyết định hỗ trợ tài chính cho dự án hoặc nếu sau này dự án có tính năng trả phí)

## Đóng góp

Mọi đóng góp đều được hoan nghênh.

- Báo lỗi trong Issues kèm bước tái hiện.
- Đề xuất tính năng mới (xin dùng nhãn/tag rõ ràng).
- Nếu bạn gửi code, hãy giới hạn phạm vi thay đổi và nêu rõ lý do.

## ❤️ Support

| Donate | PayPal | Stripe |
|---|---|---|
| [![Donate](https://img.shields.io/badge/Donate-LazyingArt-0EA5E9?style=for-the-badge&logo=ko-fi&logoColor=white)](https://chat.lazying.art/donate) | [![PayPal](https://img.shields.io/badge/PayPal-RongzhouChen-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/RongzhouChen) | [![Stripe](https://img.shields.io/badge/Stripe-Donate-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

### Bạn đóng góp giá trị cho dự án

- Báo cáo mọi lỗi
- Ủng hộ tôi :)
- Đề xuất tính năng mới. Đừng quên gắn tag cho issue

### Mời tôi một ly cà phê

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## Giấy phép

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
