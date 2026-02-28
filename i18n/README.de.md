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

SpeakGPT ist ein fortschrittlicher und sehr intuitiver Open-Source-AI-Assistent für Android. Er integriert moderne Anbieter großer Sprachmodelle (LLMs) und multimodale Workflows (Chat, Sprache, Bildgenerierung, Vision) in einer einzigen mobilen App.

Offiziell werden GPT-Modelle, LLAMA, MIXTRAL, GEMMA, Gemini (regular und pro) Vision, DALL-E und weitere Modelle unterstützt.

| Kurzdaten | Details |
|---|---|
| 📱 Plattform | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Kernnutzung | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 App-Typ | Open-Source-AI-Client (kein API-Anbieter) |
| 🌐 Web-Begleiter | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> Dieses Projekt ist Teil meiner Bachelorarbeit. Für die Nutzung dieser Arbeit ist eine Quellenangabe erforderlich. Copyright (c) 2023-2025 Dmytro Ostapenko. Alle Rechte vorbehalten.
>
> Zitieren als: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> Wir stellen die Unterstützung der folgenden Android-Versionen bald ein: 9, 10, 11. Das hängt mit aktuellen Änderungen bei SDK und Sicherheit zusammen. Ältere Android-Versionen verwenden veraltete und instabile Funktionen wie RenderScript.

## Inhaltsverzeichnis

- [Download](#download)
- [SpeakGPT Web](#speakgpt-web)
- [Überblick](#überblick)
- [Screenshots](#screenshots)
- [Informationen für Nutzer, die Google-Gemini-Modelle mit dieser App verwenden möchten](#informationen-für-nutzer-die-google-gemini-modelle-mit-dieser-app-verwenden-möchten)
- [Für alle, die etwas kostenlos mit wenig oder ohne Aufwand nutzen wollen](#für-alle-die-etwas-kostenlos-mit-wenig-oder-ohne-aufwand-nutzen-wollen)
- [Unterstützte API-Anbieter](#unterstützte-api-anbieter)
- [Grundfunktionen](#grundfunktionen)
- [Projektstruktur](#projektstruktur)
- [Voraussetzungen](#voraussetzungen)
- [Installation](#installation)
- [Nutzung](#nutzung)
- [Konfiguration](#konfiguration)
- [Beispiele](#beispiele)
- [Hinweise zur Entwicklung](#hinweise-zur-entwicklung)
- [Fehlerbehebung](#fehlerbehebung)
- [Roadmap](#roadmap)
- [API-Key-Sicherheit](#api-key-sicherheit)
- [Entwickleridentität](#entwickleridentität)
- [Mitwirken](#mitwirken)
- [Support](#support)
- [Buy me a coffee](#buy-me-a-coffee)
- [Lizenz](#lizenz)

## Download

📦 Installation über Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Starte SpeakGPT Web: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

GitHub-Repo: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Überblick

SpeakGPT ist ein Android-first-Client für AI-APIs. Er ist auf Bring-your-own-endpoint und Bring-your-own-key ausgelegt, sodass Nutzer Anbieter, Modell sowie Kosten-/Leistungsprofil frei wählen können.

Repository-Architektur:

- `app`: Android-Anwendungsmodul (`org.teslasoft.assistant`)
- `teslasoft-id`: internes Android-Bibliotheksmodul für Auth-/Client-Utilities (`org.teslasoft.core.auth`)
- JSON-Metadaten im Repository-Root (`ai_sets.json`, `explore.json`, `experiment.json`) für Model-Sets, Discovery und Import-/Export-Workflows
- `i18n/`: Ausgabeverzeichnis für mehrsprachige README-Dateien (im Repository vorhanden)

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

## Informationen für Nutzer, die Google-Gemini-Modelle mit dieser App verwenden möchten

SpeakGPT unterstützt selbst keine Google-API-Keys, aber du kannst Google Gemini trotzdem über die OpenRouter API nutzen.

Mehr Infos: [OpenRouter Models](https://openrouter.ai/docs#models)

## Für alle, die etwas kostenlos mit wenig oder ohne Aufwand nutzen wollen

> [!WARNING]
>
> Denk daran: Kostenlosen Käse gibt es nur in der Mausefalle. DIESE APP IST EIN OPEN-SOURCE-CLIENT UND WIRD "AS IS" BEREITGESTELLT. SIE BIETET SELBST KEINEN VOLLSTÄNDIG KOSTENLOSEN ZUGANG ZU PREMIUM-FUNKTIONEN VON API-ANBIETERN (WIE FLAGSHIP-AI-MODELLE UND SPEZIALFUNKTIONEN). WENN DU HIER BIST, UM DIE ARBEIT ANDERER KOSTENLOS UND OHNE GEGENLEISTUNG ZU NUTZEN, DANN ÜBERSPRINGE DIESE APP BITTE UND SUCH DIR ETWAS ANDERES. ICH WERDE NICHT AUF FRAGEN WIE "INCORRECT API KEY, WHY THIS APP REDIRECTS ME TO THE EXTERNAL SITE FOR API KEY?" ANTWORTEN. DANKE FÜR DEIN VERSTÄNDNIS.
> Alle anderen vernünftigen Menschen sind willkommen.

## Unterstützte API-Anbieter

| Anbieter | Support-Level | Hinweise |
|---|---|---|
| OpenAI | Volle Unterstützung | Primärer Integrationspfad |
| GROQ | Teilweise Unterstützung | Einige Funktionen können variieren |
| Azure | Teilweise Unterstützung | Endpoint-/Modell-Details können abweichen |
| OpenRouter | Nur Textgenerierung | Getestet mit Gemini-, Claude-, Perplexity-, Llama-, Gemma-, Mistral- und OpenAI-Modellen |
| Andere | Von der Community getestet | Feedback ist willkommen |

> [!NOTE]
>
> Um deinen API-Anbieter zu ändern, gehe zu den Einstellungen und wähle den API-Endpunkt. Du kannst auch deinen eigenen API-Anbieter hinzufügen.

## Grundfunktionen

✅ Implementierte Funktionen:

- [x] Chat (lokal gespeichert, kann bei Bedarf importiert/exportiert werden)
- [x] Bildgenerierung
- [x] Bilderkennung (verwende deine Bilder und Fotos mit ChatGPT)
- [x] Activation prompt
- [x] Systemnachricht
- [x] Spracheingabe (Whisper und Google)
- [x] Assistant
- [x] SpeakGPT im Kontextmenü
- [x] SpeakGPT im Share Sheet
- [x] Function-calling-Funktionen
- [x] Prompts-Bibliothek
- [x] Unterschiedliche Chat-Layouts
- [x] Adaptives Design
- [x] Viele verschiedene Modelle
- [x] Kein Captcha
- [x] Pay-as-you-go-System
- [x] Tipps für Einsteiger
- [x] Benutzerdefinierte fine-tuned Modelle werden unterstützt
- [x] AMOLED-Dark-Mode
- [x] Unterstützung für benutzerdefinierte API-Anbieter
- [x] Modellparameter wie `temperature`, `topP`, `frequencyPenalty`, `presencePenalty` und `logit_bias` anpassen
- [x] Playground
- [x] Zugriff auf die neuesten Flagship-Modelle wie o1, o3, o4, gpt-4.1, gpt-4.5 und gpt-image-1 (für einige dieser Modelle kann eine Identitätsprüfung bei OpenAI erforderlich sein)

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
- JDK 21 (Projekt-Source-/Target-Kompatibilität ist Java 21)
- Git
- Internetzugang für Abhängigkeitsauflösung und Modellanbieter-APIs

Build-System-Fakten aus der Repository-Konfiguration:

| Komponente | Version / Wert |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin-Plugin | `2.2.10` |
| Gradle Wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
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

### 3. Auf verbundenem Gerät/Emulator installieren

```bash
./gradlew installDebug
```

### 4. Optionale Qualitätsprüfungen

```bash
./gradlew lint
```

## Nutzung

### Endnutzer-Ablauf (in der App)

1. Installiere die App über Google Play oder einen lokalen Debug-Build.
2. Schließe das Onboarding ab.
3. Öffne die API-Einstellungen und wähle oder ergänze deinen Endpoint/Anbieter.
4. Gib den API-Key ein (lokal auf deinem Gerät gespeichert).
5. Wähle ein Modell und starte Chat-, Vision-, Bildgenerierungs- oder Sprach-Workflows.

### Verfügbare Android-Integrationen

- Assistant-Integration (`ASSIST` intent)
- Share-Sheet-Integration (`SEND` und `SEND_MULTIPLE` intents)
- Process-Text-Integration (`PROCESS_TEXT`)
- Deep Links für `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Konfiguration

### API-Endpunkte und Anbieter

- Öffne **Settings** in der App.
- Wähle **API endpoint**, um zwischen vorkonfigurierten Anbietern zu wechseln.
- Füge einen benutzerdefinierten Endpoint hinzu, wenn dein Anbieter OpenAI-kompatibel ist.

### Modell- und Generierungsparameter

SpeakGPT unterstützt Runtime-Tuning für Generierungseinstellungen wie:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Lokale Daten und Sicherheit

- Konversationen werden lokal gespeichert und können importiert/exportiert werden.
- Sensible Werte wie API-Keys werden in verschlüsselten Einstellungen verarbeitet.

### Hinweise und Annahmen

- `google-services.json` ist in diesem Repository vorhanden; wenn du einen Fork erstellst und die Datei entfernst, können einige Integrationen eine eigene Konfiguration benötigen.
- Die Anbieter-Kompatibilität kann je nach Endpoint-Implementierung und Modellfamilie variieren.

## Beispiele

### Beispiel 1: Release-APK bauen

```bash
./gradlew assembleRelease
```

### Beispiel 2: Neuaufbau nach Clean

```bash
./gradlew clean assembleDebug
```

### Beispiel 3: OpenRouter für Modelle der Gemini-Familie nutzen

1. Erstelle einen OpenRouter API key.
2. Wähle/ergänze in den SpeakGPT-Einstellungen den OpenRouter-Endpoint.
3. Wähle ein Gemini-fähiges OpenRouter-Modell.
4. Starte einen Chat und prüfe die Antwortgenerierung.

## Hinweise zur Entwicklung

- Dies ist ein Android-Multi-Module-Projekt (`:app`, `:teslasoft-id`).
- `debug`- und `release`-Build-Typen haben in der aktuellen Konfiguration beide `minifyEnabled true` und `shrinkResources true`.
- ProGuard-/R8-Regeln befinden sich in:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- Eingebettete Web-Dokumente liegen in:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Lokalisierungsressourcen befinden sich in `app/src/main/res/values-*`.
- Das README-i18n-Ausgabeverzeichnis existiert unter `i18n/` (sprachspezifische README-Dateien werden in separaten Pipeline-Schritten erzeugt).

## Fehlerbehebung

| Problem | Was prüfen |
|---|---|
| "Incorrect API key" oder Auth-Fehler | Prüfe, ob dein Key für den ausgewählten Anbieter gültig ist, ob das gewählte Modell für dein Konto verfügbar ist und ob der Anbieter für Flagship-Modelle zusätzliche Verifizierung verlangt. |
| Endpoint-/Modell-Mismatch | Wenn du einen benutzerdefinierten Endpoint nutzt, stelle ein OpenAI-kompatibles Request-/Response-Format sicher. Wechsle testweise das Endpoint-Preset in den Einstellungen und teste erneut. |
| Build-Probleme | Prüfe, ob JDK 21 aktiv ist, synchronisiere das Gradle-Projekt in Android Studio, führe `./gradlew --version` aus und verifiziere, dass der Wrapper Gradle `8.13` verwendet, dann versuche erneut `./gradlew clean build`. |
| Laufzeitprobleme auf alten Android-Versionen | Das Projekt unterstützt aktuell `minSdk 28` (Android 9). Das Projekt weist darauf hin, dass die Unterstützung für Android 9/10/11 künftig aufgrund von SDK-/Sicherheitsänderungen entfallen kann. |

## Roadmap

### ❌ Geplant (Teile deine Ideen in den Issues)

- [ ] Geräte-Routinen (z. B. Wecker stellen oder App öffnen)
- [ ] Chat-Verlauf synchronisieren
- [ ] Modell-Exchange-Portal wie einen Prompt-Store hinzufügen
- [ ] Offizielle Browsing-Fähigkeiten (GPT-AI-Modelle auf das Internet zugreifen lassen)

## API-Key-Sicherheit

SpeakGPT nutzt die OpenAI API, um dir die bestmögliche Erfahrung zu bieten. Die Nutzung von API-Keys ist sicherer als die Nutzung von Benutzername/Passwort. Deine persönlichen Informationen können über einen API-Key nicht abgerufen werden. OpenAI bietet günstigen API-Zugang zu seinen Diensten. Dein API-Key wird lokal auf deinem Gerät gespeichert und mit niemandem geteilt. SpeakGPT sammelt keine personenbezogenen Daten. SpeakGPT ist Open Source und du kannst den Code selbst prüfen. Jede Release-Version von SpeakGPT wird auf VirusTotal geprüft.
Wenn du Bedenken hast, kannst du entweder [deinen API key widerrufen](https://platform.openai.com/account/api-keys) oder einen separaten API key für SpeakGPT verwenden.

Um deinen API-Key abzusichern, führe die folgenden Schritte aus:

1. Stelle sicher, dass du einen separaten API key für SpeakGPT hast.
2. Richte ein Billing-Limit ein.
3. Aktiviere Usage-Monitoring, damit du siehst, wie viele Ressourcen SpeakGPT nutzt und was es kostet.
4. Wenn du Bedenken hast, kannst du deinen API key widerrufen.

> Warum verschleiern wir unseren Code in Produktions-Releases?
>
> Obfuskation und Resource Shrinking helfen uns, die App-Größe und Performance zu optimieren, sie gegen Reverse Engineering oder Manipulation abzusichern und sicherzustellen, dass deine Zugangsdaten wie API-Keys geschützt sind. Du kannst einen nicht obfuskierten Build anfordern oder selbst kompilieren, um sicherzugehen, dass unsere App sicher ist.

> [!CAUTION]
>
> ACHTUNG VOR MALWARE! Du darfst SpeakGPT kompilieren und verändern, aber sei sehr vorsichtig, wenn dir jemand die Installation eines fremden Builds anbietet. Solche Builds können Malware enthalten. Offizielle Builds enthalten keine Malware und werden mit mehr als 60 verschiedenen Antiviren-Programmen über VirusTotal geprüft. Du findest den VirusTotal-Bericht auf jeder Release-Seite und kannst den Hash der Binärdateien vergleichen.

## Entwickleridentität

| Feld | Wert |
|---|---|
| Entwicklername | Dmytro Ostapenko (AndraxDev) |
| Kontakt | dostapenko82@gmail.com, +421951829517 |
| Rechtliche Adresse | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Rechtsträger-ID | 55545386 (D-U-N-S: 933739642) |
| Gewerbelizenz | OU-KE-OZP1-2023/031005-2 (Ausgestellt am 14 June 2023 gemäß § 10 Abschnitt 1 Buchstabe a) des Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) in der jeweils geltenden Fassung) |
| USt-IdNr. | SK3121636045 |

(Damit du weißt, an wen du dein Geld sendest, falls du das Projekt finanziell unterstützen willst oder das Projekt künftig kostenpflichtige Funktionen haben sollte)

## Mitwirken

Beiträge sind willkommen.

- Melde Bugs in den Issues mit Reproduktionsschritten.
- Schlage neue Funktionen vor (bitte klare Issue-Tags/Labels verwenden).
- Wenn du Code einreichst, halte Änderungen klar abgegrenzt und füge eine Begründung hinzu.

## Support

### Das wird geschätzt

- Melde Bugs
- Unterstütze mich :)
- Schlage neue Funktionen vor. Vergiss nicht, das Issue mit einem Tag zu markieren

## Buy me a coffee

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

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
