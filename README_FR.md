# KYBRA NOVA — projet Android

Projet Android qui embarque le jeu KYBRA Guess Nova dans une WebView locale. Le jeu HTML/CSS/JavaScript est inclus dans l'application ; le gameplay n'a pas besoin d'une connexion Internet.

## Créer le véritable APK depuis un Samsung, sans ordinateur

Le ZIP contient maintenant un workflow GitHub Actions pour compiler automatiquement l'APK sur les serveurs GitHub.

1. Téléchargez `KYBRA_NOVA_ANDROID_PROJECT.zip` et décompressez-le si possible.
2. Dans le navigateur du téléphone, connectez-vous à GitHub et créez un nouveau dépôt (repository), par exemple `kybra-nova-android`.
3. Envoyez le CONTENU du dossier `KYBRA_NOVA_ANDROID` dans le dépôt, et pas le dossier parent en entier. Le fichier `.github/workflows/build-apk.yml` doit se trouver à l'adresse `.github/workflows/build-apk.yml` à la racine du dépôt. Si l'interface mobile ne permet pas de téléverser le dossier `.github`, créez les dossiers/fichiers depuis l'interface GitHub ou utilisez l'éditeur web.
4. Ouvrez l'onglet **Actions** du dépôt. Sélectionnez **Build KYBRA NOVA APK** puis **Run workflow**. Le workflow peut aussi se lancer automatiquement après un push sur `main` ou `master`.
5. Attendez que l'exécution se termine avec une coche verte.
6. Ouvrez cette exécution, descendez jusqu'à **Artifacts**, puis téléchargez `KYBRA-NOVA-debug-APK`.
7. Extrayez le ZIP d'artifact téléchargé : il contient `app-debug.apk`. Appuyez dessus pour installer. Android peut demander d'autoriser l'installation depuis cette source.

## Paramètres du build

- Application ID : `com.kybra.guessnova`
- Version : `1.0.0`
- Android minimum : API 23 (Android 6.0)
- Compile SDK : 35
- Le workflow utilise Java 17, Gradle 8.9 et Android SDK Build Tools 35.0.0.

## Important

Ce dépôt contient le code source et l'automatisation de compilation, pas un APK déjà compilé. La compilation doit être exécutée sur GitHub Actions. Il s'agit d'un APK de débogage (`debug`), adapté aux tests et à une installation personnelle, pas d'une version de publication signée avec une clé privée personnelle. Le build doit réussir avant que l'APK soit disponible dans les artifacts.
