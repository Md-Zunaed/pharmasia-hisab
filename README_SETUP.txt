# Pharmasia Hisab — PC + Android PWA

## What is included
- `pharmasia_hisab_app.html`: upgraded app (existing business data and features retained)
- `manifest.webmanifest`, `sw.js`, `icon-192.png`, `icon-512.png`: install/offline app shell
- `firestore.rules`: per-Google-account private Firestore rules

## One-time Firebase setup
1. Open https://console.firebase.google.com/ and create a Firebase project.
2. Add a Web App in Project Overview and copy its Firebase Web config.
3. Authentication → Sign-in method → enable **Google**.
4. Authentication → Settings → Authorized domains: add the exact HTTPS hosting domain.
5. Firestore Database → Create database.
6. Firestore → Rules: replace the rules with the contents of `firestore.rules`, then Publish.
7. Host all files in this folder together on an HTTPS host (Firebase Hosting, Netlify, or GitHub Pages). Do not open the HTML using `file://`.
8. Open the hosted app → Sync button → paste Firebase Web config → Continue with Google.
9. Repeat on PC and Android using the same Google account. The app uses `users/{your-auth-uid}/pharmasia/main`, so each Google account can only access its own data.

## Local + cloud storage
- The app keeps a local browser copy in LocalStorage and downloads JSON/CSV backups through the existing Backup menu.
- Firestore's persistent browser cache is enabled for offline reads/writes. Offline edits are queued by the Firebase SDK and upload when the device reconnects.
- Install separately on PC and Android from the same HTTPS address.

## Important
- Firebase Web config is not a server secret; Firestore Security Rules are what protect user data. Never use Admin SDK/service-account private keys in this app.
- Keep periodic JSON backups. This build uses a single shared document per Google account and timestamp-based conflict resolution; avoid editing the same record on two devices simultaneously while both are offline.
- A downloaded local backup file is separate from the browser's automatic local copy.
