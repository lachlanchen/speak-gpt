[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Asistente de IA de código abierto, centrado en Android, con flujos de chat, voz, visión y generación de imágenes.

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

| ✅ Qué | 🔗 Enlace |
|---|---|
| Instalar app Android | [Google Play](https://play.google.com/store/apps/details?id=org.teslasoft.assistant) |
| Usar web companion | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |
| Explorar incidencias | [GitHub Issues](https://github.com/AndraxDev/speak-gpt/issues) |
| Ver traducciones | [i18n/](i18n/) |

---

SpeakGPT es un asistente de IA avanzado e intuitivo de código abierto para Android. Unifica varias experiencias de IA multimodal (chat, voz, generación de imágenes y visión) en una sola app con proveedores compatibles con OpenAI.

De forma oficial admite modelos GPT, LLAMA, MIXTRAL, GEMMA, Gemini (Vision normal y pro), DALL-E y otras familias.

## Hechos rápidos

| Dato rápido | Detalles |
|---|---|
| 📱 Plataforma | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Uso principal | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 Tipo de app | Cliente de IA de código abierto (no proveedor de API) |
| 🌐 Web companion | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> Este proyecto forma parte de mi Tesis de Licenciatura. Se requiere atribución para usar este trabajo. Copyright (c) 2023-2025 Dmytro Ostapenko. Todos los derechos reservados.
> 
> Citar como: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> Se prevé retirar soporte de Android 9, 10 y 11 debido a cambios de SDK/seguridad. Las versiones antiguas de Android dependen de APIs obsoletas como RenderScript.

## Tabla de contenidos

- [Descarga](#descarga)
- [SpeakGPT Web](#speakgpt-web)
- [Resumen](#resumen)
- [Capturas de pantalla](#capturas-de-pantalla)
- [Información para quienes quieran usar modelos Google Gemini con esta app](#información-para-quienes-quieran-usar-modelos-google-gemini-con-esta-app)
- [Para quienes quieran algo gratuito con poco o ningún esfuerzo](#para-quienes-quieran-algo-gratuito-con-poco-o-ningún-esfuerzo)
- [Proveedores de API compatibles](#proveedores-de-api-compatibles)
- [Características básicas](#características-básicas)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Requisitos previos](#requisitos-previos)
- [Instalación](#instalación)
- [Uso](#uso)
- [Configuración](#configuración)
- [Ejemplos](#ejemplos)
- [Notas de desarrollo](#notas-de-desarrollo)
- [Solución de problemas](#solución-de-problemas)
- [Hoja de ruta](#hoja-de-ruta)
- [Seguridad de clave API](#seguridad-de-clave-api)
- [Identidad del desarrollador](#identidad-del-desarrollador)
- [Contribuir](#contribuir)
- [❤️ Support](#-support)
- [Licencia](#licencia)

## Descarga

📦 Instálala desde Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Abre SpeakGPT Web: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

Repositorio de GitHub: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Resumen

SpeakGPT está diseñado alrededor de un flujo de proveedores flexible para usuarios que quieren control directo sobre su stack de API.

### A grandes rasgos

| Área | Resumen |
|---|---|
| 💬 Experiencias principales | Chat, generación de imágenes, reconocimiento de imágenes, entrada de voz, integraciones con asistentes |
| 🔌 Estrategia de proveedor | Endpoints compatibles con OpenAI con proveedores configurables y endpoints personalizados |
| 🔐 Gestión de datos | Las claves API se guardan localmente; las conversaciones pueden importarse/exportarse |
| 🧱 Stack de compilación | Proyecto Android multi-módulo con AGP `8.12.2`, Gradle `8.13` y Kotlin `2.2.10` |

Arquitectura del repositorio:

- `app`: módulo de aplicación Android (`org.teslasoft.assistant`)
- `teslasoft-id`: módulo de librería interna para utilidades de autenticación/cliente (`org.teslasoft.core.auth`)
- Metadatos JSON en la raíz del repositorio (`ai_sets.json`, `explore.json`, `experiment.json`) usados para conjuntos de modelos, descubrimiento y metadatos de workflows
- `i18n/`: directorio de documentación multilingüe

## Capturas de pantalla

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

## Información para quienes quieran usar modelos Google Gemini con esta app

SpeakGPT no admite directamente claves API de Google, pero puedes usar Gemini a través de OpenRouter.

Más información: [OpenRouter Models](https://openrouter.ai/docs#models)

## Para quienes quieran algo gratuito con poco o ningún esfuerzo

> [!WARNING]
> 
> Las funciones gratuitas suelen tener restricciones. Esta app es de código abierto y se proporciona tal cual. No ofrece acceso premium gratuito a los servicios flagship de API de terceros.
> 
> Si esperas acceso premium totalmente gratuito, es más seguro usar otro producto. Preguntas como "clave API incorrecta" suelen resolverse comprobando tu endpoint y configuración de modelo. Gracias por entenderlo.
>
> Todos los demás usuarios legítimos son bienvenidos.

## Proveedores de API compatibles

| Proveedor | Nivel de soporte | Notas |
|---|---|---|
| OpenAI | Soporte total | Ruta principal de integración |
| GROQ | Soporte parcial | Algunas funciones pueden variar |
| Azure | Soporte parcial | Los detalles de endpoint/modelo pueden diferir |
| OpenRouter | Solo generación de texto | Probado con modelos Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI |
| Otro | Probado por la comunidad | Se agradecen comentarios |

> [!NOTE]
> 
> Para cambiar de proveedor, abre la configuración de la app y selecciona el endpoint de API. También puedes añadir un endpoint OpenAI-compatible personalizado.

## Características básicas

✅ Capacidades implementadas:

- [x] Chat (guardado local, importación/exportación compatible)
- [x] Generación de imágenes
- [x] Reconocimiento de imágenes (adjuntar imágenes/fotos en chat)
- [x] Flujos de prompt de activación y mensajes de sistema
- [x] Entrada de voz (Whisper y Google)
- [x] Integración con asistentes
- [x] SpeakGPT en menú contextual
- [x] SpeakGPT en hoja de compartir
- [x] Funcionalidades de llamada a funciones
- [x] Biblioteca de prompts
- [x] Múltiples diseños de chat
- [x] Diseño adaptativo
- [x] Cobertura amplia de modelos
- [x] Sin captcha
- [x] Uso con pago por uso
- [x] Consejos y guía de onboarding para nuevos usuarios
- [x] Soporte para modelos ajustados/personalizados
- [x] Modo oscuro AMOLED
- [x] Soporte de proveedor API personalizado
- [x] Personalización de parámetros del modelo (`temperature`, `topP`, `frequencyPenalty`, `presencePenalty`, `logit_bias`)
- [x] Playground
- [x] Acceso a familias insignia recientes como o1, o3, o4, gpt-4.1, gpt-4.5, gpt-image-1

## Estructura del proyecto

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

## Requisitos previos

- Android Studio (se recomienda la versión estable actual)
- Android SDK con `compileSdk 36`
- JDK 21 (`sourceCompatibility`/`targetCompatibility` alineados con Java 21 en la configuración del proyecto)
- Git
- Acceso a Internet para dependencias de Gradle y APIs de proveedores

Datos del sistema de compilación desde la configuración del repositorio:

| Componente | Versión / Valor |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Plugin de Kotlin | `2.2.10` |
| Wrapper de Gradle | `8.13` |
| ID de paquete de la app | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## Instalación

### 1. Clonar repositorio

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Abrir en Android Studio

- Abre `build.gradle` desde Android Studio.
- Espera a que termine la sincronización de Gradle.

### 3. Compilar APK de depuración

```bash
./gradlew assembleDebug
```

### 4. Instalar en un dispositivo/emulador conectado

```bash
./gradlew installDebug
```

### 5. Verificación de calidad opcional

```bash
./gradlew lint
```

## Uso

### Flujo del usuario final (en la app)

1. Instala la app desde Google Play o una build de depuración local.
2. Completa el flujo de onboarding.
3. Abre la configuración de API y selecciona un proveedor/endpoint.
4. Añade una clave API válida (se almacena localmente en el dispositivo).
5. Selecciona un modelo y empieza con chat, visión, generación de imágenes o voz.

### Integraciones disponibles en Android

- Integración con asistente (`ASSIST` intent)
- Integración en hoja de compartir (`SEND`, `SEND_MULTIPLE` intents)
- Integración de procesamiento de texto (`PROCESS_TEXT`)
- Enlaces profundos para `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Configuración

### Endpoints y proveedores de API

- Abre **Settings** en la app.
- Elige **API endpoint** para cambiar entre proveedores integrados.
- Añade un endpoint personalizado si tu proveedor es compatible con OpenAI.

### Parámetros de modelo y generación

SpeakGPT permite ajustar en tiempo de ejecución:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Datos locales y seguridad

- Las conversaciones se guardan localmente y pueden importarse/exportarse.
- Valores sensibles como las claves API se manejan mediante preferencias cifradas.

### Notas y supuestos

- `google-services.json` existe en este repositorio para builds actuales; si se elimina en forks, algunas integraciones pueden requerir una configuración equivalente de Firebase/App services.
- El comportamiento del proveedor puede variar según el endpoint y la familia del modelo.

## Ejemplos

### Compilar APK de release

```bash
./gradlew assembleRelease
```

### Reconstrucción limpia

```bash
./gradlew clean assembleDebug
```

### Usar OpenRouter para modelos de la familia Gemini

1. Crea una clave API de OpenRouter.
2. En configuración de SpeakGPT, selecciona/añade el endpoint de OpenRouter.
3. Elige un modelo compatible con Gemini.
4. Inicia un chat y verifica las respuestas.

### Ejecutar compilación limpia completa

```bash
./gradlew clean build
```

## Notas de desarrollo

- Este es un proyecto Android multi-módulo (`:app`, `:teslasoft-id`).
- Los tipos de compilación `debug` y `release` usan `minifyEnabled true` y `shrinkResources true` en la configuración actual.
- Las reglas ProGuard/R8 están en:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- La documentación web integrada está ubicada en:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Los recursos de localización están en `app/src/main/res/values-*`.
- Las traducciones del README están en `i18n/` para variantes de idioma.

## Solución de problemas

| Incidencia | Qué revisar |
|---|---|
| Clave API incorrecta / fallo de autenticación | Comprueba que la clave sea válida, la compatibilidad del proveedor y la disponibilidad del modelo. Algunos modelos flagship requieren verificación extra de cuenta. |
| Desajuste de endpoint o modelo | Valida que tu endpoint personalizado siga formatos OpenAI-compatible de solicitud/respuesta. Prueba cambiar el preset de endpoint en Ajustes y vuelve a intentarlo. |
| Errores de compilación | Confirma que JDK 21 esté activo, sincroniza Gradle y verifica que Gradle wrapper sea `8.13` con `./gradlew --version`, luego ejecuta `./gradlew clean build`. |
| Errores en tiempo de ejecución en Android legacy | El proyecto está en `minSdk 28`. Se esperan advertencias de deprecación para Android 9/10/11 por evolución de la política de soporte. |

## Hoja de ruta

### ❌ Funcionalidades previstas

- [ ] Rutinas del dispositivo (configurar alarma o abrir app)
- [ ] Sincronizar historial de chat
- [ ] Portal de intercambio de prompts / flujo estilo marketplace
- [ ] Navegación oficial/herramientas para workflows con acceso a internet

## Seguridad de clave API

SpeakGPT usa claves API para solicitar a proveedores, por lo que las credenciales están acotadas y son más seguras que los flujos de cuenta/contraseña.

- Tu clave API se almacena localmente y no se comparte por la app.
- Puedes revocar las claves desde tu consola del proveedor en cualquier momento.
- Si quieres, usa una clave dedicada para SpeakGPT.

Recordatorios de seguridad:

1. Mantén una clave API separada para SpeakGPT.
2. Configura límites de facturación.
3. Activa el monitoreo de uso para controlar costos.
4. Revoca las claves cuando detectes uso sospechoso.

Por qué las releases están ofuscadas:

La ofuscación y reducción de recursos mejoran el tamaño del paquete, el rendimiento y reducen riesgo de ingeniería inversa en torno al manejo de credenciales. Puedes pedir una build sin ofuscar o compilarla tú mismo.

> [!CAUTION]
> 
> No instales builds de fuentes no confiables. Builds de terceros pueden modificarse e introducir malware. Las builds oficiales se verifican con VirusTotal y se publican por canales oficiales.

## Identidad del desarrollador

| Campo | Valor |
|---|---|
| Nombre del desarrollador | Dmytro Ostapenko (AndraxDev) |
| Contacto | dostapenko82@gmail.com, +421951829517 |
| Dirección legal | Južná trieda 4B, 04001 Košice, Slovakia |
| ID legal de entidad | 55545386 (D-U-N-S: 933739642) |
| Licencia de actividad comercial | OU-KE-OZP1-2023/031005-2 (Emitida el 14 de junio de 2023 según el § 10(1)(a) de la Ley Nº 455/1991 Coll. on Trade Licensing, enmendada) |
| VAT ID | SK3121636045 |

(Si quieres saber dónde va tu dinero al apoyar económicamente el proyecto o si en el futuro aparecen funciones de pago.)

## Contribuir

Las contribuciones son bienvenidas.

- Informa errores en Issues con pasos de reproducción.
- Propón nuevas funciones con título y contexto claros.
- Mantén los PRs acotados e incluye justificación y notas de pruebas.

## Licencia

Este proyecto está licenciado bajo Apache License 2.0. Consulta [LICENSE.md](LICENSE.md).

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
