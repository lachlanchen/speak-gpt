[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Asistente de IA de código abierto con enfoque Android que unifica chat, voz, visión y generación de imágenes.

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#quick-facts)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#prerequisites)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#prerequisites)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#license)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#prerequisites)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#prerequisites)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#prerequisites)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)

SpeakGPT es un asistente de IA avanzado e intuitivo de código abierto para Android. Integra proveedores modernos de modelos de lenguaje de gran escala (LLM) y flujos de trabajo multimodales (chat, voz, generación de imágenes, visión) en una sola app móvil.

Oficialmente es compatible con modelos GPT, LLAMA, MIXTRAL, GEMMA, Gemini Vision (normal y pro), DALL-E y otros modelos.

## Quick facts

| Dato rápido | Detalles |
|---|---|
| 📱 Plataforma | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Uso principal | Trae-tu-propio-endpoint + trae-tu-propia-clave |
| 🧩 Tipo de app | Cliente de IA de código abierto (no proveedor de API) |
| 🌐 Web complementaria | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> Este proyecto forma parte de mi tesis de licenciatura. Se requiere atribución para usar este trabajo. Copyright (c) 2023-2025 Dmytro Ostapenko. Todos los derechos reservados.
> 
> Citar como: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> Pronto dejaremos de dar soporte a estas versiones de Android: 9, 10 y 11. Esto está relacionado con cambios recientes en el SDK y la seguridad. Las versiones más antiguas de Android usan características obsoletas e inestables como RenderScript.

## Contenido

- [Descarga](#descarga)
- [SpeakGPT Web](#speakgpt-web)
- [Resumen](#resumen)
- [Capturas de pantalla](#capturas-de-pantalla)
- [Información para quienes quieran usar modelos Google Gemini con esta app](#información-para-quienes-quieran-usar-modelos-google-gemini-con-esta-app)
- [Para quienes buscan una opción gratuita con poco o ningún esfuerzo](#para-quienes-buscan-una-opción-gratuita-con-poco-o-ningún-esfuerzo)
- [Proveedores de API compatibles](#proveedores-de-api-compatibles)
- [Características principales](#características-principales)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Requisitos previos](#prerequisites)
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

📦 Instala desde Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Abre SpeakGPT Web: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

Repositorio de GitHub: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Resumen

SpeakGPT es un cliente para Android centrado en APIs de IA. Está diseñado con el enfoque BYOE y BYOK (trae tu propio endpoint y trae tu propia clave), para que elijas proveedor, modelo y perfil de coste/rendimiento.

### En resumen

| Área | Resumen |
|---|---|
| 💬 Experiencias principales | Chat, generación de imágenes, reconocimiento de imágenes, entrada de voz, integraciones de asistente |
| 🔌 Estrategia de proveedor | Endpoints compatibles con OpenAI con proveedores configurables y endpoints personalizados |
| 🔐 Manejo de datos | Las claves API se guardan localmente; los chats pueden importarse o exportarse |
| 🧱 Pila tecnológica | Proyecto Android multi-módulo con AGP `8.12.2`, Gradle `8.13` y Kotlin `2.2.10` |

Arquitectura del repositorio:

- `app`: módulo de aplicación Android (`org.teslasoft.assistant`)
- `teslasoft-id`: módulo de librería interna de Android para utilidades de autenticación/cliente (`org.teslasoft.core.auth`)
- `ai_sets.json`, `explore.json`, `experiment.json` en la raíz, con metadatos para conjuntos de modelos, descubrimiento y flujos de importación/exportación
- `i18n/`: directorio de salida multilingüe de README en el repositorio

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

SpeakGPT no admite directamente claves API de Google, pero puedes usar Google Gemini a través de la API de OpenRouter.

Más información: [OpenRouter Models](https://openrouter.ai/docs#models)

## Para quienes buscan una opción gratuita con poco o ningún esfuerzo

> [!WARNING]
> 
> Recuerda: lo gratis suele venir con condiciones. ESTA APP ES UN CLIENTE DE CÓDIGO ABIERTO QUE SE OFRECE TAL CUAL. POR SÍ MISMA NO OFRECE ACCESO COMPLETAMENTE GRATUITO A LAS FUNCIONES PREMIUM DE LOS PROVEEDORES DE API (COMO MODELOS PRINCIPALES DE IA Y FUNCIONES ESPECIALES). SI HAS VENIDO AQUÍ PARA USAR EL TRABAJO DE OTROS DE FORMA GRATUITA SIN CRÉDITO, ES MEJOR QUE NO USES ESTA APP Y BUSQUES OTRA ALTERNATIVA. NO RESPONDERÉ A PREGUNTAS DEL TIPO "CLAVE API INCORRECTA, ¿POR QUÉ ESTA APP ME REDIRIGE A UN SITIO EXTERNO PARA OBTENER LA CLAVE API?". GRACIAS POR ENTENDER.
> El resto de personas bien intencionadas son bienvenidas.

## Proveedores de API compatibles

| Proveedor | Nivel de soporte | Notas |
|---|---|---|
| OpenAI | Soporte completo | Vía de integración principal |
| GROQ | Soporte parcial | Algunas funciones pueden variar |
| Azure | Soporte parcial | Endpoint y modelo pueden variar según la implementación |
| OpenRouter | Solo generación de texto | Probado con modelos Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI |
| Otros | Probados por la comunidad | Se agradece cualquier feedback |

> [!NOTE]
> 
> Para cambiar de proveedor de API, ve a Ajustes y selecciona el endpoint. También puedes añadir tu propio proveedor API personalizado.

## Características principales

✅ Funcionalidades implementadas:

- [x] Chat (guardado localmente, con opción de importar/exportar)
- [x] Generación de imágenes
- [x] Reconocimiento de imágenes (usa tus imágenes y fotos con ChatGPT)
- [x] Prompt de activación
- [x] Mensaje del sistema
- [x] Entrada de voz (Whisper y Google)
- [x] Assistant
- [x] SpeakGPT en menú contextual
- [x] SpeakGPT en la hoja de compartir
- [x] Llamadas a funciones
- [x] Biblioteca de prompts
- [x] Diseños de chat variados
- [x] Diseño adaptativo
- [x] Varios modelos
- [x] Sin captcha
- [x] Sistema de pago por uso
- [x] Consejos para principiantes
- [x] Soporte para modelos personalizados fine-tuned
- [x] Modo oscuro AMOLED
- [x] Soporte para proveedores API personalizados
- [x] Ajustes de parámetros del modelo: `temperature`, `topP`, `frequencyPenalty`, `presencePenalty` y `logit_bias`
- [x] Playground
- [x] Acceso a modelos destacados más nuevos como o1, o3, o4, gpt-4.1, gpt-4.5 y gpt-image-1 (algunos pueden requerir verificación de identidad en OpenAI)

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

## Prerequisites

- Android Studio (se recomienda la versión estable actual)
- Android SDK con `compileSdk 36`
- JDK 21 (la compatibilidad source/target del proyecto es Java 21)
- Git
- Acceso a internet para resolución de dependencias y APIs de proveedores de modelos

Datos del sistema de compilación del repositorio:

| Componente | Versión / Valor |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Plugin de Kotlin | `2.2.10` |
| Gradle wrapper | `8.13` |
| Package ID de la app | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## Instalación

### 1. Clonar el repositorio

```bash

git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Compilar APK de depuración

```bash
./gradlew assembleDebug
```

### 3. Instalar en un dispositivo o emulador conectado

```bash
./gradlew installDebug
```

### 4. Comprobaciones de calidad opcionales

```bash
./gradlew lint
```

## Uso

### Flujo para usuarios finales (en la app)

1. Instala la app desde Google Play o desde un build de debug local.
2. Completa el flujo de onboarding.
3. Abre la configuración de API y selecciona o añade tu endpoint/proveedor.
4. Introduce la clave API (se guarda localmente en tu dispositivo).
5. Elige el modelo y empieza chat, visión, generación de imágenes o flujos de voz.

### Integraciones disponibles en Android

- Integración del asistente (`ASSIST` intent)
- Integración con hoja de compartir (`SEND` y `SEND_MULTIPLE` intents)
- Integración de procesamiento de texto (`PROCESS_TEXT`)
- Enlaces profundos para `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Configuración

### Endpoints y proveedores de API

- Abre **Settings** en la app.
- Selecciona **API endpoint** para cambiar entre proveedores preconfigurados.
- Añade un endpoint personalizado si tu proveedor es compatible con OpenAI.

### Modelo y parámetros de generación

SpeakGPT permite ajustar en tiempo de ejecución parámetros como:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Datos locales y seguridad

- Las conversaciones se guardan localmente y pueden importarse/exportarse.
- Valores sensibles, como claves API, se manejan con preferencias cifradas.

### Notas y supuestos

- `google-services.json` está presente en este repositorio; si haces un fork y lo quitas, algunas integraciones podrían requerir tu propia configuración.
- La compatibilidad con proveedores puede variar según la implementación del endpoint y la familia de modelos.

## Ejemplos

### Ejemplo 1: Construir APK de release

```bash
./gradlew assembleRelease
```

### Ejemplo 2: Reconstrucción limpia

```bash
./gradlew clean assembleDebug
```

### Ejemplo 3: Usar OpenRouter para modelos de la familia Gemini

1. Crea una clave API de OpenRouter.
2. En la configuración de SpeakGPT, selecciona o añade el endpoint de OpenRouter.
3. Elige un modelo de OpenRouter compatible con Gemini.
4. Inicia un chat y verifica la generación de respuestas.

## Notas de desarrollo

- Este es un proyecto Android modular (`:app`, `:teslasoft-id`).
- Los tipos de build `debug` y `release` tienen `minifyEnabled true` y `shrinkResources true` en la configuración actual.
- Las reglas ProGuard/R8 están en:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- La documentación web embebida está en:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Los recursos de localización están en `app/src/main/res/values-*`.
- La carpeta de salida i18n del README está en `i18n/` (los README por idioma se generan en pasos separados del pipeline).

## Solución de problemas

| Problema | Qué comprobar |
|---|---|
| "Clave API incorrecta" o errores de autenticación | Verifica que la clave sea válida para el proveedor elegido, que el modelo seleccionado esté disponible en tu cuenta y si el proveedor exige verificación adicional para modelos insignia. |
| Desajuste de endpoint/modelo | Si usas un endpoint de proveedor personalizado, asegura el formato de solicitud/respuesta compatible con OpenAI. Prueba cambiar la configuración del endpoint y volver a probar. |
| Problemas de compilación | Comprueba que JDK 21 esté activo, sincroniza el proyecto en Android Studio, ejecuta `./gradlew --version` y verifica que el wrapper use Gradle `8.13`, luego reintenta con `./gradlew clean build`. |
| Problemas en Android antiguos | El proyecto soporta actualmente `minSdk 28` (Android 9). Se advierte que en el futuro podría dejarse de soportar Android 9/10/11 debido a cambios de SDK y seguridad. |

## Hoja de ruta

### ❌ Pendiente de añadir (comparte tus ideas en Issues)

- [ ] Rutinas de dispositivo (como configurar alarma o abrir apps)
- [ ] Sincronización del historial de chat
- [ ] Añadir un portal de intercambio de modelos tipo tienda de prompts
- [ ] Capacidades de navegación oficial (permitir que modelos GPT AI accedan a internet)

## Seguridad de clave API

SpeakGPT usa la API de OpenAI para darte la mejor experiencia posible. Usar claves API es más seguro que usar usuario y contraseña. Tu información personal no se puede obtener usando una clave API. OpenAI ofrece acceso API económico a sus servicios. Tu clave API se guarda localmente en tu dispositivo y no se comparte con nadie. SpeakGPT no recoge datos personales. SpeakGPT es de código abierto y puedes revisar el código por ti mismo. Cada versión de SpeakGPT se comprueba en VirusTotal.
Si tienes alguna duda, puedes [revocar tu clave API](https://platform.openai.com/account/api-keys) o usar una clave API separada para SpeakGPT.

Para proteger tu clave API realiza estos pasos:

1. Ten una clave API separada para SpeakGPT.
2. Configura un límite de facturación.
3. Activa el seguimiento de uso para ver cuánto recurso usa SpeakGPT y su coste.
4. Si tienes dudas, revoca tu clave API.

> ¿Por qué ofuscamos el código en versiones de producción?
> 
> La ofuscación y reducción de recursos nos permite optimizar tamaño y rendimiento, y protegerlo frente a ingeniería inversa o manipulación, además de mantener tus credenciales en un sitio seguro. Puedes solicitar una build sin ofuscación o compilarla tú mismo para comprobar la seguridad de la app.

> [!CAUTION]
> 
> ¡CUIDADO CON EL MALWARE! Puedes compilar y modificar SpeakGPT, pero ten cuidado si alguien externo te propone instalar su build. Esa build podría contener malware. Las builds oficiales no incluyen malware y son verificadas con más de 60 antivirus distintos a través de VirusTotal. Puedes encontrar el informe de VirusTotal en cada página de release y comparar el hash de los binarios.

## Identidad del desarrollador

| Campo | Valor |
|---|---|
| Nombre del desarrollador | Dmytro Ostapenko (AndraxDev) |
| Contacto | dostapenko82@gmail.com, +421951829517 |
| Dirección legal | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| ID de entidad legal | 55545386 (D-U-N-S: 933739642) |
| Licencia de actividad comercial | OU-KE-OZP1-2023/031005-2 (Emitida el 14 de junio de 2023 según § 10 sección 1 letra a) de la Ley No. 455/1991 Coll. sobre licencia comercial (Trade Licensing Act) tras sus enmiendas) |
| VAT ID | SK3121636045 |

(Para que sepas a dónde llegará tu aportación si decides apoyar el proyecto económicamente o si en el futuro incorpora funciones de pago.)

## Contribuir

Las contribuciones son bienvenidas.

- Reporta bugs en Issues indicando pasos de reproducción.
- Solicita nuevas funciones (usa etiquetas claras en los issues).
- Si envías código, mantén los cambios acotados e incluye justificación.

## ❤️ Support

| Donate | PayPal | Stripe |
|---|---|---|
| [![Donate](https://img.shields.io/badge/Donate-LazyingArt-0EA5E9?style=for-the-badge&logo=ko-fi&logoColor=white)](https://chat.lazying.art/donate) | [![PayPal](https://img.shields.io/badge/PayPal-RongzhouChen-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/RongzhouChen) | [![Stripe](https://img.shields.io/badge/Stripe-Donate-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

### Agradecimientos

- Reporta errores
- Bríndame apoyo :)
- Solicita nuevas funciones. No olvides marcar el issue con una etiqueta

### Invítame un café

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## Licencia

Este proyecto está bajo la licencia Apache License 2.0. Consulta [LICENSE.md](LICENSE.md).

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
