# JP Ogalo Aesthetic AI — Android-ready prototype

A mobile-first interactive prototype for the Dr JP Ogalo aesthetic procedure concept. It includes:

- Dark premium UI with African model imagery.
- Liposuction explorer: weight sliders, target areas, visualisation intensity, drag-to-rotate model, before/after-style toggle and indicative demo estimate.
- Botox explorer: selectable facial zones, illustrative units slider, facial treatment hotspots and indicative demo estimate.
- Anatomy learning screen with selectable layers.
- Local photo upload and preview flow.
- Consultation estimate screen and print action.
- PWA manifest/service worker for browser installation.

## Run the demo

Open `index.html` in a modern browser. For PWA install/offline caching, serve this folder over HTTPS or localhost (for example `python -m http.server 8080`) and open it in Chrome on Android.

## Android APK

This environment does not contain the Android SDK, Gradle, or network access to download them, so a signed APK cannot be compiled here. The project is web-ready and can be wrapped with Capacitor on a machine with Android Studio installed:

```bash
npm create @capacitor/app@latest
# Choose an app name and package ID, then copy this prototype's index.html,
# assets/, manifest.webmanifest and sw.js into the generated web directory.
npm install @capacitor/android
npx cap add android
npx cap sync android
npx cap open android
```

In Android Studio: Build → Build Bundle(s) / APK(s) → Build APK(s). For a distributable release, configure a signing key under Build → Generate Signed Bundle / APK.

## Before production

1. Replace all demo price ranges with Dr Ogalo's approved clinic pricing and quote rules.
2. Add clinician-approved 3D anatomy assets (GLB/GLTF) and a true Three.js/WebGL scene. The current model rotation is a visual interaction prototype, not a full anatomical mesh.
3. Build a secure backend for image upload, consent, authentication, storage, AI editing and clinician review. Do not put API keys in the Android client.
4. Add AI image-editing with a fixed prompt template, preserving identity and skin tone, plus safety checks and clear simulation labels. The local upload currently previews only; it does not generate a real AI result.
5. Add the clinic's correct contact details, booking link, privacy policy, data retention policy and medical disclaimers.
6. Do not use a photo of a patient without explicit informed consent. Avoid sending intimate or identifiable images to third-party AI services without a documented privacy and data-processing assessment.

## Pricing placeholders

The KES ranges shown are demonstration placeholders only, not Dr Ogalo's prices or a clinical quote. Replace them before showing the app as a real quoting service.

## Native Android Studio project

A minimal Android WebView wrapper is included in `android/`. Open that folder directly in Android Studio. It includes the app manifest, Java activity, Gradle build files and bundled web assets. Android Studio will need internet access to resolve Gradle/Android plugins and an Android SDK (API 35) installed. Then use **Build → Build APK(s)**.
# Prototype-II
