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

SpeakGPT es un asistente de IA avanzado y muy intuitivo de código abierto para Android. Integra proveedores modernos de modelos de lenguaje grandes (LLM) y flujos de trabajo multimodales (chat, voz, generación de imágenes, visión) en una sola app móvil.

Oficialmente es compatible con modelos GPT, LLAMA, MIXTRAL, GEMMA, Gemini (regular y pro) Vision, DALL-E y otros modelos.

| Datos rápidos | Detalles |
|---|---|
| 📱 Plataforma | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Uso principal | Trae tu propio endpoint + trae tu propia clave |
| 🧩 Tipo de app | Cliente de IA de código abierto (no proveedor de API) |
| 🌐 Complemento web | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> Este proyecto forma parte de mi tesis de grado. Se requiere atribución para usar este trabajo. Copyright (c) 2023-2025 Dmytro Ostapenko. Todos los derechos reservados.
>
> Citar como: Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> Pronto dejaremos de dar soporte a las siguientes versiones de Android: 9, 10, 11. Está relacionado con cambios recientes en SDK y seguridad. Las versiones antiguas de Android usan funciones obsoletas e inestables como RenderScript.

## Tabla de contenido

- [Descarga](#descarga)
- [SpeakGPT Web](#speakgpt-web)
- [Resumen](#resumen)
- [Capturas de pantalla](#capturas-de-pantalla)
- [Información para usuarios que quieren usar modelos Google Gemini con esta app](#información-para-usuarios-que-quieren-usar-modelos-google-gemini-con-esta-app)
- [Para quienes no quieren complicarse y quieren usar algo gratis con poco o ningún esfuerzo](#para-quienes-no-quieren-complicarse-y-quieren-usar-algo-gratis-con-poco-o-ningún-esfuerzo)
- [Proveedores de API compatibles](#proveedores-de-api-compatibles)
- [Funciones básicas](#funciones-básicas)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Requisitos previos](#requisitos-previos)
- [Instalación](#instalación)
- [Uso](#uso)
- [Configuración](#configuración)
- [Ejemplos](#ejemplos)
- [Notas de desarrollo](#notas-de-desarrollo)
- [Solución de problemas](#solución-de-problemas)
- [Hoja de ruta](#hoja-de-ruta)
- [Seguridad de la clave API](#seguridad-de-la-clave-api)
- [Identidad del desarrollador](#identidad-del-desarrollador)
- [Contribuir](#contribuir)
- [Soporte](#soporte)
- [Invítame un café](#invítame-un-café)
- [Licencia](#licencia)

## Descarga

📦 Instala desde Google Play:

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Abre SpeakGPT Web: [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

Repositorio de GitHub: [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Resumen

SpeakGPT es un cliente para Android centrado en APIs de IA. Está diseñado alrededor del enfoque de traer tu propio endpoint y tu propia clave, para que los usuarios puedan elegir proveedor, modelo y perfil de costo/rendimiento.

Arquitectura del repositorio:

- `app`: módulo de aplicación Android (`org.teslasoft.assistant`)
- `teslasoft-id`: módulo interno de biblioteca Android para utilidades de autenticación/cliente (`org.teslasoft.core.auth`)
- Metadatos JSON en la raíz del repositorio (`ai_sets.json`, `explore.json`, `experiment.json`) usados para conjuntos de modelos, descubrimiento y flujos de importación/exportación
- `i18n/`: directorio de salida README multilingüe (presente en el repositorio)

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

## Información para usuarios que quieren usar modelos Google Gemini con esta app

SpeakGPT no admite claves de API de Google directamente, pero aun así puedes usar Google Gemini mediante la API de OpenRouter.

Más información: [OpenRouter Models](https://openrouter.ai/docs#models)

## Para quienes no quieren complicarse y quieren usar algo gratis con poco o ningún esfuerzo

> [!WARNING]
>
> Recuerda que el queso gratis solo existe en la ratonera. ESTA APP ES UN CLIENTE DE CÓDIGO ABIERTO PROPORCIONADO TAL CUAL. POR SÍ MISMA NO OFRECE ACCESO COMPLETAMENTE GRATUITO A LAS FUNCIONES PREMIUM DE LOS PROVEEDORES DE API (COMO MODELOS DE IA INSIGNIA Y FUNCIONES ESPECIALES). SI VIENES AQUÍ PARA USAR EL TRABAJO DE OTROS GRATIS Y SIN CRÉDITO, MEJOR OMITE ESTA APP Y BUSCA OTRA COSA. NO VOY A RESPONDER PREGUNTAS COMO "API KEY INCORRECTA, ¿POR QUÉ ESTA APP ME REDIRIGE AL SITIO EXTERNO PARA LA API KEY?". GRACIAS POR ENTENDER.
> Todas las demás personas razonables son bienvenidas.

## Proveedores de API compatibles

| Proveedor | Nivel de soporte | Notas |
|---|---|---|
| OpenAI | Soporte completo | Ruta principal de integración |
| GROQ | Soporte parcial | Algunas funciones pueden variar |
| Azure | Soporte parcial | Los detalles de endpoint/modelo pueden diferir |
| OpenRouter | Solo generación de texto | Probado con modelos Gemini, Claude, Perplexity, Llama, Gemma, Mistral y OpenAI |
| Other | Probado por la comunidad | Se agradece la retroalimentación |

> [!NOTE]
>
> Para cambiar tu proveedor de API, ve a la configuración y selecciona el endpoint de API. También puedes agregar tu proveedor de API personalizado.

## Funciones básicas

✅ Capacidades implementadas:

- [x] Chat (se guarda localmente, pero puede importarse/exportarse si hace falta)
- [x] Generación de imágenes
- [x] Reconocimiento de imágenes (usa tus imágenes y fotos con ChatGPT)
- [x] Prompt de activación
- [x] Mensaje de sistema
- [x] Entrada de voz (Whisper y Google)
- [x] Assistant
- [x] SpeakGPT en menú contextual
- [x] SpeakGPT en Share sheet
- [x] Funciones de function calling
- [x] Biblioteca de prompts
- [x] Distinto diseño de chat
- [x] Diseño adaptativo
- [x] Muchos modelos diferentes
- [x] Sin captcha
- [x] Sistema de pago por uso
- [x] Consejos para principiantes
- [x] Compatibilidad con modelos fine-tuned personalizados
- [x] Modo oscuro AMOLED
- [x] Soporte para proveedor de API personalizado
- [x] Personaliza parámetros del modelo como `temperature`, `topP`, `frequencyPenalty`, `presencePenalty` y `logit_bias`
- [x] Playground
- [x] Acceso a los modelos insignia más recientes como o1, o3, o4, gpt-4.1, gpt-4.5 y gpt-image-1 (algunos de estos modelos pueden requerir que verifiques tu identidad con OpenAI)

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
- JDK 21 (la compatibilidad source/target del proyecto es Java 21)
- Git
- Acceso a internet para resolver dependencias y APIs de proveedores de modelos

Datos del sistema de compilación según la configuración del repositorio:

| Componente | Versión / Valor |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## Instalación

### 1. Clonar el repositorio

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Compilar APK de debug

```bash
./gradlew assembleDebug
```

### 3. Instalar en dispositivo/emulador conectado

```bash
./gradlew installDebug
```

### 4. Comprobaciones de calidad opcionales

```bash
./gradlew lint
```

## Uso

### Flujo para usuario final (en la app)

1. Instala la app desde Google Play o una build local de debug.
2. Completa el flujo de onboarding.
3. Abre la configuración de API y selecciona o agrega tu endpoint/proveedor.
4. Introduce la clave API (se almacena localmente en tu dispositivo).
5. Selecciona un modelo y empieza chat, visión, generación de imágenes o flujos de voz.

### Integraciones Android disponibles

- Integración de Assistant (intent `ASSIST`)
- Integración de Share sheet (intents `SEND` y `SEND_MULTIPLE`)
- Integración de process text (`PROCESS_TEXT`)
- Enlaces profundos para `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Configuración

### Endpoints API y proveedores

- Abre **Settings** en la app.
- Elige **API endpoint** para cambiar entre proveedores preconfigurados.
- Agrega un endpoint personalizado si tu proveedor es compatible con OpenAI.

### Modelo y parámetros de generación

SpeakGPT admite ajustes en tiempo de ejecución para parámetros de generación como:

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Datos locales y seguridad

- Las conversaciones se almacenan localmente y se pueden importar/exportar.
- Los valores sensibles como las claves API se manejan en preferencias cifradas.

### Notas y supuestos

- `google-services.json` está presente en este repositorio; si haces fork y lo eliminas, algunas integraciones pueden requerir tu propia configuración.
- La compatibilidad del proveedor puede variar según la implementación del endpoint y la familia de modelos.

## Ejemplos

### Ejemplo 1: Compilar APK release

```bash
./gradlew assembleRelease
```

### Ejemplo 2: Reconstrucción limpia

```bash
./gradlew clean assembleDebug
```

### Ejemplo 3: Usar OpenRouter para modelos de la familia Gemini

1. Crea una clave API de OpenRouter.
2. En la configuración de SpeakGPT, selecciona/agrega el endpoint de OpenRouter.
3. Elige un modelo de OpenRouter con soporte Gemini.
4. Inicia un chat y verifica la generación de respuestas.

## Notas de desarrollo

- Este es un proyecto Android de múltiples módulos (`:app`, `:teslasoft-id`).
- Los tipos de build `debug` y `release` tienen `minifyEnabled true` y `shrinkResources true` en la configuración actual.
- Las reglas de ProGuard/R8 están en:
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- La documentación web embebida está en:
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Los recursos de localización están en `app/src/main/res/values-*`.
- El directorio de salida i18n del README existe en `i18n/` (los archivos README específicos por idioma se generan por separado en pasos del pipeline).

## Solución de problemas

| Problema | Qué revisar |
|---|---|
| "Incorrect API key" o fallos de autenticación | Verifica que tu clave sea válida para el proveedor seleccionado, que el modelo elegido esté disponible en tu cuenta y si el proveedor requiere verificación adicional para modelos insignia. |
| Incompatibilidad endpoint/modelo | Si usas un endpoint de proveedor personalizado, asegúrate de que tenga formato de solicitud/respuesta compatible con OpenAI. Prueba cambiar el preset de endpoint en configuración y vuelve a probar. |
| Problemas de compilación | Confirma que JDK 21 esté activo, sincroniza el proyecto Gradle en Android Studio, ejecuta `./gradlew --version` y verifica que el wrapper use Gradle `8.13`, luego reintenta con `./gradlew clean build`. |
| Problemas en ejecución en versiones antiguas de Android | El proyecto actualmente admite `minSdk 28` (Android 9). El proyecto advierte que el soporte para Android 9/10/11 podría eliminarse en el futuro por cambios de SDK/seguridad. |

## Hoja de ruta

### ❌ Planeado para agregar (Comparte tus ideas en Issues)

- [ ] Rutinas del dispositivo (como configurar alarma o abrir app)
- [ ] Sincronizar historial de chat
- [ ] Agregar un portal de intercambio de modelos como tienda de prompts
- [ ] Capacidades oficiales de navegación (hacer que los modelos GPT AI accedan a internet)

## Seguridad de la clave API

SpeakGPT usa la API de OpenAI para ofrecerte la mejor experiencia. Usar claves API es más seguro que usar usuario/contraseña. Tu información personal no puede obtenerse usando una clave API. OpenAI ofrece acceso API económico a sus servicios. Tu clave API se almacena localmente en tu dispositivo y no se comparte con nadie. SpeakGPT no recopila datos personales. SpeakGPT es de código abierto y puedes revisar el código por tu cuenta. Cada versión de SpeakGPT se verifica en VirusTotal.
Si tienes alguna preocupación, puedes [revocar tu API key](https://platform.openai.com/account/api-keys) o usar una clave API separada para SpeakGPT.

Para asegurar tu clave API, realiza los siguientes pasos:

1. Asegúrate de tener una clave API separada para SpeakGPT.
2. Configura un límite de facturación.
3. Activa el monitoreo de uso para que puedas ver cuántos recursos usa SpeakGPT y cuánto cuesta.
4. Si tienes alguna preocupación, puedes revocar tu clave API.

> ¿Por qué ofuscamos nuestro código en los lanzamientos de producción?
>
> La ofuscación y la reducción de recursos nos permiten optimizar el tamaño de la app, su rendimiento y protegerla contra ingeniería inversa o manipulación, y asegurarnos de que tus credenciales como claves API estén en un lugar seguro. Puedes solicitar una build sin ofuscar o compilarla tú mismo para comprobar que nuestra app es segura.

> [!CAUTION]
>
> ¡CUIDADO CON EL MALWARE! Puedes compilar SpeakGPT y modificarlo, pero ten mucho cuidado cuando otra persona te ofrezca instalar su build. Esa build podría contener malware. Las builds oficiales no contienen malware y se revisan con más de 60 antivirus diferentes usando VirusTotal. Puedes encontrar el informe de VirusTotal en la página de cada release y comparar el hash de los archivos binarios.

## Identidad del desarrollador

| Campo | Valor |
|---|---|
| Nombre del desarrollador | Dmytro Ostapenko (AndraxDev) |
| Contacto | dostapenko82@gmail.com, +421951829517 |
| Dirección legal | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| ID de entidad legal | 55545386 (D-U-N-S: 933739642) |
| Licencia de actividad comercial | OU-KE-OZP1-2023/031005-2 (Emitida el 14 June 2023 según § 10 sección 1 letra a) de la Ley No. 455/1991 Coll. sobre licencias comerciales (Trade Licensing Act) y sus modificaciones) |
| VAT ID | SK3121636045 |

(Para que sepas a dónde envías tu dinero si decides apoyar financieramente el proyecto o si el proyecto tiene funciones de pago en el futuro)

## Contribuir

Las contribuciones son bienvenidas.

- Reporta errores en Issues con pasos de reproducción.
- Solicita nuevas funciones (usa etiquetas claras de issue).
- Si envías código, mantén los cambios acotados e incluye justificación.

## Soporte

### Se agradece que

- Reportes cualquier error
- Me apoyes :)
- Solicites nuevas funciones. No olvides marcar el issue con una etiqueta

## Invítame un café

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

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
