[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Android-first, Open Source KI-Assistent mit Chat-, Sprach-, Vision- und Bildgenerierungs-Workflows.

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#kurzinfos)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#voraussetzungen)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#voraussetzungen)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#lizenz)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#voraussetzungen)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#voraussetzungen)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#voraussetzungen)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)

SpeakGPT ist ein fortschrittlicher und sehr intuitiver Open-Source-KI-Assistent für Android. Er integriert moderne Large-Language-Model-Anbieter (LLM) und multimodale Workflows (Chat, Sprache, Bildgenerierung, Vision) in einer einzelnen mobilen App.

Offiziell werden GPT-Modelle, LLAMA, MIXTRAL, GEMMA, Gemini (regular und pro) Vision, DALL-E und weitere Modelle unterstützt.

## Kurzinfos

| Kurzinfos | Details |
|---|---|
| 📱 Plattform | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Kernnutzung | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 App-Typ | Open-Source-AI-Client (kein API-Anbieter) |
| 🌐 Web-Begleiter | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> Dieses Projekt ist Teil meiner Bachelorarbeit. Eine Namensnennung ist erforderlich, wenn diese Arbeit genutzt wird. Copyright (c) 2023-2025 Dmytro Ostapenko. Alle Rechte vorbehalten.
> 
> Zitieren als: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> Wir stellen die Unterstützung der folgenden Android-Versionen bald ein: 9, 10, 11. Das hängt mit den aktuellen Änderungen an SDK und Sicherheit zusammen. Ältere Android-Versionen verwenden veraltete und instabile Features wie RenderScript.

## Inhaltsverzeichnis

- [Download](#download)
- [SpeakGPT Web](#speakgpt-web)
- [Überblick](#überblick)
- [Screenshots](#screenshots)
- [Informationen für Nutzerinnen und Nutzer, die Google Gemini-Modelle mit dieser App verwenden möchten](#informationen-für-nutzerinnen-und-nutzer-die-google-gemini-modelle-mit-dieser-app-verwenden-möchten)
- [Für alle, die etwas kostenlos mit wenig oder ohne Aufwand nutzen wollen](#für-alle-die-etwas-kostenlos-mit-wenig-oder-ohne-aufwand-nutzen-wollen)
- [Unterstützte API-Anbieter](#unterstützte-api-anbieter)
- [Basisfunktionen](#basisfunktionen)
- [Projektstruktur](#projektstruktur)
- [Voraussetzungen](#voraussetzungen)
- [Installation](#installation)
- [Nutzung](#nutzung)
- [Konfiguration](#konfiguration)
- [Beispiele](#beispiele)
- [Entwicklungshinweise](#entwicklungshinweise)
- [Fehlerbehebung](#fehlerbehebung)
- [Roadmap](#roadmap)
- [Sicherheit von API-Schlüsseln](#sicherheit-von-api-schlüsseln)
- [Entwickleridentität](#entwickleridentität)
- [Mitwirken](#mitwirken)
- [❤️ Support](#-support)
- [Lizenz](#lizenz)

## Download

📦 Installation über Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Starte SpeakGPT Web: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub-Repo: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Überblick

SpeakGPT ist ein Android-first Client für AI-APIs. Er ist auf Bring-your-own-endpoint und Bring-your-own-key ausgelegt, sodass Nutzerinnen und Nutzer den Anbieter, das Modell sowie das Kosten-/Leistungsprofil auswählen können.

### Auf einen Blick

| Bereich | Zusammenfassung |
|---|---|
| 💬 Kernfunktionen | Chat, Bildgenerierung, Bilderkennung, Spracheingabe, Assistent-Integrationen |
| 🔌 Anbieter-Strategie | OpenAI-kompatible Endpunkte mit konfigurierbaren Anbietern und eigenen Endpunkten |
| 🔐 Datenverarbeitung | API-Schlüssel werden lokal gespeichert; Chats können importiert und exportiert werden |
| 🧱 Tech-Stack | Android-Multi-Modulprojekt mit AGP `8.12.2`, Gradle `8.13`, Kotlin `2.2.10` |

Repository-Architektur:

- `app`: Android-Anwendungsmodul (`org.teslasoft.assistant`)
- `teslasoft-id`: internes Android-Bibliotheksmodul für Auth-/Client-Utilities (`org.teslasoft.core.auth`)
- JSON-Metadaten im Repository-Root (`ai_sets.json`, `explore.json`, `experiment.json`) für Modell-Sets, Discovery und Import-/Export-Workflows
- `i18n/`: Ausgabeordner für sprachspezifische README-Dateien

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

## Informationen für Nutzerinnen und Nutzer, die Google Gemini-Modelle mit dieser App verwenden möchten

SpeakGPT unterstützt keine Google-API-Keys direkt, aber du kannst Google Gemini trotzdem über die OpenRouter-API nutzen.

Mehr Infos: [OpenRouter Models](https://openrouter.ai/docs#models)

## Für alle, die etwas kostenlos mit wenig oder ohne Aufwand nutzen wollen

> [!WARNING]
> 
> Vergiss nicht: Kostenloser Käse ist oft nur eine Mausefalle. DIESE APP IST EIN OPEN-SOURCE-CLIENT UND WIRD "AS IS" GELIEFERT. SIE BIETET KEINEN VOLLSTÄNDIG KOSTENLOSEN ZUGRIFF AUF PREMIUM-FUNKTIONEN DER API-ANBIETER (WIE FLAGSHIP-AI-MODELLE UND SPEZIALFUNKTIONEN). WENN DU HIER BIST, UM DIE ARBEIT VON ANDEREN KOSTENLOS UND OHNE GEGENSEITIGE LEISTUNG ZU NUTZEN, SIND ALTERNATIVE OPTIONEN BESSER ALS DIESE APP. AUF FRAGEN WIE "INCORRECT API KEY, WHY THIS APP REDIRECTS ME TO THE EXTERNAL SITE FOR API KEY?" WERDE ICH NICHT REAGIEREN. VIELEN DANK FÜR DEIN VERSTÄNDNIS.
> Alle anderen sachkundigen Nutzerinnen und Nutzer sind willkommen.

## Unterstützte API-Anbieter

| Anbieter | Unterstützungsgrad | Hinweise |
|---|---|---|
| OpenAI | Vollständige Unterstützung | Primärer Integrationspfad |
| GROQ | Teilweise Unterstützung | Einige Funktionen können abweichen |
| Azure | Teilweise Unterstützung | Endpunkt-/Modellspezifika können variieren |
| OpenRouter | Nur Textgenerierung | Getestet mit Gemini, Claude, Perplexity, Llama, Gemma, Mistral und OpenAI-Modellen |
| Sonstige | Community-getestet | Feedback ist willkommen |

> [!NOTE]
> 
> Um deinen API-Anbieter zu ändern, gehe zu den Einstellungen und wähle den API-Endpunkt. Du kannst auch deinen eigenen API-Anbieter hinzufügen.

## Basisfunktionen

✅ Implementierte Funktionen:

- [x] Chat (lokal gespeichert, kann bei Bedarf importiert/exportiert werden)
- [x] Bildgenerierung
- [x] Bilderkennung (verwende deine Bilder und Fotos mit ChatGPT)
- [x] Aktivierungs-Prompt
- [x] Systemnachricht
- [x] Spracheingabe (Whisper und Google)
- [x] Assistant
- [x] SpeakGPT im Kontextmenü
- [x] SpeakGPT im Teilen-Blatt
- [x] Funktion-Calls
- [x] Prompt-Bibliothek
- [x] Unterschiedliche Chat-Layouts
- [x] Adaptives Design
- [x] Viele verschiedene Modelle
- [x] Kein Captcha
- [x] Pay-as-you-go-System
- [x] Tipps für Einsteigerinnen und Einsteiger
- [x] Benutzerdefinierte fine-tuned Modelle werden unterstützt
- [x] AMOLED-Dark-Mode
- [x] Unterstützung für benutzerdefinierte API-Anbieter
- [x] Modell-Parameter wie `temperature`, `topP`, `frequencyPenalty`, `presencePenalty` und `logit_bias` anpassen
- [x] Playground
- [x] Zugriff auf neueste Flagship-Modelle wie o1, o3, o4, gpt-4.1, gpt-4.5 und gpt-image-1 (für manche dieser Modelle kann eine Identitätsprüfung bei OpenAI nötig sein)

## Projektstruktur

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

## Voraussetzungen

- Android Studio (aktuelle stabile Version empfohlen)
- Android SDK mit `compileSdk 36`
- JDK 21 (Quell- und Zielkompatibilität des Projekts ist Java 21)
- Git
- Internetzugriff für Abhängigkeitsauflösung und APIs der Modellanbieter

Buildsystemdaten aus der Repository-Konfiguration:

| Komponente | Version / Wert |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin-Plugin | `2.2.10` |
| Gradle Wrapper | `8.13` |
| App-Paket-ID | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## Installation

### 1. Repository klonen

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Debug-APK bauen

```bash
./gradlew assembleDebug
```

### 3. Auf verbundenem Gerät oder Emulator installieren

```bash
./gradlew installDebug
```

### 4. Optionale Qualitätsprüfungen

```bash
./gradlew lint
```

## Nutzung

### Ablauf für Endnutzerinnen und Endnutzer (in der App)

1. Installiere die App über Google Play oder einen lokalen Debug-Build.
2. Schließe den Onboarding-Flow ab.
3. Öffne die API-Einstellungen und wähle oder füge deinen Endpunkt/Anbieter hinzu.
4. Gib den API-Schlüssel ein (wird lokal auf deinem Gerät gespeichert).
5. Wähle ein Modell und beginne Chat, Vision, Bildgenerierung oder Sprach-Workflows.

### Verfügbare Android-Integrationen

- Assistant-Integration (`ASSIST` intent)
- Share-Sheet-Integration (`SEND` und `SEND_MULTIPLE` intents)
- Process-Text-Integration (`PROCESS_TEXT`)
- Deep Links für `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Konfiguration

### API-Endpunkte und Anbieter

- Öffne **Settings** in der App.
- Wähle **API endpoint**, um zwischen vorgefertigten Anbietern zu wechseln.
- Füge einen benutzerdefinierten Endpunkt hinzu, wenn dein Anbieter OpenAI-kompatibel ist.

### Modell- und Generierungsparameter

SpeakGPT unterstützt das runtime-basierte Tuning für Generierungseinstellungen wie:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Lokale Daten und Sicherheit

- Konversationen werden lokal gespeichert und können importiert/exportiert werden.
- Sensible Werte wie API-Schlüssel werden in verschlüsselten Einstellungen verarbeitet.

### Hinweise und Annahmen

- `google-services.json` ist in diesem Repository vorhanden; wenn du einen Fork erstellst und sie entfernst, benötigen einige Integrationen möglicherweise eine eigene Konfiguration.
- Die Kompatibilität von Anbietern kann je nach Implementierung des Endpunkts und der Modellfamilie variieren.

## Beispiele

### Beispiel 1: Release-APK bauen

```bash
./gradlew assembleRelease
```

### Beispiel 2: Sauberer Neuaufbau

```bash
./gradlew clean assembleDebug
```

### Beispiel 3: OpenRouter für Modelle der Gemini-Familie nutzen

1. Erstelle einen OpenRouter-API-Schlüssel.
2. Wähle in den SpeakGPT-Einstellungen OpenRouter als Endpunkt aus oder füge ihn hinzu.
3. Wähle ein Gemini-fähiges OpenRouter-Modell.
4. Starte einen Chat und prüfe die Antwortgenerierung.

## Entwicklungshinweise

- Dies ist ein Android-Multi-Modulprojekt (`:app`, `:teslasoft-id`).
- Die Build-Typen `debug` und `release` verwenden aktuell beide `minifyEnabled true` und `shrinkResources true`.
- ProGuard-/R8-Regeln befinden sich in:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- Eingebettete Web-Dokumentation liegt in:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Lokalisierungsressourcen befinden sich in `app/src/main/res/values-*`.
- Das README-i18n-Ausgabeverzeichnis ist unter `i18n/` vorhanden (sprachspezifische README-Dateien werden getrennt in Pipeline-Schritten generiert).

## Fehlerbehebung

| Problem | Was du prüfen solltest |
|---|---|
| "Incorrect API key" oder Auth-Fehler | Prüfe, ob dein Schlüssel für den gewählten Anbieter gültig ist, ob das gewählte Modell für dein Konto verfügbar ist und ob für Flagship-Modelle zusätzliche Verifizierungen erforderlich sind. |
| Endpunkt-/Modell-Mismatch | Wenn du einen benutzerdefinierten Endpunkt nutzt, stelle sicher, dass Request/Response OpenAI-kompatibel sind. Wechsle testweise auf ein anderes Endpoint-Preset in den Einstellungen und prüfe erneut. |
| Build-Probleme | Stelle sicher, dass JDK 21 aktiv ist, synchronisiere das Gradle-Projekt in Android Studio, führe `./gradlew --version` aus und verifiziere, dass der Wrapper Gradle `8.13` nutzt, dann wiederhole `./gradlew clean build`. |
| Laufzeitprobleme auf älteren Android-Versionen | Das Projekt unterstützt aktuell `minSdk 28` (Android 9). Es wird gewarnt, dass die Unterstützung für Android 9/10/11 künftig wegen SDK-/Sicherheitsänderungen entfallen kann. |

## Roadmap

### ❌ Geplant (Teile deine Ideen in den Issues)

- [ ] Geräte-Routinen (z. B. Alarm einstellen oder App öffnen)
- [ ] Chat-Verlauf synchronisieren
- [ ] Ein Modell-Exchange-Portal wie einen Prompt-Store hinzufügen
- [ ] Offizielle Browsing-Funktionen (GPT-KI-Modelle mit Internetzugriff ausstatten)

## Sicherheit von API-Schlüsseln

SpeakGPT nutzt die OpenAI-API, um dir die beste Erfahrung zu bieten. Die Verwendung von API-Schlüsseln ist sicherer als die Verwendung von Benutzername und Passwort. Über einen API-Schlüssel können keine persönlichen Daten entnommen werden. OpenAI stellt günstigen API-Zugang zu seinen Diensten bereit. Dein API-Schlüssel wird lokal auf deinem Gerät gespeichert und nicht mit anderen geteilt. SpeakGPT sammelt keine personenbezogenen Daten. SpeakGPT ist Open Source und du kannst den Code selbst prüfen. Jede SpeakGPT-Version wird auf VirusTotal geprüft.
Falls du Bedenken hast, kannst du entweder deinen [API-Schlüssel widerrufen](https://platform.openai.com/account/api-keys) oder einen separaten API-Schlüssel für SpeakGPT verwenden.

So gehst du vor, um deinen API-Schlüssel zu sichern:

1. Stelle sicher, dass du einen separaten API-Schlüssel für SpeakGPT hast.
2. Richte ein Billing-Limit ein.
3. Aktiviere Nutzungsmonitoring, damit du sehen kannst, wie viele Ressourcen SpeakGPT verwendet und was es kostet.
4. Wenn du Bedenken hast, kannst du deinen API-Schlüssel widerrufen.

> Warum obfuskieren wir unseren Code in Produktions-Releases?
> 
> Obfuskation und Resource Shrinking helfen uns, App-Größe und Performance zu optimieren, die App vor Reverse Engineering oder Manipulation zu schützen und sicherzustellen, dass deine Zugangsdaten wie API-Schlüssel sicher aufbewahrt sind. Du kannst einen unverschleierten Build anfordern oder den Code selbst kompilieren, um sicherzugehen, dass unsere App sicher ist.

> [!CAUTION]
> 
> PASSE AUF MALWARE AUF! Du darfst SpeakGPT kompilieren und anpassen, aber sei vorsichtig, wenn dir jemand empfiehlt, einen fremden Build zu installieren. Ein solcher Build kann Malware enthalten. Offizielle Builds enthalten keine Malware und werden mit über 60 verschiedenen Antivirenprogrammen via VirusTotal geprüft. Den VirusTotal-Bericht findest du auf jeder Release-Seite und kannst den Binary-Hash vergleichen.

## Entwickleridentität

| Feld | Wert |
|---|---|
| Entwicklername | Dmytro Ostapenko (AndraxDev) |
| Kontakt | dostapenko82@gmail.com, +421951829517 |
| Rechtsstandort | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Rechtsträger-ID | 55545386 (D-U-N-S: 933739642) |
| Gewerbliche Lizenz | OU-KE-OZP1-2023/031005-2 (Ausgestellt am 14. Juni 2023 gemäß § 10 Absatz 1 Buchstabe a) des Gesetzes Nr. 455/1991 Coll. on Trade Licensing (Gewerbegesetz) in der jeweils gültigen Fassung) |
| USt-Identifikationsnummer | SK3121636045 |

(So weißt du, wohin dein Geld fließt, falls du das Projekt finanziell unterstützen willst oder wenn das Projekt zukünftig kostenpflichtige Funktionen bekommt.)

## Mitwirken

Beiträge sind willkommen.

- Melde Bugs in Issues mit Reproduktionsschritten.
- Bitte um neue Funktionen (verwendet bitte klare Issue-Tags/-Labels).
- Wenn du Code einreichst, halte Änderungen fokussiert und füge eine Begründung hinzu.

## ❤️ Support

| Donate | PayPal | Stripe |
|---|---|---|
| [![Donate](https://img.shields.io/badge/Donate-LazyingArt-0EA5E9?style=for-the-badge&logo=ko-fi&logoColor=white)](https://chat.lazying.art/donate) | [![PayPal](https://img.shields.io/badge/PayPal-RongzhouChen-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/RongzhouChen) | [![Stripe](https://img.shields.io/badge/Stripe-Donate-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

### Deine Unterstützung wird geschätzt

- Melde Bugs
- Unterstütze mich :)
- Bitte um neue Funktionen. Bitte nicht vergessen, das Issue mit einem Tag zu versehen.

### Buy me a coffee

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## Lizenz

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
