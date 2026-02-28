[English](../README.md) · [العربية](README.ar.md) · [Español](README.es.md) · [Français](README.fr.md) · [日本語](README.ja.md) · [한국어](README.ko.md) · [Tiếng Việt](README.vi.md) · [中文 (简体)](README.zh-Hans.md) · [中文（繁體）](README.zh-Hant.md) · [Deutsch](README.de.md) · [Русский](README.ru.md)


[![LazyingArt banner](https://github.com/lachlanchen/lachlanchen/raw/main/figs/banner.png)](https://github.com/lachlanchen/lachlanchen/blob/main/figs/banner.png)

# SpeakGPT

> Assistant IA open source conçu pour Android, avec des flux de chat, voix, vision et génération d’images.

[![Plateforme](https://img.shields.io/badge/Platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white)](#faits-rapides)
[![Min SDK](https://img.shields.io/badge/minSdk-28-2563EB?style=flat-square)](#prérequis)
[![Target SDK](https://img.shields.io/badge/targetSdk-36-2563EB?style=flat-square)](#prérequis)
[![License](https://img.shields.io/badge/License-Apache%202.0-F59E0B?style=flat-square&style=flat-square)](#licence)
[![Gradle](https://img.shields.io/badge/Gradle-8.13-02303A?style=flat-square&logo=gradle&logoColor=white)](#prérequis)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.2.10-7F52FF?style=flat-square&logo=kotlin&logoColor=white)](#prérequis)
[![AGP](https://img.shields.io/badge/AGP-8.12.2-34A853?style=flat-square&logo=android&logoColor=white)](#prérequis)
[![Google Play](https://img.shields.io/badge/Google%20Play-Install-0F9D58?style=flat-square&logo=google-play&logoColor=white)](https://play.google.com/store/apps/details?id=org.teslasoft.assistant)
[![Web Companion](https://img.shields.io/badge/Web-assistant.teslasoft.org-0EA5E9?style=flat-square&logo=googlechrome&logoColor=white)](https://assistant.teslasoft.org/)
[![Translations](https://img.shields.io/badge/Translations-11-2563EB?style=flat-square&logo=googletranslate&logoColor=white)](#table-des-matières)
[![Contributions](https://img.shields.io/badge/Contributions-Welcome-10B981?style=flat-square&logo=github&logoColor=white)](#contribution)
[![Support](https://img.shields.io/badge/Support-Open%20in%202%20clicks-EC4899?style=flat-square&logo=ko-fi&logoColor=white)](#-support)

| ✅ Contenu | 🔗 Lien |
|---|---|
| Installer l’application Android | [Google Play](https://play.google.com/store/apps/details?id=org.teslasoft.assistant) |
| Utiliser le compagnon web | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |
| Voir les tickets | [GitHub Issues](https://github.com/AndraxDev/speak-gpt/issues) |
| Consulter les traductions | [i18n/](i18n/) |

---

SpeakGPT est un assistant IA open source avancé et intuitif pour Android. Il unifie plusieurs expériences multimodales (chat, voix, génération d’images et vision) dans une seule application avec des fournisseurs compatibles OpenAI.

Officiellement, il prend en charge les modèles GPT, LLAMA, MIXTRAL, GEMMA, Gemini (standard et pro) Vision, DALL-E et d’autres familles.

## Faits rapides

| Informations | Détails |
|---|---|
| 📱 Plateforme | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Utilisation principale | Bring-your-own-endpoint + bring-your-own-key |
| 🧩 Type d’application | Client IA open source (pas fournisseur d’API) |
| 🌐 Compagnon web | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
> 
> Ce projet fait partie de mon mémoire de licence. L’attribution est obligatoire pour utiliser ce travail. Copyright (c) 2023-2025 Dmytro Ostapenko. Tous droits réservés.
> 
> À citer ainsi : Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
> 
> Le support des versions Android 9, 10 et 11 est prévu pour être supprimé, en raison des changements du SDK et de la sécurité. Les versions Android plus anciennes reposent sur des API dépréciées telles que RenderScript.

## Table des matières

- [Téléchargement](#téléchargement)
- [SpeakGPT Web](#speakgpt-web)
- [Aperçu](#aperçu)
- [Captures d’écran](#captures-décran)
- [Informations pour les utilisateurs qui souhaitent utiliser Google Gemini avec cette application](#informations-pour-les-utilisateurs-qui-souhaitent-utiliser-google-gemini-avec-cette-application)
- [Pour les personnes voulant quelque chose gratuitement avec peu ou pas d’effort](#pour-les-personnes-voulant-quelque-chose-gratuitement-avec-peu-ou-pas-d%E2%80%99effort)
- [Fournisseurs d’API pris en charge](#fournisseurs-dapi-prise-en-charge)
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

📦 Installez depuis Google Play :

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Lancez SpeakGPT Web : [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

Dépôt GitHub : [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Aperçu

SpeakGPT repose sur un workflow flexible de fournisseur pour les utilisateurs voulant contrôler directement leur pile API.

### En bref

| Domaine | Résumé |
|---|---|
| 💬 Expériences principales | Chat, génération d’images, reconnaissance d’images, saisie vocale, intégrations d’assistant |
| 🔌 Stratégie fournisseur | Endpoints compatibles OpenAI avec fournisseurs configurables et endpoints personnalisés |
| 🔐 Gestion des données | Clés API stockées localement ; conversations pouvant être importées/exportées |
| 🧱 Stack de build | Projet Android multi-module utilisant AGP `8.12.2`, Gradle `8.13`, Kotlin `2.2.10` |

Architecture du dépôt :

- `app` : module application Android (`org.teslasoft.assistant`)
- `teslasoft-id` : module de bibliothèque Android interne pour l’authentification/utilitaires client (`org.teslasoft.core.auth`)
- Métadonnées JSON à la racine du dépôt (`ai_sets.json`, `explore.json`, `experiment.json`) utilisées pour les sets de modèles, la découverte et les métadonnées de flux de travail
- `i18n/` : répertoire de documentation multilingue

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

SpeakGPT ne prend pas directement en charge les clés API Google, mais vous pouvez utiliser Gemini via OpenRouter.

Plus d’infos : [OpenRouter Models](https://openrouter.ai/docs#models)

## Pour les personnes voulant quelque chose gratuitement avec peu ou pas d’effort

> [!WARNING]
> 
> Les fonctionnalités gratuites sont souvent limitées. Cette application est open source et fournie en l’état. Elle ne fournit pas un accès premium gratuit complet aux services phares des API tierces.
> 
> Si vous recherchez un accès totalement gratuit sans effort, il est préférable d’utiliser un autre produit. Les questions du type « clé API incorrecte » sont généralement résolues en vérifiant votre endpoint et la configuration du modèle. Merci de votre compréhension.
> 
> Tous les utilisateurs légitimes sont les bienvenus.

## Fournisseurs d’API pris en charge

| Fournisseur | Niveau de support | Remarques |
|---|---|---|
| OpenAI | Support complet | Chemin d’intégration principal |
| GROQ | Support partiel | Certaines fonctionnalités peuvent varier |
| Azure | Support partiel | Endpoint/modèle peut différer |
| OpenRouter | Génération de texte uniquement | Testé avec Gemini, Claude, Perplexity, Llama, Gemma, Mistral, modèles OpenAI |
| Autre | Testé par la communauté | Les retours sont bienvenus |

> [!NOTE]
> 
> Pour changer de fournisseur, ouvrez les paramètres de l’application et sélectionnez un endpoint API. Vous pouvez aussi ajouter un endpoint OpenAI-compatible personnalisé.

## Fonctionnalités de base

✅ Fonctionnalités implémentées :

- [x] Chat (sauvegardé localement, import/export supportés)
- [x] Génération d’images
- [x] Reconnaissance d’images (attacher des images/photos dans le chat)
- [x] Workflows de prompt d’activation et message système
- [x] Entrée vocale (Whisper et Google)
- [x] Intégration d’assistant
- [x] SpeakGPT dans le menu contextuel
- [x] SpeakGPT dans la feuille de partage
- [x] Fonctionnalités d’appel de fonctions
- [x] Bibliothèque de prompts
- [x] Disposition de chat multiple
- [x] Design adaptatif
- [x] Couverture large des modèles
- [x] Sans captcha
- [x] Modèle usage à la carte
- [x] Aide de démarrage pour nouveaux utilisateurs
- [x] Support des modèles fine-tunés/personnalisés
- [x] Mode sombre AMOLED
- [x] Support de fournisseur d’API personnalisé
- [x] Personnalisation des paramètres du modèle (`temperature`, `topP`, `frequencyPenalty`, `presencePenalty`, `logit_bias`)
- [x] Playground
- [x] Accès aux familles récentes telles que o1, o3, o4, gpt-4.1, gpt-4.5, gpt-image-1

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

- Android Studio (stable actuel recommandé)
- Android SDK avec `compileSdk 36`
- JDK 21 (`sourceCompatibility`/`targetCompatibility` alignés sur Java 21 dans la configuration du projet)
- Git
- Accès Internet pour les dépendances Gradle et les API des fournisseurs

Faits de build du dépôt :

| Composant | Version / Valeur |
|---|---|
| Plugin Android Gradle | `8.12.2` |
| Plugin Kotlin | `2.2.10` |
| Gradle wrapper | `8.13` |
| ID du package | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Ouvrir dans Android Studio

- Ouvrez `build.gradle` dans Android Studio.
- Laissez la synchronisation Gradle se terminer.

### 3. Générer l’APK debug

```bash
./gradlew assembleDebug
```

### 4. Installer sur un appareil ou émulateur connecté

```bash
./gradlew installDebug
```

### 5. Vérification qualité optionnelle

```bash
./gradlew lint
```

## Utilisation

### Flux utilisateur (dans l’application)

1. Installez l’application depuis Google Play ou une build debug locale.
2. Complétez le flux d’onboarding.
3. Ouvrez les paramètres API et choisissez un fournisseur/endpoint.
4. Ajoutez une clé API valide (stockée localement sur l’appareil).
5. Sélectionnez un modèle et démarrez un chat, la vision, la génération d’images ou la voix.

### Intégrations Android disponibles

- Intégration assistant (`ASSIST` intent)
- Intégration feuille de partage (`SEND`, `SEND_MULTIPLE` intents)
- Intégration de traitement de texte (`PROCESS_TEXT`)
- Liens profonds pour `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Configuration

### Endpoints API et fournisseurs

- Ouvrez **Settings** dans l’application.
- Choisissez **API endpoint** pour basculer entre les fournisseurs intégrés.
- Ajoutez un endpoint personnalisé si votre fournisseur est compatible OpenAI.

### Paramètres de modèle et de génération

SpeakGPT prend en charge l’ajustement dynamique de :

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Données locales et sécurité

- Les conversations sont stockées localement et peuvent être importées/exportées.
- Les valeurs sensibles comme les clés API sont gérées via des préférences chiffrées.

### Remarques et hypothèses

- `google-services.json` existe dans ce dépôt pour les builds actuelles ; s’il est supprimé dans des forks, certaines intégrations peuvent nécessiter une configuration Firebase/Service équivalente.
- Le comportement des fournisseurs peut différer selon l’endpoint et la famille de modèles.

## Exemples

### Générer une APK de release

```bash
./gradlew assembleRelease
```

### Rebuild propre

```bash
./gradlew clean assembleDebug
```

### Utiliser OpenRouter pour les modèles de la famille Gemini

1. Créez une clé API OpenRouter.
2. Dans les paramètres SpeakGPT, sélectionnez/ajoutez l’endpoint OpenRouter.
3. Choisissez un modèle compatible Gemini.
4. Lancez un chat et vérifiez les réponses.

### Faire un build complet propre

```bash
./gradlew clean build
```

## Notes de développement

- Il s’agit d’un projet Android multi-module (`:app`, `:teslasoft-id`).
- Les types de build `debug` et `release` utilisent tous deux `minifyEnabled true` et `shrinkResources true` dans la configuration actuelle.
- Les règles ProGuard/R8 se trouvent dans :
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- La documentation web embarquée se trouve dans :
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Les ressources localisées se trouvent dans `app/src/main/res/values-*`.
- Les traductions du README résident dans `i18n/` pour les variantes linguistiques.

## Dépannage

| Problème | Vérification |
|---|---|
| Clé API incorrecte / erreur d’authentification | Vérifiez la validité de la clé, la compatibilité du fournisseur et la disponibilité du modèle. Certains modèles phares exigent une vérification de compte supplémentaire. |
| Endpoint ou modèle incorrect | Vérifiez que votre endpoint personnalisé respecte les formats de requête/réponse compatibles OpenAI. Essayez de changer le pré-réglage d’endpoint dans Paramètres et relancez. |
| Erreurs de build | Vérifiez que JDK 21 est actif, synchronisez Gradle, et validez que le wrapper est `8.13` via `./gradlew --version`, puis exécutez `./gradlew clean build`. |
| Problèmes runtime sur anciens Android | Le projet est à `minSdk 28`. Les avertissements de dépréciation pour Android 9/10/11 sont attendus au fil de l’évolution de la politique de support. |

## Feuille de route

### ❌ Ajouts prévus

- [ ] Routines appareil (définir une alarme ou ouvrir une app)
- [ ] Synchroniser l’historique de chat
- [ ] Portail d’échange de prompts / flux de style marketplace
- [ ] Navigation et outils officiels pour les flux d’accès Internet

## Sécurité des clés API

SpeakGPT utilise des clés API pour les demandes aux fournisseurs, afin que les identifiants soient plus cadrés et plus sûrs que des flux compte/mot de passe.

- Votre clé API est stockée localement et n’est pas partagée par l’application.
- Vous pouvez révoquer vos clés à tout moment depuis la console de votre fournisseur.
- Si vous le souhaitez, utilisez une clé dédiée à SpeakGPT.

Rappels de sécurité :

1. Gardez une clé API séparée pour SpeakGPT.
2. Configurez des limites de facturation.
3. Activez la surveillance d’usage pour contrôler les coûts.
4. Révoquez les clés dès qu’une utilisation suspecte apparaît.

Pourquoi les versions de l’application sont obfusquées :

L’obfuscation et la réduction des ressources améliorent la taille des paquets, les performances et réduisent le risque de reverse engineering lié à la gestion des identifiants. Vous pouvez demander un build non obfusqué ou compiler vous-même.

> [!CAUTION]
> 
> N’installez pas de builds provenant de sources non fiables. Des builds tiers peuvent être modifiés pour injecter des logiciels malveillants. Les builds officiels sont vérifiés par VirusTotal et publiés via les canaux officiels.

## Identité du développeur

| Champ | Valeur |
|---|---|
| Nom du développeur | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Adresse légale | Južná trieda 4B, 04001 Košice, Slovakia |
| ID entité juridique | 55545386 (D-U-N-S: 933739642) |
| Licence d’activité commerciale | OU-KE-OZP1-2023/031005-2 (délivrée le 14 juin 2023 selon § 10(1)(a) de l’Acte n°455/1991 sur la licence commerciale, tel que modifié) |
| Numéro TVA | SK3121636045 |

(Si vous choisissez de soutenir financièrement le projet, ou si des fonctionnalités payantes apparaissent à l’avenir, c’est vers ce contact.)

## Contribution

Les contributions sont les bienvenues.

- Signaler des bugs dans Issues avec les étapes de reproduction.
- Proposer de nouvelles fonctionnalités avec un titre clair et du contexte.
- Garder les PR ciblées et inclure justification et notes de vérification.

## Licence

Ce projet est sous licence Apache License 2.0. Voir [LICENSE.md](LICENSE.md).

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
