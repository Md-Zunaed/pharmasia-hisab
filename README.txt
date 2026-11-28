PHARMASIA HISAB - fixed version

FILES (shob ek folder e rakhte hobe):
  pharmasia_hisab_app.html, index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png

PHONE E APP HISEBE USE KORTE (HTTPS hosting lage - file:// e install/offline kaj kore na):
  Option A - Netlify Drop: https://app.netlify.com/drop e ei folder ta drag-drop koro, link pabe.
  Option B - GitHub Pages: repo te file gulo upload kore Settings > Pages on koro.
  Tarpor phone Chrome e link khule: menu > Install app / Add to Home Screen.
  Prothom bar internet e khulte hobe (style/fonts cache hoye jay), tarpor offline o cholbe.

GOOGLE SYNC: app er Sync button e Firebase config paste koro (Firebase Console > Project settings > Web app).
  Authorized domains e tomar hosting domain add korte hobe. Firestore rules: shudhu nijer uid read/write:
    match /users/{uid}/{document=**} { allow read, write: if request.auth != null && request.auth.uid == uid; }

MONTHLY COST TAB (notun):
  Alada "Monthly Cost" tab: protita khoroch er date, category, amount ar note (kno ei cost holo).
  Category: Meal, Travel, Hand Cost, House+Wifi+Pharia, Other. Protita category r mashik limit box e edit kora jay.
  July ar August er data Monthly_Cost.xlsx theke import kora ache. CSV export ar backup/sync e cost o thake.

UPDATE (premium):
  - Notun icon (capsule + gold ring), header logo o capsule.
  - Monthly Cost tab premium design: hero total + progress ring, category split, daily spend graph, category budget cards, notes list.
  - "Download All" button (Monthly Cost tab ar Settings e): ek click e shob month er shob data ek Excel (.xlsx) file e,
    7 ta sheet: Summary, Parties, Daily Sales, Honorarium, Loss & Profit, Monthly Cost, Cost Budget.
  - Loss ar Profit row er naam ekhon edit kora jay.

UPDATE KORAR NIYOM: host kora jaygay (Netlify/GitHub) purano file gulo replace koro, tarpor phone e app ta bondho kore abar kholo.
  Na bodlale browser/app e purano version cache theke dekhabe.
