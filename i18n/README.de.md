[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Android-first, Open-Source-KI-Assistent mit Chat-, Sprach-, Vision- und Bildgenerierungs-Workflows.

[![Plattform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#schnellfakten)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#voraussetzungen)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#voraussetzungen)
[![Lizenz](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#lizenz)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#voraussetzungen)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#voraussetzungen)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#voraussetzungen)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)
[![Übersetzungen](https://img.shields.io/badge/Translations-11-2563EB?style=flat-square&logo=googletranslate&logoColor=white)](#inhaltsverzeichnis)
[![Beiträge willkommen](https://img.shields.io/badge/Contributions-Welcome-10B981?style=flat-square&logo=github&logoColor=white)](#mitwirken)
[![Support](https://img.shields.io/badge/Support-Open%20in%202%20clicks-EC4899?style=flat-square&logo=ko-fi&logoColor=white)](#-support)

| ✅ Was | 🔗 Link |
|---|---|
| Android-App installieren | [Google Play](https://play.google.com/store/apps/details?id=org.teslasoft.assistant) |
| Web Companion nutzen | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |
| Issues durchsuchen | [GitHub Issues](https://github.com/AndraxDev/speak-gpt/issues) |
| Übersetzungen lesen | [i18n/](i18n/) |

---

SpeakGPT ist ein fortschrittlicher und intuitiver Open-Source-KI-Assistent für Android. Er vereint mehrere multimodale KI-Workflows (Chat, Sprache, Bildgenerierung und Vision) in einer einzigen App mit OpenAI-kompatiblen Anbietern.

Offiziell werden GPT-Modelle, LLAMA, MIXTRAL, GEMMA, Gemini (Standard und Pro) Vision, DALL-E und weitere Familien unterstützt.

## Schnellfakten

| Kurzinfo | Details |
|---|---|
| 📱 Plattform | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Hauptnutzung | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 App-Typ | Open-Source-KI-Client (keine API-Anbieterseite) |
| 🌐 Web Companion | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> Dieses Projekt ist Teil meiner Bachelorarbeit. Die Namensnennung ist erforderlich, wenn diese Arbeit verwendet wird. Copyright (c) 2023-2025 Dmytro Ostapenko. Alle Rechte vorbehalten.
> 
> Zitierweise: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> Android-Versionen 9, 10 und 11 sollen aufgrund von SDK-/Sicherheitsänderungen abgekündigt werden. Ältere Android-Versionen basieren auf veralteten APIs wie RenderScript.

## Inhaltsverzeichnis

- [Download](#download)
- [SpeakGPT Web](#speakgpt-web)
- [Überblick](#überblick)
- [Screenshots](#screenshots)
- [Informationen für Nutzer, die Google Gemini mit dieser App verwenden möchten](#informationen-für-nutzer-die-google-gemini-mit-dieser-app-verwenden-möchten)
- [Für Nutzer mit wenig Aufwand kostenlos starten](#für-nutzer-mit-wenig-aufwand-kostenlos-starten)
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
- [API-Schlüssel-Sicherheit](#api-schlüssel-sicherheit)
- [Entwickleridentität](#entwickleridentität)
- [Mitwirken](#mitwirken)
- [❤️ Support](#-support)
- [Lizenz](#lizenz)

## Download

📦 Installation über Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 SpeakGPT Web starten: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub-Repo: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Überblick

SpeakGPT ist auf einen flexiblen Provider-Workflow ausgelegt, damit Nutzer die Kontrolle über ihre API-Landschaft behalten.

### Auf einen Blick

| Bereich | Zusammenfassung |
|---|---|
| 💬 Kernfunktionen | Chat, Bildgenerierung, Bilderkennung, Spracheingabe, Assistent-Integrationen |
| 🔌 Provider-Strategie | OpenAI-kompatible Endpunkte mit konfigurierbaren Providern und benutzerdefinierten Endpunkten |
| 🔐 Datenverarbeitung | API-Schlüssel werden lokal gespeichert; Unterhaltungen können importiert/exportiert werden |
| 🧱 Build-Stack | Android-Multi-Modulprojekt mit AGP `8.12.2`, Gradle `8.13`, Kotlin `2.2.10` |

Repository-Architektur:

- `app`: Android-App-Modul (`org.teslasoft.assistant`)
- `teslasoft-id`: internes Android-Bibliotheksmodul für Authentifizierungs-/Client-Utilities (`org.teslasoft.core.auth`)
- JSON-Metadaten im Repository-Root (`ai_sets.json`, `explore.json`, `experiment.json`) für Modellsets, Entdeckung und Workflow-Metadaten
- `i18n/`: Dokumentationsordner für mehrere Sprachen

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

## Informationen für Nutzer, die Google Gemini mit dieser App verwenden möchten

SpeakGPT unterstützt Google-API-Schlüssel nicht direkt, aber Gemini kann über OpenRouter genutzt werden.

Weitere Infos: [OpenRouter Models](https://openrouter.ai/docs#models)

## Für Nutzer mit wenig Aufwand kostenlos starten

> [!WARNING]
> 
> Kostenlose Funktionen haben oft Einschränkungen. Diese App ist Open Source und wird „as-is“ bereitgestellt. Sie bietet keinen kostenlosen Vollzugriff auf Premium-Features externer API-Anbieter.
> 
> Wenn Sie vollen Premium-Zugriff ohne Aufwand erwarten, ist es sinnvoller, ein anderes Produkt zu nutzen. Fragen wie „Incorrect API key“ sind in der Regel durch die Prüfung von Endpoint- und Modellkonfiguration lösbar. Vielen Dank für Ihr Verständnis.
> 
> Alle anderen legitimen Nutzer sind willkommen.

## Unterstützte API-Anbieter

| Anbieter | Unterstützungsgrad | Anmerkungen |
|---|---|---|
| OpenAI | Vollständig | Primärer Integrationspfad |
| GROQ | Teilweise | Einige Funktionen können variieren |
| Azure | Teilweise | Endpoint-/Modelldetails können abweichen |
| OpenRouter | Nur Textgenerierung | Getestet mit Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI-Modellen |
| Sonstiges | Community-getestet | Feedback ist willkommen |

> [!NOTE]
> 
> Um den Anbieter zu wechseln, öffnen Sie die App-Einstellungen und wählen den API-Endpunkt. Sie können auch einen eigenen OpenAI-kompatiblen Endpunkt hinzufügen.

## Basisfunktionen

✅ Implementierte Funktionen:

- [x] Chat (lokal gespeichert, Import/Export unterstützt)
- [x] Bildgenerierung
- [x] Bilderkennung (Bilder/Fotos im Chat anhängen)
- [x] Aktivierungs-Prompt und Systemnachrichten-Workflows
- [x] Spracheingabe (Whisper und Google)
- [x] Assistenten-Integration
- [x] SpeakGPT im Kontextmenü
- [x] SpeakGPT im Freigabeblatt
- [x] Function Calling
- [x] Prompt-Bibliothek
- [x] Mehrere Chat-Layouts
- [x] Adaptives Design
- [x] Breite Modellabdeckung
- [x] Kein Captcha
- [x] Pay-as-you-go-Nutzung
- [x] Tipps für Neueinsteiger und Onboarding
- [x] Fine-tuned/custom Modellunterstützung
- [x] AMOLED Dark Mode
- [x] Eigene API-Anbieter-Unterstützung
- [x] Anpassung von Modellparametern (`temperature`, `topP`, `frequencyPenalty`, `presencePenalty`, `logit_bias`)
- [x] Playground
- [x] Zugriff auf neueste Flagship-Familien wie o1, o3, o4, gpt-4.1, gpt-4.5, gpt-image-1

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

- Android Studio (empfohlenerweise die aktuelle stabile Version)
- Android SDK mit `compileSdk 36`
- JDK 21 (`sourceCompatibility`/`targetCompatibility` auf Java 21 in der Projektkonfiguration ausgerichtet)
- Git
- Internetzugang für Gradle-Abhängigkeiten und Provider-APIs

Buildsystem-Fakten aus der Repo-Konfiguration:

| Komponente | Version / Wert |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin Plugin | `2.2.10` |
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

### 2. In Android Studio öffnen

- Öffnen Sie `build.gradle` in Android Studio.
- Warten Sie bis Gradle-Sync abgeschlossen ist.

### 3. Debug-APK erstellen

```bash
./gradlew assembleDebug
```

### 4. Auf verbundenem Gerät/Emulator installieren

```bash
./gradlew installDebug
```

### 5. Optionale Qualitätsprüfung

```bash
./gradlew lint
```

## Nutzung

### Endnutzerablauf (in der App)

1. App von Google Play oder lokalem Debug-Build installieren.
2. Onboarding abschließen.
3. API-Einstellungen öffnen und einen Anbieter/Endpoint auswählen.
4. Gültigen API-Schlüssel hinzufügen (wird lokal auf dem Gerät gespeichert).
5. Modell wählen und Chat-, Vision-, Bildgenerierungs- oder Sprach-Workflows starten.

### Verfügbare Android-Integrationen

- Assistenten-Integration (`ASSIST`-Intent)
- Freigabenamensblatt-Integration (`SEND`, `SEND_MULTIPLE` Intents)
- Textverarbeitungs-Integration (`PROCESS_TEXT`)
- Deep Links für `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Konfiguration

### API-Endpunkte und Anbieter

- Öffnen Sie **Einstellungen** in der App.
- Wählen Sie **API endpoint**, um zwischen eingebauten Providern zu wechseln.
- Fügen Sie einen benutzerdefinierten Endpoint hinzu, wenn Ihr Anbieter OpenAI-kompatibel ist.

### Modell- und Generierungsparameter

SpeakGPT unterstützt Runtime-Tuning für:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Lokale Daten und Sicherheit

- Unterhaltungen werden lokal gespeichert und können importiert/exportiert werden.
- Sensible Werte wie API-Schlüssel werden über verschlüsselte Präferenzen verwaltet.

### Hinweise und Annahmen

- `google-services.json` ist in diesem Repository für aktuelle Builds vorhanden; bei Forks, in denen die Datei entfernt wurde, könnten einige Integrationen eine gleichwertige Firebase-/App-Services-Konfiguration erfordern.
- Das Verhalten von Providern kann je nach Endpoint und Modellfamilie variieren.

## Beispiele

### Release-APK erstellen

```bash
./gradlew assembleRelease
```

### Sauberer Neuaufbau

```bash
./gradlew clean assembleDebug
```

### OpenRouter für Gemini-Modelle nutzen

1. OpenRouter-API-Schlüssel erstellen.
2. In den SpeakGPT-Einstellungen den OpenRouter-Endpoint auswählen/hinzufügen.
3. Ein Gemini-kompatibles Modell wählen.
4. Chat starten und Antworten prüfen.

### Vollständigen Clean-Build ausführen

```bash
./gradlew clean build
```

## Entwicklungshinweise

- Dies ist ein Multi-Module-Android-Projekt (`:app`, `:teslasoft-id`).
- Sowohl `debug` als auch `release` verwenden aktuell `minifyEnabled true` und `shrinkResources true`.
- ProGuard/R8-Regeln befinden sich in:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- Eingebettete Web-Dokumentation ist hier abgelegt:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Lokalisierte String-Ressourcen befinden sich in `app/src/main/res/values-*`.
- README-Übersetzungen sind in `i18n/` für Sprachvarianten abgelegt.

## Fehlerbehebung

| Problem | Was zu prüfen ist |
|---|---|
| Falscher API-Schlüssel / Auth-Fehler | Schlüsselgültigkeit, Provider-Kompatibilität und Modellverfügbarkeit prüfen. Einige Flagship-Modelle benötigen zusätzliche Kontoverifikation. |
| Endpoint- oder Modell-Mismatch | Prüfen Sie, ob Ihr benutzerdefinierter Endpoint OpenAI-kompatible Request-/Response-Formate nutzt. Versuchen Sie, das Endpoint-Preset in den Einstellungen zu ändern und erneut zu testen. |
| Build-Fehler | Sicherstellen, dass JDK 21 aktiv ist, Gradle zu synchronisieren und den Gradle-Wrapper auf `8.13` zu prüfen (mit `./gradlew --version`), dann `./gradlew clean build` ausführen. |
| Laufzeitprobleme auf älteren Android-Geräten | Das Projekt nutzt `minSdk 28`. Deprecation-Warnungen für Android 9/10/11 sind normal, da sich die Support-Politik weiterentwickelt. |

## Roadmap

### ❌ Geplante Ergänzungen

- [ ] Geräte-Routinen (Wecker stellen oder App öffnen)
- [ ] Chat-Verlauf synchronisieren
- [ ] Prompt-Austausch-Portal / Marketplace-ähnlicher Ablauf
- [ ] Offizielles Browsing/Tools für internetgestützte Workflows

## API-Key-Sicherheit

SpeakGPT nutzt API-Schlüssel für Provider-Anfragen, wodurch die Zugangsdaten besser abgegrenzt und sicherer sind als Konto-/Passwort-Flows.

- Ihr API-Schlüssel wird lokal gespeichert und nicht von der App geteilt.
- Sie können Schlüssel jederzeit in der Provider-Konsole widerrufen.
- Wenn gewünscht, verwenden Sie einen Schlüssel, der nur für SpeakGPT bestimmt ist.

Sicherheits-Hinweise:

1. Einen separaten API-Schlüssel für SpeakGPT nutzen.
2. Abrechnungsgrenzen festlegen.
3. Nutzungsüberwachung aktivieren, um Kosten im Griff zu behalten.
4. Schlüssel widerrufen, sobald verdächtige Nutzung auffällt.

Warum App-Releases obfuskiert sind:

Obfuskation und Ressourcen-Shrinking verbessern Paketgröße, Leistung und reduzieren das Reverse-Engineering-Risiko im Umgang mit Zugangsdaten. Sie können ein nicht obfuskiertes Build anfordern oder selbst kompilieren.

> [!CAUTION]
> 
> Installieren Sie keine Builds aus nicht vertrauenswürdigen Quellen. Drittanbieter-Builds können manipuliert sein und Schadsoftware enthalten. Offizielle Builds werden bei VirusTotal geprüft und über offizielle Kanäle veröffentlicht.

## Entwickleridentität

| Feld | Wert |
|---|---|
| Entwicklername | Dmytro Ostapenko (AndraxDev) |
| Kontakt | dostapenko82@gmail.com, +421951829517 |
| Rechtsadresse | Južná trieda 4B, 04001 Košice, Slovakia |
| Rechtsform-ID | 55545386 (D-U-N-S: 933739642) |
| Handelslizenz | OU-KE-OZP1-2023/031005-2 (ausgestellt am 14. Juni 2023 gemäß § 10(1)(a) des Gesetzes Nr. 455/1991 über Gewerbelizenzen, in der geänderten Fassung) |
| USt-IdNr. | SK3121636045 |

(Somit können Sie sehen, wohin Ihr Beitrag geht, falls Sie das Projekt finanziell unterstützen oder künftig kostenpflichtige Funktionen erscheinen.)

## Mitwirken

Beiträge sind willkommen.

- Fehler in den Issues mit Reproduktionsschritten melden.
- Neue Funktionen mit klarem Titel und Kontext vorschlagen.
- PRs fokussiert halten und eine Begründung mit Test-Hinweisen beifügen.

## Lizenz

Dieses Projekt ist unter der Apache License 2.0 lizenziert. Siehe [LICENSE.md](LICENSE.md).

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
