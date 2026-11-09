# Service Tracker (Android) — free build, no Android Studio needed

1. Create a free GitHub account and a new repository. Upload everything in this folder (keep the `.github` folder).
2. Open the repo's **Actions** tab → **Build APK** → wait ~5 minutes → download the **service-tracker-apk** artifact (zip containing `app-debug.apk`).
3. Copy the APK to your phone, open it, allow "install unknown apps".

Fingerprint/face lock works straight away (uses the phone's own biometrics).
Everything else (vehicles, services, bills, fuel, accessories, Indian brand list) works fully offline.

## Turn on Google sync (free)
1. console.cloud.google.com → new project → enable **Google Drive API**.
2. OAuth consent screen → External → add yourself as a test user.
3. Credentials → create an **Android** client ID (package `com.example.vehicleservicetracker`, SHA-1 of the debug keystore from the build) and a **Web** client ID.
4. Put the Web client ID in `capacitor.config.json` (`serverClientId`), commit, rebuild.
Data is stored in the app's hidden Drive folder, not your visible files.
