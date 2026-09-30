# MonAppCitationExpo

![React Native](https://img.shields.io/badge/React%20Native-0.79.2-blue.svg)
![Expo](https://img.shields.io/badge/Expo-53.0.9-black.svg)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8.3-blue.svg)
![Expo Router](https://img.shields.io/badge/Expo%20Router-5.0.6-lightgrey.svg)
![Version](https://img.shields.io/badge/Version-1.0.0-green.svg)

## 2. DESCRIPTION DU PROJET

MonAppCitationExpo est une application mobile développée avec Expo et React Native, dédiée à l'affichage aléatoire de citations inspirantes. L'objectif principal est de proposer une expérience utilisateur fluide, minimaliste et esthétique, permettant à l'utilisateur de découvrir une nouvelle citation à chaque interaction.

Cette application met en valeur une approche moderne du développement mobile cross-platform, avec une gestion dynamique des données issues d'une API externe, des animations fluides et un design adaptatif prenant en charge les modes clair et sombre.

## 3. FONCTIONNALITÉS CLÉS

- **Affichage aléatoire de citations** : Récupération automatique d'une citation aléatoire via l'API [Quotable](https://api.quotable.io/).
- **Interface utilisateur moderne** : Design épuré avec fond dégradé dynamique et effets visuels soignés.
- **Animations fluides** : Transitions d'opacité et de translation lors du changement de citation, optimisées avec React Native Reanimated.
- **Thème adaptatif** : Prise en charge native du mode clair et sombre grâce au système de thème d'Expo Router et React Navigation.
- **Navigation par onglets** : Structure à onglets avec routage basé sur les fichiers (File-Based Routing).
- **Expérience cross-platform** : Compatible Android, iOS et Web grâce à Expo.
- **Chargement optimisé des polices** : Gestion du chargement asynchrone des polices personnalisées pour une expérience fluide.

## 4. STACK TECHNIQUE

| Catégorie | Technologies utilisées |
|---|---|
| **Frontend** | [React Native](https://reactnative.dev/) (v0.79.2), [React](https://react.dev/) (v19.0.0), [TypeScript](https://www.typescriptlang.org/) (v5.8.3) |
| **Framework Mobile** | [Expo](https://expo.dev/) (v53.0.9), [Expo Router](https://docs.expo.dev/router/) (v5.0.6) |
| **Navigation** | [React Navigation](https://reactnavigation.org/) (v7.x) - Bottom Tabs |
| **Données & API** | [Axios](https://axios-http.com/) (v1.9.0), [Quotable API](https://api.quotable.io/) |
| **UI & Animations** | [Expo Linear Gradient](https://docs.expo.dev/versions/latest/sdk/linear-gradient/), [React Native Reanimated](https://docs.swmansion.com/react-native-reanimated/), [React Native Gesture Handler](https://docs.swmansion.com/react-native-gesture-handler/), [Expo Blur](https://docs.expo.dev/versions/latest/sdk/blur/) |
| **Thèmes & Styles** | [Expo System UI](https://docs.expo.dev/versions/latest/sdk/system-ui/), [React Native Safe Area Context](https://github.com/th3rdwave/react-native-safe-area-context) |
| **Outils de développement** | [ESLint](https://eslint.org/) (v9.25.0), [eslint-config-expo](https://github.com/expo/eslint-config-expo), [Metro Bundler](https://metrobundler.dev/) |

## 5. ARCHITECTURE DU PROJET

Le projet suit une architecture modulaire basée sur le **File-Based Routing** d'Expo Router, favorisant la scalabilité, la lisibilité et une séparation claire des responsabilités.

```text
MonAppCitationExpo/
├── app/                        # Système de routage (Expo Router)
│   ├── _layout.tsx             # Layout racine (gestion des thèmes, polices, Stack)
│   ├── +not-found.tsx          # Écran 404
│   └── (tabs)/                 # Groupe d'écrans avec navigation par onglets
│       ├── _layout.tsx         # Configuration des onglets (icônes, styles, haptics)
│       ├── index.tsx           # Écran principal - Générateur de citations
│       └── explore.tsx         # Écran d'exploration et documentation template
│
├── components/                 # Composants réutilisables
│   ├── Collapsible.tsx         # Composant accordéon
│   ├── ExternalLink.tsx        # Lien externe optimisé Expo
│   ├── HapticTab.tsx           # Bouton d'onglet avec retour haptique
│   ├── HelloWave.tsx           # Animation de salutation
│   ├── ParallaxScrollView.tsx  # Vue scrollable avec effet parallax
│   ├── ThemedText.tsx          # Composant texte adaptatif (clair/sombre)
│   ├── ThemedView.tsx          # Composant vue adaptatif (clair/sombre)
│   └── ui/                     # Composants d'interface atomiques
│       ├── IconSymbol.tsx      # Système d'icônes unifié
│       └── TabBarBackground.tsx# Arrière-plan dynamique de la barre d'onglets
│
├── constants/                  # Constantes globales
│   └── Colors.ts               # Palette de couleurs pour thèmes clair/sombre
│
├── hooks/                      # Hooks personnalisés React
│   ├── useColorScheme.ts       # Détection du thème système
│   ├── useColorScheme.web.ts   # Gestion du thème spécifique Web
│   └── useThemeColor.ts        # Hook d'accès aux couleurs thématisées
│
├── assets/                     # Ressources statiques (fonts, images, icônes)
├── scripts/                    # Scripts utilitaires (reset-project)
├── android/                    # Code natif Android (build Expo prebuild)
└── .vscode/                    # Configuration de l'environnement de développement
```

**Choix d'organisation :**

- **Architecture basée sur les routes (Expo Router)** : Favorise la co-localisation des écrans et une navigation déclarative, conforme aux bonnes pratiques modernes de React Native.
- **Approche modulaire et atomique** : Séparation claire entre écrans (`app/`), composants UI réutilisables (`components/`), logique métier (hooks) et constantes.
- **Gestion thématique centralisée** : Utilisation des hooks et composants thématisés (`ThemedText`, `ThemedView`) pour garantir une cohérence UI/UX entre modes clair et sombre.
- **Alias de chemin (`@/*`)** : Simplifie les imports et améliore la maintenabilité du code via `tsconfig.json` (le dossier racine joue le rôle de racine `src/`).

## 6. ROADMAP & ÉVOLUTIONS FUTURES

- **Persistance des favoris** : Ajout de la possibilité d'enregistrer ses citations favorites (AsyncStorage ou SecureStore).
- **Partage de citations** : Intégration d'une fonctionnalité de partage natif (Social Share API) vers les réseaux sociaux ou applications.
- **Catégorisation des citations** : Filtrage par auteur, thème ou catégorie (inspiration, motivation, philosophie...).
- **Mode hors-ligne** : Mise en cache des citations récemment consultées pour un accès sans connexion internet.
- **Personnalisation avancée** : Possibilité de choisir des palettes de dégradés personnalisées ou d'ajouter des polices supplémentaires.
- **Internationalisation (i18n)** : Support multilingue pour élargir l'accessibilité de l'application.
- **Tests unitaires et d'intégration** : Mise en place d'une couverture de tests (Jest, React Native Testing Library) pour garantir la rigueur technique.
- **Accessibilité (a11y)** : Amélioration du contraste, ajout de descriptions d'accessibilité et support des lecteurs d'écran.

## 7. INSTALLATION ET LANCEMENT

### Prérequis

- [Node.js](https://nodejs.org/) (version LTS recommandée)
- [npm](https://www.npmjs.com/) ou [yarn](https://yarnpkg.com/)
- [Expo CLI](https://docs.expo.dev/get-started/installation/) (facultatif, géré via npx)
- Pour l'émulation mobile : [Android Studio](https://developer.android.com/studio) (Android) ou [Xcode](https://developer.apple.com/xcode/) (iOS - macOS uniquement)

### Étapes d'installation

1. **Cloner le dépôt**

   ```bash
   git clone https://github.com/[votre-nom]/MonAppCitationExpo.git
   cd MonAppCitationExpo
   ```

2. **Installer les dépendances**

   ```bash
   npm install
   ```

3. **Lancer l'application**

   L'application peut être lancée sur différentes plateformes via Expo :

   - **Mode développement (Expo Go ou Dev Client)**

     ```bash
     npm start
     ```

   - **Sur Android (émulateur ou appareil)**

     ```bash
     npm run android
     ```

   - **Sur iOS (émulateur ou appareil - macOS requis)**

     ```bash
     npm run ios
     ```

   - **Sur le Web**

     ```bash
     npm run web
     ```

4. **Vérification du code (Lint)**

   ```bash
   npm run lint
   ```

### Remarques

- Un **Dev Client** est configuré (`expo-dev-client`) pour permettre l'utilisation de modules natifs personnalisés si besoin.
- Le projet utilise **Expo SDK 53** avec l'architecture React Native New Architecture activée (`newArchEnabled: true`).
- L'application se connecte à l'API publique [Quotable.io](https://api.quotable.io/) : une connexion internet est nécessaire pour générer de nouvelles citations.