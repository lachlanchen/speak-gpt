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

SpeakGPT là một trợ lý AI mã nguồn mở tiên tiến, trực quan cao dành cho Android. Ứng dụng tích hợp các nhà cung cấp mô hình ngôn ngữ lớn (LLM) hiện đại và các quy trình đa phương thức (chat, giọng nói, tạo ảnh, thị giác) trong một app di động duy nhất.

Chính thức hỗ trợ các mô hình GPT, LLAMA, MIXTRAL, GEMMA, Gemini (bản thường và pro) Vision, DALL-E và các mô hình khác.

| Thông tin nhanh | Chi tiết |
|---|---|
| 📱 Nền tảng | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Cách sử dụng cốt lõi | Tự cung cấp endpoint + tự cung cấp API key |
| 🧩 Loại ứng dụng | AI client mã nguồn mở (không phải nhà cung cấp API) |
| 🌐 Bản web đồng hành | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> Dự án này là một phần trong luận văn Cử nhân của tôi. Cần ghi công khi sử dụng công trình này. Copyright (c) 2023-2025 Dmytro Ostapenko. Mọi quyền được bảo lưu.
>
> Trích dẫn: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> Chúng tôi sẽ sớm ngừng hỗ trợ các phiên bản Android sau: 9, 10, 11. Điều này liên quan đến các thay đổi gần đây về SDK và bảo mật. Các phiên bản Android cũ dùng các tính năng đã lỗi thời và thiếu ổn định như RenderScript.

## Mục lục

- [Tải xuống](#tải-xuống)
- [SpeakGPT Web](#speakgpt-web)
- [Tổng quan](#tổng-quan)
- [Ảnh chụp màn hình](#ảnh-chụp-màn-hình)
- [Thông tin cho người dùng muốn dùng mô hình Google Gemini với ứng dụng này](#thông-tin-cho-người-dùng-muốn-dùng-mô-hình-google-gemini-với-ứng-dụng-này)
- [Dành cho những ai muốn dùng miễn phí với rất ít hoặc không cần nỗ lực](#dành-cho-những-ai-muốn-dùng-miễn-phí-với-rất-ít-hoặc-không-cần-nỗ-lực)
- [Các nhà cung cấp API được hỗ trợ](#các-nhà-cung-cấp-api-được-hỗ-trợ)
- [Tính năng cơ bản](#tính-năng-cơ-bản)
- [Cấu trúc dự án](#cấu-trúc-dự-án)
- [Điều kiện tiên quyết](#điều-kiện-tiên-quyết)
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
- [Hỗ trợ](#hỗ-trợ)
- [Mời tôi một ly cà phê](#mời-tôi-một-ly-cà-phê)
- [Giấy phép](#giấy-phép)

## Tải xuống

📦 Cài đặt từ Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Mở SpeakGPT Web: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub repo: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Tổng quan

SpeakGPT là một client Android-first cho các API AI. Ứng dụng được thiết kế theo hướng tự cung cấp endpoint và API key, để người dùng có thể chọn nhà cung cấp, mô hình, cũng như mức chi phí/hiệu năng phù hợp.

Kiến trúc repository:

- `app`: module ứng dụng Android (`org.teslasoft.assistant`)
- `teslasoft-id`: module thư viện Android nội bộ cho tiện ích auth/client (`org.teslasoft.core.auth`)
- Metadata JSON ở thư mục gốc repository (`ai_sets.json`, `explore.json`, `experiment.json`) dùng cho bộ mô hình, khám phá và luồng import/export
- `i18n/`: thư mục đầu ra README đa ngôn ngữ (có sẵn trong repository)

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

## Thông tin cho người dùng muốn dùng mô hình Google Gemini với ứng dụng này

SpeakGPT không tự hỗ trợ Google API key, nhưng bạn vẫn có thể dùng Google Gemini thông qua OpenRouter API.

Thông tin thêm: [OpenRouter Models](https://openrouter.ai/docs#models)

## Dành cho những ai muốn dùng miễn phí với rất ít hoặc không cần nỗ lực

> [!WARNING]
>
> Hãy nhớ rằng “miếng pho mát miễn phí chỉ có trong bẫy chuột”. ỨNG DỤNG NÀY LÀ MỘT CLIENT MÃ NGUỒN MỞ, CUNG CẤP THEO HIỆN TRẠNG. BẢN THÂN NÓ KHÔNG CUNG CẤP QUYỀN TRUY CẬP HOÀN TOÀN MIỄN PHÍ VÀO CÁC TÍNH NĂNG CAO CẤP CỦA NHÀ CUNG CẤP API (NHƯ CÁC MÔ HÌNH AI FLAGSHIP VÀ TÍNH NĂNG ĐẶC BIỆT). NẾU BẠN ĐẾN ĐÂY ĐỂ DÙNG CÔNG SỨC CỦA NGƯỜI KHÁC MIỄN PHÍ VÀ KHÔNG TRẢ PHÍ, TỐT NHẤT HÃY BỎ QUA ỨNG DỤNG NÀY VÀ TÌM THỨ KHÁC. TÔI SẼ KHÔNG TRẢ LỜI CÁC CÂU HỎI KIỂU “API KEY SAI, TẠI SAO APP LẠI CHUYỂN TÔI SANG TRANG NGOÀI ĐỂ LẤY API KEY?”. CẢM ƠN BẠN ĐÃ HIỂU.
> Tất cả những người dùng nghiêm túc khác đều được chào đón.

## Các nhà cung cấp API được hỗ trợ

| Provider | Mức hỗ trợ | Ghi chú |
|---|---|---|
| OpenAI | Hỗ trợ đầy đủ | Luồng tích hợp chính |
| GROQ | Hỗ trợ một phần | Một số tính năng có thể khác nhau |
| Azure | Hỗ trợ một phần | Chi tiết endpoint/mô hình có thể khác nhau |
| OpenRouter | Chỉ tạo văn bản | Đã thử nghiệm với Gemini, Claude, Perplexity, Llama, Gemma, Mistral, mô hình OpenAI |
| Other | Được cộng đồng thử nghiệm | Hoan nghênh phản hồi |

> [!NOTE]
>
> Để đổi nhà cung cấp API, vào phần cài đặt và chọn API endpoint. Bạn cũng có thể thêm nhà cung cấp API tùy chỉnh của riêng mình.

## Tính năng cơ bản

✅ Khả năng đã triển khai:

- [x] Chat (lưu cục bộ nhưng có thể import/export khi cần)
- [x] Tạo ảnh
- [x] Nhận diện ảnh (dùng ảnh/hình chụp của bạn với ChatGPT)
- [x] Activation prompt
- [x] System message
- [x] Voice input (Whisper và Google)
- [x] Assistant
- [x] SpeakGPT trong context menu
- [x] SpeakGPT trong Share sheet
- [x] Tính năng function calling
- [x] Thư viện prompt
- [x] Bố cục chat khác nhau
- [x] Thiết kế thích ứng
- [x] Nhiều mô hình khác nhau
- [x] Không captcha
- [x] Hệ thống trả theo mức dùng (pay as you go)
- [x] Mẹo cho người mới
- [x] Hỗ trợ mô hình fine-tuned tùy chỉnh
- [x] Chế độ tối AMOLED
- [x] Hỗ trợ nhà cung cấp API tùy chỉnh
- [x] Tùy chỉnh tham số mô hình như `temperature`, `topP`, `frequencyPenalty`, `presencePenalty` và `logit_bias`
- [x] Playground
- [x] Truy cập các mô hình flagship mới nhất như o1, o3, o4, gpt-4.1, gpt-4.5 và gpt-image-1 (Một số mô hình này có thể yêu cầu bạn xác minh danh tính với OpenAI)

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

## Điều kiện tiên quyết

- Android Studio (khuyến nghị bản stable mới nhất)
- Android SDK với `compileSdk 36`
- JDK 21 (source/target compatibility của dự án là Java 21)
- Git
- Kết nối Internet để tải dependency và gọi API từ nhà cung cấp mô hình

Thông tin build system từ cấu hình repository:

| Component | Version / Value |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
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

### 3. Cài lên thiết bị/emulator đã kết nối

```bash
./gradlew installDebug
```

### 4. Kiểm tra chất lượng (tùy chọn)

```bash
./gradlew lint
```

## Cách sử dụng

### Luồng cho người dùng cuối (trong app)

1. Cài app từ Google Play hoặc từ bản debug build cục bộ.
2. Hoàn tất quy trình onboarding.
3. Mở API settings và chọn hoặc thêm endpoint/provider của bạn.
4. Nhập API key (được lưu cục bộ trên thiết bị).
5. Chọn mô hình và bắt đầu chat, thị giác, tạo ảnh hoặc luồng giọng nói.

### Các tích hợp Android khả dụng

- Tích hợp Assistant (`ASSIST` intent)
- Tích hợp Share sheet (`SEND` và `SEND_MULTIPLE` intents)
- Tích hợp xử lý văn bản (`PROCESS_TEXT`)
- Deep link cho `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Cấu hình

### API endpoints và providers

- Mở **Settings** trong app.
- Chọn **API endpoint** để chuyển giữa các nhà cung cấp được cấu hình sẵn.
- Thêm endpoint tùy chỉnh nếu nhà cung cấp của bạn tương thích OpenAI.

### Mô hình và tham số tạo sinh

SpeakGPT hỗ trợ tinh chỉnh runtime cho các thiết lập tạo sinh như:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Dữ liệu cục bộ và bảo mật

- Hội thoại được lưu cục bộ và có thể import/export.
- Các giá trị nhạy cảm như API key được xử lý trong encrypted preferences.

### Ghi chú và giả định

- `google-services.json` có trong repository này; nếu bạn fork rồi xóa file này, một số tích hợp có thể cần cấu hình riêng của bạn.
- Khả năng tương thích provider có thể khác nhau tùy cách endpoint và họ mô hình được triển khai.

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
2. Trong phần cài đặt SpeakGPT, chọn/thêm endpoint OpenRouter.
3. Chọn mô hình OpenRouter có hỗ trợ Gemini.
4. Bắt đầu một cuộc chat và xác nhận phản hồi được tạo.

## Ghi chú phát triển

- Đây là dự án Android đa module (`:app`, `:teslasoft-id`).
- `debug` và `release` đều có `minifyEnabled true` và `shrinkResources true` trong cấu hình hiện tại.
- Quy tắc ProGuard/R8 nằm tại:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- Tài liệu web nhúng nằm tại:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Tài nguyên bản địa hóa nằm trong `app/src/main/res/values-*`.
- Thư mục đầu ra i18n README nằm ở `i18n/` (các file README theo ngôn ngữ được tạo riêng trong các bước pipeline).

## Khắc phục sự cố

| Sự cố | Cần kiểm tra |
|---|---|
| "Incorrect API key" hoặc lỗi xác thực | Xác minh key hợp lệ với provider đã chọn, xác minh mô hình đã chọn có sẵn cho tài khoản của bạn, và kiểm tra xem provider có yêu cầu xác minh bổ sung cho các mô hình flagship hay không. |
| Endpoint/model không khớp | Nếu dùng endpoint tùy chỉnh, hãy đảm bảo định dạng request/response tương thích OpenAI. Thử chuyển endpoint preset trong cài đặt rồi kiểm tra lại. |
| Vấn đề build | Xác nhận đang dùng JDK 21, sync dự án Gradle trong Android Studio, chạy `./gradlew --version` và xác minh wrapper dùng Gradle `8.13`, sau đó thử lại với `./gradlew clean build`. |
| Lỗi runtime trên Android cũ | Dự án hiện hỗ trợ `minSdk 28` (Android 9). Dự án cảnh báo có thể ngừng hỗ trợ Android 9/10/11 trong tương lai do thay đổi về SDK/bảo mật. |

## Lộ trình

### ❌ Dự kiến bổ sung (Hãy chia sẻ ý tưởng của bạn trong Issues)

- [ ] Routine trên thiết bị (ví dụ đặt báo thức hoặc mở app)
- [ ] Đồng bộ lịch sử chat
- [ ] Thêm cổng trao đổi mô hình như kho prompt
- [ ] Khả năng duyệt web chính thức (cho mô hình GPT AI truy cập Internet)

## An toàn API key

SpeakGPT sử dụng OpenAI API để mang lại trải nghiệm tốt nhất cho bạn. Dùng API key an toàn hơn dùng username/password. Không thể lấy thông tin cá nhân của bạn chỉ từ API key. OpenAI cung cấp quyền truy cập API với chi phí hợp lý. API key của bạn được lưu cục bộ trên thiết bị và không chia sẻ với bất kỳ ai. SpeakGPT không thu thập dữ liệu cá nhân. SpeakGPT là mã nguồn mở và bạn có thể tự kiểm tra mã nguồn. Mỗi bản phát hành SpeakGPT đều được kiểm tra trên VirusTotal.
Nếu có bất kỳ lo ngại nào, bạn có thể [thu hồi API key](https://platform.openai.com/account/api-keys) hoặc dùng một API key riêng cho SpeakGPT.

Để bảo mật API key, hãy thực hiện các bước sau:

1. Đảm bảo bạn có API key riêng cho SpeakGPT.
2. Thiết lập giới hạn thanh toán.
3. Bật giám sát sử dụng để theo dõi SpeakGPT dùng bao nhiêu tài nguyên và tốn bao nhiêu chi phí.
4. Nếu có lo ngại, bạn có thể thu hồi API key.

> Tại sao chúng tôi làm rối mã trong các bản phát hành production?
>
> Obfuscation và resource shrinking giúp tối ưu kích thước app, hiệu năng, đồng thời tăng khả năng bảo vệ trước reverse engineering hoặc chỉnh sửa trái phép, và đảm bảo thông tin xác thực như API key được giữ an toàn. Bạn có thể yêu cầu bản build không obfuscate hoặc tự biên dịch để tự xác minh app an toàn.

> [!CAUTION]
>
> HÃY CẨN THẬN VỚI MÃ ĐỘC! Bạn được phép biên dịch SpeakGPT và chỉnh sửa nó, nhưng hãy thật cẩn trọng nếu ai đó đề nghị bạn cài bản build của họ. Những bản build như vậy có thể chứa mã độc. Các bản build chính thức không chứa mã độc và được kiểm tra bởi hơn 60 chương trình diệt virus khác nhau thông qua VirusTotal. Bạn có thể xem báo cáo VirusTotal ở mỗi trang phát hành và đối chiếu hash của file nhị phân.

## Danh tính nhà phát triển

| Field | Value |
|---|---|
| Developer name | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Legal address | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Legal entity ID | 55545386 (D-U-N-S: 933739642) |
| Commercial activity license | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to the § 10 section 1 letter a) of the Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) as amended) |
| VAT ID | SK3121636045 |

(Để bạn biết mình đang gửi tiền cho ai nếu quyết định hỗ trợ tài chính cho dự án hoặc nếu dự án có tính năng trả phí trong tương lai)

## Đóng góp

Hoan nghênh mọi đóng góp.

- Báo lỗi trong Issues kèm các bước tái hiện.
- Đề xuất tính năng mới (vui lòng dùng tag/label rõ ràng).
- Nếu bạn gửi code, hãy giữ thay đổi trong phạm vi nhỏ và nêu rõ lý do.

## Hỗ trợ

### Chúng tôi rất trân trọng nếu bạn

- Báo mọi lỗi bạn gặp
- Ủng hộ tôi :)
- Đề xuất tính năng mới. Đừng quên gắn tag cho issue

## Mời tôi một ly cà phê

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
