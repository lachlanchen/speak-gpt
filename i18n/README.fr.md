[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Assistant IA open-source orienté Android, avec des flux de chat, de voix, de vision et de génération d’images.

[![Platform](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#quick-facts)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#prerequisites)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#prerequisites)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square)](#license)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#prerequisites)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#prerequisites)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#prerequisites)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)

SpeakGPT est un assistant IA open-source avancé et très intuitif pour Android. Il intègre des fournisseurs modernes de grands modèles de langage (LLM) et des workflows multimodaux (chat, voix, génération d’images, vision) dans une seule application mobile.

Officiellement, il prend en charge les modèles GPT, LLAMA, MIXTRAL, GEMMA, Gemini (version normale et pro) Vision, DALL-E et d’autres modèles.

## Faits rapides

| Faits rapides | Détails |
|---|---|
| 📱 Plateforme | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Usage principal | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 Type d’application | Client IA open-source (pas un fournisseur d’API) |
| 🌐 Compagnon web | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> Ce projet fait partie de mon mémoire de licence. L’attribution est requise pour utiliser ce travail. Copyright (c) 2023-2025 Dmytro Ostapenko. Tous droits réservés.
>
> À citer comme suit : Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> Nous allons bientôt arrêter la prise en charge des versions Android suivantes : 9, 10, 11. C’est lié aux récentes évolutions du SDK et de la sécurité. Les versions plus anciennes d’Android utilisent des fonctionnalités obsolètes et instables, comme RenderScript.

## Table des matières

- [Téléchargement](#téléchargement)
- [SpeakGPT Web](#speakgpt-web)
- [Vue d’ensemble](#vue-densemble)
- [Captures d’écran](#captures-décran)
- [Informations pour les utilisateurs qui souhaitent utiliser Google Gemini avec cette application](#informations-pour-les-utilisateurs-qui-souhaitent-utiliser-google-gemini-avec-cette-application)
- [Pour ceux qui veulent quelque chose gratuitement avec peu ou pas d’effort](#pour-ceux-qui-veulent-quelque-chose-gratuitement-avec-peu-ou-pas-deffort)
- [Fournisseurs API pris en charge](#fournisseurs-api-pris-en-charge)
- [Fonctionnalités de base](#fonctionnalités-de-base)
- [Structure du projet](#structure-du-projet)
- [Prérequis](#prérequis)
- [Installation](#installation)
- [Utilisation](#utilisation)
- [Configuration](#configuration)
- [Exemples](#exemples)
- [Notes de développement](#notes-de-développement)
- [Dépannage](#dépannage)
- [Feuille de route](#feuille-de-route)
- [Sécurité des clés API](#sécurité-des-clés-api)
- [Identité du développeur](#identité-du-développeur)
- [Contribution](#contribution)
- [❤️ Support](#-support)
- [Licence](#licence)

## Téléchargement

📦 Installer depuis Google Play :

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Lancez SpeakGPT Web : [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

Dépôt GitHub : [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Vue d’ensemble

SpeakGPT est un client Android-first pour les API IA. Il est conçu autour du concept bring-your-own-endpoint et bring-your-own-key, pour que les utilisateurs puissent choisir le fournisseur, le modèle et le profil coût/performance.

### En bref

| Domaine | Résumé |
|---|---|
| 💬 Expériences centrales | Chat, génération d’images, reconnaissance d’images, entrée vocale, intégrations assistant |
| 🔌 Stratégie de fournisseurs | Endpoints compatibles OpenAI avec fournisseurs configurables et endpoints personnalisés |
| 🔐 Gestion des données | Clés API stockées localement ; les conversations peuvent être importées/exportées |
| 🧱 Stack technique | Projet Android multi-modules utilisant AGP `8.12.2`, Gradle `8.13`, Kotlin `2.2.10` |

Architecture du dépôt :

- `app` : module d’application Android (`org.teslasoft.assistant`)
- `teslasoft-id` : module de bibliothèque Android interne pour les utilitaires d’authentification/client (`org.teslasoft.core.auth`)
- Métadonnées JSON à la racine du dépôt (`ai_sets.json`, `explore.json`, `experiment.json`) utilisées pour les ensembles de modèles, la découverte et les flux d’import/export
- `i18n/` : répertoire de sortie des README multilingues (présent dans le dépôt)

## Captures d’écran

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

## Informations pour les utilisateurs qui souhaitent utiliser Google Gemini avec cette application

SpeakGPT ne prend pas directement en charge les clés API Google, mais vous pouvez tout de même utiliser Google Gemini via l’API OpenRouter.

Plus d’infos : [OpenRouter Models](https://openrouter.ai/docs#models)

## Pour ceux qui veulent quelque chose gratuitement avec peu ou pas d’effort

> [!WARNING]
>
> Souvenez-vous que le « fromage gratuit » peut n’être qu’un piège à souris. CETTE APPLICATION EST UN CLIENT OPEN-SOURCE FOURNI « EN L’ÉTAT ». ELLE N’OFFRE PAS D’ACCÈS COMPLÈTEMENT GRATUIT AUX FONCTIONNALITÉS PREMIUM DES FOURNISSEURS D’API (COMME LES MODÈLES IA PHARES ET LES FONCTIONNALITÉS SPÉCIALES). SI VOUS ÊTES ICI POUR UTILISER LE TRAVAIL DES AUTRES SANS PAYER ET SANS CREDIT, IL VAUT MIEUX PASSER À AUTRE CHOSE. JE N’EXPLIQUE PAS AUX QUESTIONS DU TYPE « MA CLÉ API EST INCORRECTE, POURQUOI CETTE APP ME REDIRIGE VERS UN SITE EXTERNE POUR OBTENIR UNE CLÉ API ? ». MERCI DE VOTRE COMPRÉHENSION.
> Toutes les autres personnes de bonne foi sont les bienvenues.

## Fournisseurs API pris en charge

| Fournisseur | Niveau de prise en charge | Notes |
|---|---|---|
| OpenAI | Prise en charge complète | Intégration principale |
| GROQ | Prise en charge partielle | Certaines fonctionnalités peuvent varier |
| Azure | Prise en charge partielle | L’endpoint et le modèle peuvent différer |
| OpenRouter | Génération de texte uniquement | Testé avec Gemini, Claude, Perplexity, Llama, Gemma, Mistral, modèles OpenAI |
| Autre | Testé par la communauté | Les retours sont les bienvenus |

> [!NOTE]
>
> Pour changer de fournisseur d’API, ouvrez les paramètres et sélectionnez l’endpoint API. Vous pouvez aussi ajouter votre propre fournisseur d’API personnalisé.

## Fonctionnalités de base

✅ Fonctionnalités implémentées :

- [x] Chat (enregistré localement mais pouvant être importé/exporté si nécessaire)
- [x] Génération d’images
- [x] Reconnaissance d’images (utilisez vos images et photos avec ChatGPT)
- [x] Prompt d’activation
- [x] Message système
- [x] Saisie vocale (Whisper et Google)
- [x] Assistant
- [x] SpeakGPT dans le menu contextuel
- [x] SpeakGPT dans la feuille de partage
- [x] Fonctionnalités d’appel de fonctions
- [x] Librairie de prompts
- [x] Mise en page de chat différente
- [x] Design adaptatif
- [x] Beaucoup de modèles différents
- [x] Pas de captcha
- [x] Paiement à l’usage
- [x] Conseils pour débutants
- [x] Les modèles personnalisés fine-tuned sont pris en charge
- [x] Mode sombre AMOLED
- [x] Prise en charge de fournisseurs d’API personnalisés
- [x] Personnalisation des paramètres de modèle tels que `temperature`, `topP`, `frequencyPenalty`, `presencePenalty` et `logit_bias`
- [x] Playground
- [x] Accès aux derniers modèles phares comme o1, o3, o4, gpt-4.1, gpt-4.5 et gpt-image-1 (Certains de ces modèles peuvent vous demander de vérifier votre identité via OpenAI)

## Structure du projet

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

## Prérequis

- Android Studio (version stable actuelle recommandée)
- Android SDK avec `compileSdk 36`
- JDK 21 (la compatibilité source/cible du projet est Java 21)
- Git
- Accès Internet pour la résolution des dépendances et les API des fournisseurs de modèles

Informations sur le système de build à partir de la configuration du dépôt :

| Composant | Version / Valeur |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Plugin Kotlin | `2.2.10` |
| Gradle Wrapper | `8.13` |
| Identifiant du package | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Générer l’APK debug

```bash
./gradlew assembleDebug
```

### 3. Installer sur un appareil ou un émulateur connecté

```bash
./gradlew installDebug
```

### 4. Vérifications qualité optionnelles

```bash
./gradlew lint
```

## Utilisation

### Flux utilisateur (dans l’application)

1. Installez l’application depuis Google Play ou depuis une version debug locale.
2. Terminez le parcours d’onboarding.
3. Ouvrez les réglages API et sélectionnez ou ajoutez votre endpoint/fournisseur.
4. Renseignez votre clé API (stockée localement sur votre appareil).
5. Choisissez un modèle et démarrez un chat, la vision, la génération d’images ou les workflows vocaux.

### Intégrations Android disponibles

- Intégration Assistant (`ASSIST` intent)
- Intégration de la feuille de partage (`SEND` et `SEND_MULTIPLE` intents)
- Intégration de traitement de texte (`PROCESS_TEXT`)
- Liens profonds pour `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Configuration

### Endpoints API et fournisseurs

- Ouvrez **Settings** dans l’application.
- Choisissez **API endpoint** pour basculer entre les fournisseurs préconfigurés.
- Ajoutez un endpoint personnalisé si votre fournisseur est compatible avec OpenAI.

### Paramètres de modèle et de génération

SpeakGPT prend en charge le réglage à l’exécution de paramètres de génération tels que :

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Données locales et sécurité

- Les conversations sont stockées localement et peuvent être importées/exportées.
- Les valeurs sensibles, comme les clés API, sont gérées dans des préférences chiffrées.

### Notes et hypothèses

- `google-services.json` est présent dans ce dépôt ; si vous le supprimez en créant un fork, certaines intégrations peuvent nécessiter votre propre configuration.
- La compatibilité d’un fournisseur peut varier selon l’implémentation de l’endpoint et la famille de modèles.

## Exemples

### Exemple 1 : Générer l’APK de release

```bash
./gradlew assembleRelease
```

### Exemple 2 : Rebuild propre

```bash
./gradlew clean assembleDebug
```

### Exemple 3 : Utiliser OpenRouter pour des modèles de la famille Gemini

1. Créez une clé API OpenRouter.
2. Dans les paramètres de SpeakGPT, sélectionnez/ajoutez l’endpoint OpenRouter.
3. Choisissez un modèle OpenRouter capable de Gemini.
4. Lancez une discussion et vérifiez la génération de réponses.

## Notes de développement

- Il s’agit d’un projet Android multi-modules (`:app`, `:teslasoft-id`).
- Les types de build `debug` et `release` ont tous deux `minifyEnabled true` et `shrinkResources true` dans la configuration actuelle.
- Les règles ProGuard/R8 se trouvent dans :
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- La documentation web embarquée se trouve ici :
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Les ressources de localisation sont dans `app/src/main/res/values-*`.
- Le répertoire de sortie i18n des README est présent dans `i18n/` (les fichiers README spécifiques à chaque langue sont générés séparément dans les étapes du pipeline).

## Dépannage

| Problème | Vérifications |
|---|---|
| "Clé API incorrecte" ou erreurs d’authentification | Vérifiez que votre clé est valide pour le fournisseur sélectionné, que le modèle choisi est disponible sur votre compte, et si le modèle principal nécessite une vérification d’identité supplémentaire. |
| Inadéquation endpoint/modèle | Si vous utilisez un endpoint personnalisé, assurez-vous d’un format de requête/réponse compatible OpenAI. Essayez de changer le preset d’endpoint dans les paramètres puis retestez. |
| Problèmes de build | Vérifiez que JDK 21 est actif, resynchronisez le projet Gradle dans Android Studio, lancez `./gradlew --version` pour confirmer le wrapper Gradle `8.13`, puis relancez `./gradlew clean build`. |
| Problèmes d’exécution sur d’anciennes versions Android | Le projet prend actuellement en charge `minSdk 28` (Android 9). Il est indiqué qu’un support d’Android 9/10/11 peut être supprimé prochainement en raison des évolutions du SDK et de la sécurité. |

## Feuille de route

### ❌ Prévu (partagez vos idées dans les Issues)

- [ ] Routines appareil (définir une alarme ou ouvrir une application)
- [ ] Synchronisation de l’historique des discussions
- [ ] Ajouter un portail d’échange de modèles comme une bibliothèque de prompts
- [ ] Capacités de navigation web officielles (permettre aux modèles GPT d’accéder à Internet)

## Sécurité des clés API

SpeakGPT utilise l’API OpenAI pour offrir la meilleure expérience possible. Utiliser des clés API est plus sûr que d’utiliser un nom d’utilisateur/mot de passe. Vos informations personnelles ne peuvent pas être récupérées via la clé API. OpenAI propose un accès API bon marché à ses services. Votre clé API est stockée localement sur votre appareil et n’est partagée avec personne. SpeakGPT ne collecte aucune donnée personnelle. SpeakGPT est open-source et vous pouvez vérifier le code vous-même. Chaque version de SpeakGPT est vérifiée sur VirusTotal.
Si vous avez des inquiétudes, vous pouvez [révoquer votre clé API](https://platform.openai.com/account/api-keys) ou utiliser une clé API distincte pour SpeakGPT.

Pour sécuriser votre clé API, suivez ces étapes :

1. Créez une clé API dédiée à SpeakGPT.
2. Configurez une limite de facturation.
3. Activez la surveillance d’usage pour voir combien de ressources SpeakGPT consomme et le coût associé.
4. Si vous avez des doutes, révoquez votre clé API.

> Pourquoi obfusquons-nous notre code dans les versions de production ?
>
> L’obfuscation et la réduction des ressources nous permettent d’optimiser la taille de l’application, ses performances et de la sécuriser contre le reverse engineering ou la falsification, tout en garantissant que vos identifiants, comme les clés API, restent en lieu sûr. Vous pouvez demander une version non-obfusquée ou la compiler vous-même pour vérifier la sécurité de l’application.

> [!CAUTION]
>
> MÉFIEZ-VOUS des logiciels malveillants ! Vous êtes autorisé à compiler SpeakGPT et à le modifier, mais soyez extrêmement prudent lorsqu’une personne tierce vous propose d’installer sa propre build. Une telle build peut contenir des malwares. Les builds officielles ne contiennent aucun malware et sont vérifiées par plus de 60 antivirus différents via VirusTotal. Vous pouvez consulter le rapport VirusTotal de chaque page de release et comparer le hash des fichiers binaires.

## Identité du développeur

| Champ | Valeur |
|---|---|
| Nom du développeur | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Adresse légale | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| Identifiant juridique | 55545386 (D-U-N-S: 933739642) |
| Licence d’activité commerciale | OU-KE-OZP1-2023/031005-2 (délivrée le 14 juin 2023 selon l’article 10 paragraphe 1 lettre a) de la loi n°455/1991 sur la licence commerciale (Loi sur la licence commerciale), dans sa version modifiée) |
| Numéro de TVA | SK3121636045 |

(Vous saurez ainsi vers qui vous envoyez vos fonds si vous choisissez de soutenir financièrement le projet ou si celui-ci propose des fonctions payantes à l’avenir.)

## Contribution

Les contributions sont les bienvenues.

- Signalez les bugs dans les Issues avec des étapes de reproduction.
- Proposez de nouvelles fonctionnalités (merci d’utiliser des tags/labels explicites).
- Si vous soumettez du code, limitez la portée des changements et incluez votre justification.

## ❤️ Support

| Donate | PayPal | Stripe |
|---|---|---|
| [![Donate](https://img.shields.io/badge/Donate-LazyingArt-0EA5E9?style=for-the-badge&logo=ko-fi&logoColor=white)](https://chat.lazying.art/donate) | [![PayPal](https://img.shields.io/badge/PayPal-RongzhouChen-00457C?style=for-the-badge&logo=paypal&logoColor=white)](https://paypal.me/RongzhouChen) | [![Stripe](https://img.shields.io/badge/Stripe-Donate-635BFF?style=for-the-badge&logo=stripe&logoColor=white)](https://buy.stripe.com/aFadR8gIaflgfQV6T4fw400) |

### Vous êtes encouragé(e) à

- Signaler tout bug
- Me soutenir :) 
- Demander de nouvelles fonctionnalités. N’oubliez pas de marquer le ticket avec un label

### Offrez-moi un café

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

## Licence

Ce projet est sous licence Apache 2.0. Voir [LICENSE.md](LICENSE.md).

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
