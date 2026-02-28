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

SpeakGPT هو مساعد ذكاء اصطناعي مفتوح المصدر ومتقدم وبديهي جدًا لنظام Android. يدمج مزوّدي نماذج اللغة الكبيرة (LLM) الحديثة وسير العمل متعدد الوسائط (الدردشة، الصوت، توليد الصور، الرؤية) داخل تطبيق جوّال واحد.

يدعم رسميًا نماذج GPT وLLAMA وMIXTRAL وGEMMA وGemini (العادي وpro) Vision وDALL-E ونماذج أخرى.

| حقائق سريعة | التفاصيل |
|---|---|
| 📱 المنصة | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 نمط الاستخدام الأساسي | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 نوع التطبيق | عميل ذكاء اصطناعي مفتوح المصدر (وليس مزوّد API) |
| 🌐 الواجهة الويب المرافقة | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> هذا المشروع جزء من رسالة البكالوريوس الخاصة بي. يلزم الإسناد عند استخدام هذا العمل. حقوق النشر (c) 2023-2025 Dmytro Ostapenko. جميع الحقوق محفوظة.
>
> الاستشهاد: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> سنوقف قريبًا دعم إصدارات Android التالية: 9 و10 و11. السبب مرتبط بالتغييرات الحديثة في SDK والأمان. تستخدم الإصدارات الأقدم من Android ميزات مهملة وغير مستقرة مثل RenderScript.

## جدول المحتويات

- [التنزيل](#التنزيل)
- [SpeakGPT Web](#speakgpt-web)
- [نظرة عامة](#نظرة-عامة)
- [لقطات الشاشة](#لقطات-الشاشة)
- [معلومات للمستخدمين الذين يريدون استخدام نماذج Google Gemini مع هذا التطبيق](#معلومات-للمستخدمين-الذين-يريدون-استخدام-نماذج-google-gemini-مع-هذا-التطبيق)
- [لمن يريد شيئًا مجانيًا مع أقل جهد أو دون جهد](#لمن-يريد-شيئًا-مجانيًا-مع-أقل-جهد-أو-دون-جهد)
- [مزوّدو API المدعومون](#مزوّدو-api-المدعومون)
- [الميزات الأساسية](#الميزات-الأساسية)
- [هيكل المشروع](#هيكل-المشروع)
- [المتطلبات المسبقة](#المتطلبات-المسبقة)
- [التثبيت](#التثبيت)
- [الاستخدام](#الاستخدام)
- [الإعداد](#الإعداد)
- [أمثلة](#أمثلة)
- [ملاحظات التطوير](#ملاحظات-التطوير)
- [استكشاف الأخطاء وإصلاحها](#استكشاف-الأخطاء-وإصلاحها)
- [خريطة الطريق](#خريطة-الطريق)
- [أمان مفتاح API](#أمان-مفتاح-api)
- [هوية المطور](#هوية-المطور)
- [المساهمة](#المساهمة)
- [الدعم](#الدعم)
- [Buy me a coffee](#buy-me-a-coffee)
- [الترخيص](#الترخيص)

## التنزيل

📦 ثبّت التطبيق من Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 افتح SpeakGPT Web: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

مستودع GitHub: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## نظرة عامة

SpeakGPT هو عميل Android-first لواجهات AI API. صُمم بنمط bring-your-own-endpoint وbring-your-own-key، بحيث يمكن للمستخدم اختيار المزود والنموذج وملف التكلفة/الأداء المناسب.

بنية المستودع:

- `app`: وحدة تطبيق Android (`org.teslasoft.assistant`)
- `teslasoft-id`: وحدة مكتبة Android داخلية لأدوات المصادقة/العميل (`org.teslasoft.core.auth`)
- بيانات JSON الوصفية في جذر المستودع (`ai_sets.json`, `explore.json`, `experiment.json`) وتُستخدم لمجموعات النماذج والاكتشاف وسير عمل بأسلوب الاستيراد/التصدير
- `i18n/`: دليل إخراج README متعدد اللغات (موجود في المستودع)

## لقطات الشاشة

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

## معلومات للمستخدمين الذين يريدون استخدام نماذج Google Gemini مع هذا التطبيق

لا يدعم SpeakGPT مفاتيح Google API بشكل مباشر، ولكن يمكنك استخدام Google Gemini عبر OpenRouter API.

مزيد من المعلومات: [OpenRouter Models](https://openrouter.ai/docs#models)

## لمن يريد شيئًا مجانيًا مع أقل جهد أو دون جهد

> [!WARNING]
>
> تذكّر أن الجبن المجاني لا يوجد إلا في المصيدة. THIS APP IS OPEN-SOURCE CLIENT PROVIDED AS IS. ITSELF IT DOES NOT PROVIDE COMPLETELY FREE ACCESS TO THE PREMIUM FEATURES OF API PROVIDERS (LIKE FLAGSHIP AI MODELS AND SPECIAL FEATURES). IF YOU COME HERE TO USE OTHER'S WORK FOR FREE AND WITHOUT A CREDIT, IT'S BETTER YOU SKIP THIS APP AND LOOK FOR SOMETHING ELSE. I WILL NOT RESPOND TO YOUR "INCORRECT API KEY, WHY THIS APP REDIRECTS ME TO THE EXTERNAL SITE FOR API KEY?" QUESTIONS. THANK YOU FOR UNDERSTANDING.
> كل الأشخاص المتفهمين مرحّب بهم.

## مزوّدو API المدعومون

| المزود | مستوى الدعم | ملاحظات |
|---|---|---|
| OpenAI | دعم كامل | مسار التكامل الأساسي |
| GROQ | دعم جزئي | قد تختلف بعض الميزات |
| Azure | دعم جزئي | قد تختلف تفاصيل endpoint/model |
| OpenRouter | توليد النص فقط | تم اختباره مع نماذج Gemini وClaude وPerplexity وLlama وGemma وMistral وOpenAI |
| Other | مجرّب من المجتمع | نرحب بالملاحظات |

> [!NOTE]
>
> لتغيير مزود API، انتقل إلى الإعدادات واختر API endpoint. يمكنك أيضًا إضافة مزود API مخصص.

## الميزات الأساسية

✅ الإمكانات المُنفذة:

- [x] الدردشة (تُحفظ محليًا لكن يمكن استيرادها/تصديرها عند الحاجة)
- [x] توليد الصور
- [x] التعرّف على الصور (استخدم صورك وصور الكاميرا مع ChatGPT)
- [x] Activation prompt
- [x] System message
- [x] إدخال صوتي (Whisper وGoogle)
- [x] Assistant
- [x] SpeakGPT في قائمة السياق
- [x] SpeakGPT في Share sheet
- [x] ميزات Function calling
- [x] مكتبة Prompts
- [x] تخطيط دردشة مختلف
- [x] تصميم متكيف
- [x] عدد كبير من النماذج المختلفة
- [x] بدون captcha
- [x] نظام Pay as you go
- [x] نصائح للمبتدئين
- [x] دعم النماذج المخصصة fine-tuned
- [x] وضع AMOLED الداكن
- [x] دعم مزود API مخصص
- [x] تخصيص معاملات النموذج مثل `temperature`, `topP`, `frequencyPenalty`, `presencePenalty` و `logit_bias`
- [x] Playground
- [x] الوصول إلى أحدث النماذج الرائدة مثل o1 وo3 وo4 وgpt-4.1 وgpt-4.5 وgpt-image-1 (قد تتطلب بعض هذه النماذج التحقق من الهوية مع OpenAI)

## هيكل المشروع

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

## المتطلبات المسبقة

- Android Studio (يُنصح بالإصدار المستقر الحالي)
- Android SDK مع `compileSdk 36`
- JDK 21 (توافق source/target للمشروع هو Java 21)
- Git
- اتصال إنترنت لحل الاعتماديات والوصول إلى APIs الخاصة بمزودي النماذج

حقائق نظام البناء من إعدادات المستودع:

| المكوّن | الإصدار / القيمة |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## التثبيت

### 1. Clone repository

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Build debug APK

```bash
./gradlew assembleDebug
```

### 3. Install to connected device/emulator

```bash
./gradlew installDebug
```

### 4. Optional quality checks

```bash
./gradlew lint
```

## الاستخدام

### تدفق المستخدم النهائي (داخل التطبيق)

1. ثبّت التطبيق من Google Play أو من نسخة debug محلية.
2. أكمل خطوات التهيئة الأولى (onboarding).
3. افتح إعدادات API واختر endpoint/provider أو أضف واحدًا جديدًا.
4. أدخل مفتاح API (يُخزن محليًا على جهازك).
5. اختر النموذج وابدأ الدردشة أو الرؤية أو توليد الصور أو تدفقات العمل الصوتية.

### تكاملات Android المتاحة

- تكامل المساعد (`ASSIST` intent)
- تكامل Share sheet (`SEND` و `SEND_MULTIPLE` intents)
- تكامل Process text (`PROCESS_TEXT`)
- Deep links لـ `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## الإعداد

### API endpoints and providers

- افتح **Settings** في التطبيق.
- اختر **API endpoint** للتبديل بين المزودين المهيئين مسبقًا.
- أضف endpoint مخصصًا إذا كان مزودك متوافقًا مع OpenAI.

### معاملات النموذج والتوليد

يدعم SpeakGPT الضبط أثناء التشغيل لإعدادات التوليد مثل:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### البيانات المحلية والأمان

- تُخزن المحادثات محليًا ويمكن استيرادها/تصديرها.
- تُعالج القيم الحساسة مثل مفاتيح API ضمن تفضيلات مشفرة.

### ملاحظات وافتراضات

- الملف `google-services.json` موجود في هذا المستودع؛ إذا قمت بعمل fork وحذفته فقد تتطلب بعض التكاملات إعدادك الخاص.
- قد يختلف التوافق بين المزودين بحسب تنفيذ endpoint وعائلة النموذج.

## أمثلة

### Example 1: Build release APK

```bash
./gradlew assembleRelease
```

### Example 2: Clean rebuild

```bash
./gradlew clean assembleDebug
```

### Example 3: Use OpenRouter for Gemini-family models

1. أنشئ مفتاح OpenRouter API.
2. في إعدادات SpeakGPT، اختر/أضف OpenRouter endpoint.
3. اختر نموذج OpenRouter يدعم Gemini.
4. ابدأ محادثة وتحقق من توليد الاستجابة.

## ملاحظات التطوير

- هذا مشروع Android متعدد الوحدات (`:app`, `:teslasoft-id`).
- كل من نوعي البناء `debug` و`release` لديهما `minifyEnabled true` و`shrinkResources true` في الإعداد الحالي.
- قواعد ProGuard/R8 موجودة في:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- وثائق الويب المضمنة موجودة في:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- موارد الترجمة المحلية موجودة في `app/src/main/res/values-*`.
- دليل إخراج README متعدد اللغات موجود في `i18n/` (تُولَّد ملفات README الخاصة بكل لغة بشكل منفصل ضمن خطوات pipeline).

## استكشاف الأخطاء وإصلاحها

| المشكلة | ما الذي يجب التحقق منه |
|---|---|
| "Incorrect API key" أو فشل المصادقة | تحقّق من أن المفتاح صالح للمزود المحدد، وأن النموذج المحدد متاح لحسابك، وتحقق مما إذا كان المزود يتطلب تحققًا إضافيًا للنماذج الرائدة. |
| عدم تطابق endpoint/model | إذا كنت تستخدم endpoint مخصصًا لمزود، فتأكد من تنسيق request/response المتوافق مع OpenAI. جرّب التبديل إلى إعداد endpoint مُسبق في الإعدادات ثم أعد الاختبار. |
| مشاكل البناء | تأكد من تفعيل JDK 21، ثم قم بمزامنة مشروع Gradle في Android Studio، وشغّل `./gradlew --version` وتحقق أن الـ wrapper يستخدم Gradle `8.13`، ثم أعد المحاولة باستخدام `./gradlew clean build`. |
| مشاكل التشغيل على إصدارات Android القديمة | يدعم المشروع حاليًا `minSdk 28` (Android 9). ويحذر المشروع من أن دعم Android 9/10/11 قد يتم إيقافه مستقبلًا بسبب تغييرات SDK/الأمان. |

## خريطة الطريق

### ❌ Planned to add (Share your ideas in Issues)

- [ ] روتينات الجهاز (مثل ضبط المنبّه أو فتح تطبيق)
- [ ] مزامنة سجل الدردشة
- [ ] إضافة بوابة تبادل نماذج مثل متجر prompts
- [ ] قدرات تصفح رسمية (لتمكين نماذج GPT AI من الوصول إلى الإنترنت)

## أمان مفتاح API

يستخدم SpeakGPT واجهة OpenAI API لتقديم أفضل تجربة لك. استخدام مفاتيح API أكثر أمانًا من استخدام اسم المستخدم/كلمة المرور. لا يمكن الحصول على معلوماتك الشخصية باستخدام مفتاح API. توفّر OpenAI وصول API منخفض التكلفة إلى خدماتها. يتم تخزين مفتاح API محليًا على جهازك ولا تتم مشاركته مع أي طرف. لا يجمع SpeakGPT أي بيانات شخصية. SpeakGPT مفتوح المصدر ويمكنك التحقق من الكود بنفسك. يتم فحص كل إصدار من SpeakGPT عبر VirusTotal.
إذا كانت لديك أي مخاوف فيمكنك [revoke your API key](https://platform.openai.com/account/api-keys) أو استخدام مفتاح API منفصل لـ SpeakGPT.

لتأمين مفتاح API اتبع الخطوات التالية:

1. تأكد من امتلاك مفتاح API منفصل لـ SpeakGPT.
2. عيّن حدًا للفوترة.
3. فعّل مراقبة الاستخدام حتى تتمكن من رؤية مقدار الموارد التي يستخدمها SpeakGPT وتكلفتها.
4. إذا كانت لديك أي مخاوف يمكنك إلغاء مفتاح API.

> Why we obfuscate our code in production releases?
>
> يتيح لنا Obfuscation وتقليص الموارد تحسين حجم التطبيق وأدائه وتأمينه ضد الهندسة العكسية أو العبث، والتأكد من أن بيانات الاعتماد مثل مفاتيح API في مكان آمن. يمكنك طلب نسخة unobfuscated أو تجميع التطبيق بنفسك للتأكد من أن تطبيقنا آمن.

> [!CAUTION]
>
> احذر من البرمجيات الخبيثة! يمكنك تجميع SpeakGPT وتعديله، لكن كن شديد الحذر عندما يعرض عليك شخص آخر تثبيت نسخته. قد تحتوي هذه النسخ على برمجيات خبيثة. الإصدارات الرسمية لا تحتوي على برمجيات خبيثة ويتم فحصها بأكثر من 60 برنامج مكافحة فيروسات عبر VirusTotal. يمكنك العثور على تقرير VirusTotal في صفحة كل إصدار ومقارنة hash لملفات الـ binary.

## هوية المطور

| الحقل | القيمة |
|---|---|
| اسم المطور | Dmytro Ostapenko (AndraxDev) |
| معلومات التواصل | dostapenko82@gmail.com, +421951829517 |
| العنوان القانوني | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| معرف الكيان القانوني | 55545386 (D-U-N-S: 933739642) |
| ترخيص النشاط التجاري | OU-KE-OZP1-2023/031005-2 (Issued on 14 June 2023 according to the § 10 section 1 letter a) of the Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) as amended) |
| رقم ضريبة القيمة المضافة | SK3121636045 |

(حتى تعرف الجهة التي ترسل إليها أموالك إذا قررت دعم المشروع ماليًا أو إذا أصبح للمشروع ميزات مدفوعة مستقبلًا)

## المساهمة

المساهمات مرحب بها.

- أبلغ عن الأخطاء في Issues مع خطوات إعادة الإنتاج.
- اطلب ميزات جديدة (يرجى استخدام وسوم/تصنيفات واضحة للمشكلة).
- إذا أرسلت كودًا، اجعل التغييرات محددة النطاق وأرفق سببها.

## الدعم

### You are appreciated to

- الإبلاغ عن أي أخطاء
- دعمي :)
- طلب ميزات جديدة. لا تنسَ وسم المشكلة بعلامة

## Buy me a coffee

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## الترخيص

هذا المشروع مرخّص بموجب Apache License 2.0. راجع [LICENSE.md](LICENSE.md).

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
