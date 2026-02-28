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

SpeakGPT est un assistant IA open-source avancé et très intuitif pour Android. Il intègre des fournisseurs modernes de grands modèles de langage (LLM) et des workflows multimodaux (chat, voix, génération d’images, vision) dans une seule application mobile.

Il prend officiellement en charge les modèles GPT, LLAMA, MIXTRAL, GEMMA, Gemini (standard et pro) Vision, DALL-E et d’autres modèles.

| Infos rapides | Détails |
|---|---|
| 📱 Plateforme | Android (`minSdk 28`, `targetSdk 36`) |
| 🧠 Utilisation principale | Apportez votre propre endpoint + votre propre clé |
| 🧩 Type d’application | Client IA open-source (pas un fournisseur d’API) |
| 🌐 Compagnon web | [assistant.teslasoft.org](https://assistant.teslasoft.org/) |

> [!NOTE]
>
> Ce projet fait partie de mon mémoire de licence. L’attribution est requise pour utiliser ce travail. Copyright (c) 2023-2025 Dmytro Ostapenko. Tous droits réservés.
>
> Citer comme suit : Dmytro Ostapenko (2024), "Review Program Automation Using Copilot Services" Bachelor Thesis, Technical University of Košice, 2024.

> [!CAUTION]
>
> Nous abandonnerons bientôt la prise en charge des versions Android suivantes : 9, 10, 11. Cela est lié aux changements récents du SDK et de la sécurité. Les anciennes versions d’Android utilisent des fonctionnalités obsolètes et instables comme RenderScript.

## Table des matières

- [Téléchargement](#téléchargement)
- [SpeakGPT Web](#speakgpt-web)
- [Vue d’ensemble](#vue-densemble)
- [Captures d’écran](#captures-décran)
- [Informations pour les utilisateurs qui veulent utiliser les modèles Google Gemini avec cette application](#informations-pour-les-utilisateurs-qui-veulent-utiliser-les-modèles-google-gemini-avec-cette-application)
- [Pour les personnes pas très futées qui veulent utiliser quelque chose gratuitement avec peu ou pas d’effort](#pour-les-personnes-pas-très-futées-qui-veulent-utiliser-quelque-chose-gratuitement-avec-peu-ou-pas-deffort)
- [Fournisseurs d’API pris en charge](#fournisseurs-dapi-pris-en-charge)
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
- [Contribuer](#contribuer)
- [Support](#support)
- [Offrez-moi un café](#offrez-moi-un-café)
- [Licence](#licence)

## Téléchargement

📦 Installer depuis Google Play :

<a href="https://play.google.com/store/apps/details?id=org.teslasoft.assistant"><img src="play.webp" alt="Get it on Play" width="200"/></a>

## SpeakGPT Web

🌍 Lancez SpeakGPT Web : [https://assistant.teslasoft.org/](https://assistant.teslasoft.org/)

Dépôt GitHub : [https://github.com/AndraxDev/speak-gpt-web](https://github.com/AndraxDev/speak-gpt-web)

## Vue d’ensemble

SpeakGPT est un client Android-first pour les API d’IA. Il est conçu autour de l’approche apportez votre propre endpoint et apportez votre propre clé, afin que les utilisateurs puissent choisir le fournisseur, le modèle, et le profil coût/performance.

Architecture du dépôt :

- `app` : module application Android (`org.teslasoft.assistant`)
- `teslasoft-id` : module bibliothèque Android interne pour les utilitaires d’auth/client (`org.teslasoft.core.auth`)
- Métadonnées JSON à la racine du dépôt (`ai_sets.json`, `explore.json`, `experiment.json`) utilisées pour les ensembles de modèles, la découverte et les workflows de style import/export
- `i18n/` : répertoire de sortie README multilingue (présent dans le dépôt)

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

## Informations pour les utilisateurs qui veulent utiliser les modèles Google Gemini avec cette application

SpeakGPT ne prend pas directement en charge les clés API Google, mais vous pouvez quand même utiliser Google Gemini via l’API OpenRouter.

Plus d’infos : [OpenRouter Models](https://openrouter.ai/docs#models)

## Pour les personnes pas très futées qui veulent utiliser quelque chose gratuitement avec peu ou pas d’effort

> [!WARNING]
>
> N’oubliez pas que le fromage gratuit n’existe que dans un piège à souris. CETTE APPLICATION EST UN CLIENT OPEN-SOURCE FOURNI EN L’ÉTAT. À ELLE SEULE, ELLE N’OFFRE PAS D’ACCÈS ENTIÈREMENT GRATUIT AUX FONCTIONNALITÉS PREMIUM DES FOURNISSEURS D’API (COMME LES MODÈLES IA PHARES ET LES FONCTIONNALITÉS SPÉCIALES). SI VOUS VENEZ ICI POUR UTILISER LE TRAVAIL DES AUTRES GRATUITEMENT ET SANS CRÉDIT, IL VAUT MIEUX PASSER VOTRE CHEMIN ET CHERCHER AUTRE CHOSE. JE NE RÉPONDRAI PAS AUX QUESTIONS DU TYPE « CLÉ API INCORRECTE, POURQUOI CETTE APPLICATION ME REDIRIGE VERS UN SITE EXTERNE POUR LA CLÉ API ? ». MERCI DE VOTRE COMPRÉHENSION.
> Toutes les autres personnes raisonnables sont les bienvenues.

## Fournisseurs d’API pris en charge

| Fournisseur | Niveau de prise en charge | Notes |
|---|---|---|
| OpenAI | Prise en charge complète | Voie d’intégration principale |
| GROQ | Prise en charge partielle | Certaines fonctionnalités peuvent varier |
| Azure | Prise en charge partielle | Les spécificités endpoint/modèle peuvent différer |
| OpenRouter | Génération de texte uniquement | Testé avec les modèles Gemini, Claude, Perplexity, Llama, Gemma, Mistral, OpenAI |
| Other | Testé par la communauté | Les retours sont les bienvenus |

> [!NOTE]
>
> Pour changer de fournisseur d’API, allez dans les paramètres et sélectionnez l’endpoint API. Vous pouvez aussi ajouter votre propre fournisseur d’API personnalisé.

## Fonctionnalités de base

✅ Capacités implémentées :

- [x] Chat (enregistré localement mais peut être importé/exporté si nécessaire)
- [x] Génération d’images
- [x] Reconnaissance d’images (utilisez vos images et photos avec ChatGPT)
- [x] Prompt d’activation
- [x] Message système
- [x] Saisie vocale (Whisper et Google)
- [x] Assistant
- [x] SpeakGPT dans le menu contextuel
- [x] SpeakGPT dans la feuille de partage
- [x] Fonctionnalités d’appel de fonctions
- [x] Bibliothèque de prompts
- [x] Différentes dispositions de chat
- [x] Design adaptatif
- [x] Beaucoup de modèles différents
- [x] Pas de captcha
- [x] Système pay-as-you-go
- [x] Conseils pour débutants
- [x] Les modèles personnalisés fine-tuned sont pris en charge
- [x] Mode sombre AMOLED
- [x] Prise en charge de fournisseur d’API personnalisé
- [x] Personnalisation de paramètres de modèle comme `temperature`, `topP`, `frequencyPenalty`, `presencePenalty` et `logit_bias`
- [x] Playground
- [x] Accès aux derniers modèles phares comme o1, o3, o4, gpt-4.1, gpt-4.5 et gpt-image-1 (Certains de ces modèles peuvent vous demander de vérifier votre identité auprès d’OpenAI)

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

Informations du système de build à partir de la configuration du dépôt :

| Composant | Version / Valeur |
|---|---|
| Android Gradle Plugin | `8.12.2` |
| Kotlin plugin | `2.2.10` |
| Gradle wrapper | `8.13` |
| App package id | `org.teslasoft.assistant` |
| Min SDK | `28` |
| Target SDK | `36` |

## Installation

### 1. Cloner le dépôt

```bash
git clone https://github.com/AndraxDev/speak-gpt.git
cd speak-gpt
```

### 2. Compiler l’APK debug

```bash
./gradlew assembleDebug
```

### 3. Installer sur un appareil/émulateur connecté

```bash
./gradlew installDebug
```

### 4. Vérifications qualité optionnelles

```bash
./gradlew lint
```

## Utilisation

### Flux utilisateur final (dans l’application)

1. Installez l’application depuis Google Play ou via un build debug local.
2. Terminez le flux d’onboarding.
3. Ouvrez les paramètres API et sélectionnez ou ajoutez votre endpoint/fournisseur.
4. Saisissez votre clé API (stockée localement sur votre appareil).
5. Sélectionnez un modèle et démarrez un workflow de chat, vision, génération d’images ou voix.

### Intégrations Android disponibles

- Intégration Assistant (`ASSIST` intent)
- Intégration feuille de partage (`SEND` et `SEND_MULTIPLE` intents)
- Intégration de traitement de texte (`PROCESS_TEXT`)
- Liens profonds pour `assistant.teslasoft.org` (`/chat`, `/prompts`, `/assistant`)

## Configuration

### Endpoints API et fournisseurs

- Ouvrez **Settings** dans l’application.
- Choisissez **API endpoint** pour basculer entre les fournisseurs préconfigurés.
- Ajoutez un endpoint personnalisé si votre fournisseur est compatible OpenAI.

### Paramètres de modèle et de génération

SpeakGPT prend en charge l’ajustement à l’exécution des paramètres de génération tels que :

- `temperature`
- `topP`
- `frequencyPenalty`
- `presencePenalty`
- `logit_bias`

### Données locales et sécurité

- Les conversations sont stockées localement et peuvent être importées/exportées.
- Les valeurs sensibles comme les clés API sont gérées dans des préférences chiffrées.

### Notes et hypothèses

- `google-services.json` est présent dans ce dépôt ; si vous faites un fork et le supprimez, certaines intégrations peuvent nécessiter votre propre configuration.
- La compatibilité fournisseur peut varier selon l’implémentation de l’endpoint et la famille de modèles.

## Exemples

### Exemple 1 : Compiler l’APK release

```bash
./gradlew assembleRelease
```

### Exemple 2 : Rebuild propre

```bash
./gradlew clean assembleDebug
```

### Exemple 3 : Utiliser OpenRouter pour des modèles de la famille Gemini

1. Créez une clé API OpenRouter.
2. Dans les paramètres SpeakGPT, sélectionnez/ajoutez l’endpoint OpenRouter.
3. Choisissez un modèle OpenRouter compatible Gemini.
4. Démarrez un chat et vérifiez la génération de réponse.

## Notes de développement

- Il s’agit d’un projet Android multi-modules (`:app`, `:teslasoft-id`).
- Les types de build `debug` et `release` ont tous deux `minifyEnabled true` et `shrinkResources true` dans la configuration actuelle.
- Les règles ProGuard/R8 se trouvent dans :
  - `app/proguard-rules.pro`
  - `teslasoft-id/proguard-rules.pro`
- La documentation web embarquée se trouve dans :
  - `app/src/main/assets/www/api.html`
  - `app/src/main/assets/www/api_light.html`
  - `app/src/main/assets/www/privacy.html`
  - `app/src/main/assets/www/privacy_light.html`
- Les ressources de localisation se trouvent dans `app/src/main/res/values-*`.
- Le répertoire de sortie README i18n existe dans `i18n/` (les README spécifiques aux langues sont générés séparément lors des étapes du pipeline).

## Dépannage

| Problème | Vérifications |
|---|---|
| "Incorrect API key" ou échecs d’authentification | Vérifiez que votre clé est valide pour le fournisseur sélectionné, que le modèle sélectionné est disponible pour votre compte, et si le fournisseur exige une vérification supplémentaire pour les modèles phares. |
| Incompatibilité endpoint/modèle | Si vous utilisez un endpoint de fournisseur personnalisé, assurez-vous du format de requête/réponse compatible OpenAI. Essayez de changer de preset d’endpoint dans les paramètres puis retestez. |
| Problèmes de build | Confirmez que JDK 21 est actif, synchronisez le projet Gradle dans Android Studio, exécutez `./gradlew --version` et vérifiez que le wrapper utilise Gradle `8.13`, puis réessayez avec `./gradlew clean build`. |
| Problèmes d’exécution sur d’anciennes versions Android | Le projet prend actuellement en charge `minSdk 28` (Android 9). Le projet avertit que la prise en charge d’Android 9/10/11 pourrait être abandonnée à l’avenir en raison de changements SDK/sécurité. |

## Feuille de route

### ❌ Prévu à l’ajout (Partagez vos idées dans les Issues)

- [ ] Routines appareil (comme définir une alarme ou ouvrir une application)
- [ ] Synchroniser l’historique des chats
- [ ] Ajouter un portail d’échange de modèles comme un store de prompts
- [ ] Capacités officielles de navigation (permettre aux modèles IA GPT d’accéder à Internet)

## Sécurité des clés API

SpeakGPT utilise l’API OpenAI pour vous offrir la meilleure expérience. Utiliser des clés API est plus sûr que d’utiliser votre nom d’utilisateur/mot de passe. Vos informations personnelles ne peuvent pas être obtenues avec une clé API. OpenAI fournit un accès API économique à ses services. Votre clé API est stockée localement sur votre appareil et n’est partagée avec personne. SpeakGPT ne collecte aucune donnée personnelle. SpeakGPT est open-source et vous pouvez vérifier le code vous-même. Chaque version de SpeakGPT est vérifiée sur VirusTotal.
Si vous avez des inquiétudes, vous pouvez soit [révoquer votre clé API](https://platform.openai.com/account/api-keys), soit utiliser une clé API séparée pour SpeakGPT.

Pour sécuriser votre clé API, effectuez les étapes suivantes :

1. Assurez-vous d’avoir une clé API séparée pour SpeakGPT.
2. Définissez une limite de facturation.
3. Activez le suivi d’utilisation, afin de voir combien de ressources SpeakGPT utilise et combien cela coûte.
4. Si vous avez des inquiétudes, vous pouvez révoquer votre clé API.

> Pourquoi obfusquons-nous notre code dans les versions de production ?
>
> L’obfuscation et la réduction des ressources nous permettent d’optimiser la taille de l’application, ses performances, de la sécuriser contre la rétro-ingénierie ou l’altération, et de nous assurer que vos identifiants comme les clés API restent en sécurité. Vous pouvez demander un build non obfusqué ou le compiler vous-même pour vérifier que notre application est sûre.

> [!CAUTION]
>
> ATTENTION AUX MALWARES ! Vous êtes autorisé à compiler SpeakGPT et à le modifier, mais soyez très prudent si quelqu’un d’autre vous propose d’installer son build. Un tel build peut contenir des malwares. Les builds officiels ne contiennent aucun malware et sont vérifiés par plus de 60 antivirus différents via VirusTotal. Vous pouvez trouver le rapport VirusTotal sur chaque page de release et comparer le hash des fichiers binaires.

## Identité du développeur

| Champ | Valeur |
|---|---|
| Nom du développeur | Dmytro Ostapenko (AndraxDev) |
| Contact | dostapenko82@gmail.com, +421951829517 |
| Adresse légale | Južná trieda 4B, 04001 Košice, Slovakia 04001 |
| ID entité légale | 55545386 (D-U-N-S: 933739642) |
| Licence d’activité commerciale | OU-KE-OZP1-2023/031005-2 (Délivrée le 14 June 2023 according to the § 10 section 1 letter a) of the Act No. 455/1991 Coll. on Trade Licensing (Trade Licensing Act) as amended) |
| Numéro de TVA | SK3121636045 |

(Pour que vous sachiez à qui vous envoyez votre argent si vous décidez de soutenir le projet financièrement ou si le projet comporte des fonctionnalités payantes à l’avenir)

## Contribuer

Les contributions sont les bienvenues.

- Signalez les bugs dans les Issues avec des étapes de reproduction.
- Demandez de nouvelles fonctionnalités (veuillez utiliser des tags/labels d’issue clairs).
- Si vous soumettez du code, gardez des changements ciblés et incluez la justification.

## Support

### Vous êtes invité à

- Signaler tout bug
- Me soutenir :)
- Demander de nouvelles fonctionnalités. N’oubliez pas de marquer l’issue avec un tag

## Offrez-moi un café

<a href="https://buymeacoffee.com/andrax_dev"><img src="https://andrax.dev/bmc_qr.png" width="200"/></a>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/S6S6X3NCE)

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
