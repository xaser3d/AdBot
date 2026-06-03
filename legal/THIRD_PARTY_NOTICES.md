# Third-Party Notices — AdBot

AdBot is a Unreal Engine integration layer. **Third-party Android SDK binaries are not included in the Fab/marketplace plugin ZIP.** At Android package time, Gradle resolves the dependencies below from official Maven repositories (see `Source/AdBot/AdBot_UPL.xml`). The game developer building the APK accepts each vendor’s license when downloading and using those artifacts.

## Distribution model (marketplace compliance)

| What AdBot ships | What the game developer gets at Android build |
|------------------|-----------------------------------------------|
| C++/Blueprint integration, UPL, Java bridge, Gradle dependency declarations | SDK `.aar` / transitive libraries downloaded by Gradle on the developer’s machine |
| No redistribution of Yandex, Mintegral, Google, or Huawei SDK binaries inside the plugin product | Separate accounts, keys, and legal compliance for each enabled network |

This matches the Yandex Mobile Ads SDK License Agreement **Section 3.2** (the SDK itself must not be distributed by third parties) and **Section 3.3** (the *application* built with the SDK may be distributed with required attribution).

**Yandex attribution (Section 3.3):** If you ship an app that uses Yandex Mobile Ads SDK, include the notice **“Developed with the use of Yandex Mobile Ads SDK”** in the program About section, on the app store download page, and in the installer description file (if you ship one).

**Mintegral mediation:** AdBot enables **`com.yandex.ads.mediation:mobileads-mintegral`** (Yandex’s mediation adapter). The full **Mintegral SDK** is not bundled in AdBot; it may be pulled transitively by Gradle when the toggle is ON. You need your own Mintegral / Yandex mediation setup and must comply with [Mintegral Terms of Service](https://www.mintegral.com/en/terms-of-service/) and Mintegral’s SDK/developer terms from the [Mintegral developer portal](https://www.mintegral.com/en/) — not only the Privacy Policy.

## Always included (Android package)

| Component | Maven coordinate | Vendor |
|-----------|----------------|--------|
| Yandex Mobile Ads | `com.yandex.android:mobileads:8.0.0` | Yandex |
| AppMetrica Analytics | `io.appmetrica.analytics:analytics:8.2.0` | Yandex |

## Optional — Yandex Mediation (Project Settings toggles)

| Network | Maven coordinate (when enabled) |
|---------|----------------------------------|
| VK Ads (myTarget) | `com.yandex.ads.mediation:mobileads-mytarget:5.45.3.1` |
| Mintegral | `com.yandex.ads.mediation:mobileads-mintegral:17.0.41.0` |
| BIGO Ads | `com.yandex.ads.mediation:mobileads-bigoads:5.7.0.0` |
| Liftoff (Vungle) | `com.yandex.ads.mediation:mobileads-vungle:7.7.0.0` |
| InMobi | `com.yandex.ads.mediation:mobileads-inmobi:11.0.0.0` |

## Optional — AppMetrica Push (when enabled in Project Settings)

| Component | Maven coordinate |
|-----------|------------------|
| AppMetrica Push | `io.appmetrica.analytics:push:4.3.0` |
| Firebase provider | `io.appmetrica.analytics:push-provider-firebase:4.3.0` |
| HMS provider | `io.appmetrica.analytics:push-provider-hms:4.3.0` |
| AndroidX legacy support | `androidx.legacy:legacy-support-v4:1.0.0` |
| Firebase Cloud Messaging | `com.google.firebase:firebase-messaging:22.0.0` |
| Google Play services base | `com.google.android.gms:play-services-base:17.5.0` |

Push also requires Firebase and/or Huawei project configuration in the buyer's AppMetrica cabinet and in `Config/DefaultAdBot.ini` (or `google-services.json` import).

## Buyer responsibilities

1. **Accounts:** Yandex Advertising Network (ad unit IDs), [AppMetrica](https://appmetrica.yandex.com/) (API key). For push: Firebase and/or Huawei AppGallery Connect as applicable.
2. **Network at build time:** Android packaging needs Maven access (`google()`, `mavenCentral()`, and Mintegral repo if that adapter is enabled).
3. **Privacy & consent:** GDPR, COPPA, personalized ads consent, location tracking, and Android 13+ `POST_NOTIFICATIONS` runtime permission are the **game developer's** responsibility. AdBot exposes Blueprint privacy nodes; it does not provide legal text or a CMP.
4. **SDK terms:** Use of Yandex, Google, Huawei, and mediation SDKs is governed by each vendor’s **software license / terms of service** (privacy policies alone are not sufficient for redistribution rights). Review:

| Vendor / component | License or terms (software) | Privacy |
|------------------|----------------------------|---------|
| Yandex Mobile Ads SDK 8.0.0 | [Mobile Ads SDK License Agreement](https://yandex.com/legal/mobileads_sdk_agreement/) | [Yandex Privacy Policy](https://yandex.com/legal/confidential/) |
| AppMetrica Analytics 8.2.0 | [AppMetrica terms](https://yandex.com/legal/appmetrica_termsofuse/) (and Yandex service terms) | [AppMetrica data policy](https://yandex.com/legal/confidential/) |
| Yandex mediation adapters (VK, Mintegral, BIGO, Liftoff, InMobi) | Covered by Yandex Mobile Ads / mediation docs; each network has its own partner terms | Per network (e.g. [Mintegral Privacy](https://www.mintegral.com/en/privacy/)) |
| Mintegral SDK (when mediation ON) | [Mintegral Terms of Service](https://www.mintegral.com/en/terms-of-service/) + SDK license from Mintegral developer portal | [Mintegral Privacy Policy](https://www.mintegral.com/en/privacy/) |
| Firebase / Google Play services (push) | [Google APIs Terms](https://developers.google.com/terms) / [Firebase Terms](https://firebase.google.com/terms) | [Google Privacy Policy](https://policies.google.com/privacy) |
| Huawei HMS (push, optional) | [Huawei developer agreements](https://developer.huawei.com/) | Huawei privacy docs |

Product help (not a substitute for legal text): [Yandex Ads Help](https://ads.yandex.com/helpcenter/en/), [AppMetrica](https://appmetrica.yandex.com/).

## AdBot-authored code

Java bridge under `Source/ThirdParty/Android/java/com/adbot/` and C++ under `Source/AdBot/` are part of the AdBot plugin and licensed under `LICENSE.txt` (plugin EULA), not under the third-party SDK licenses above.
