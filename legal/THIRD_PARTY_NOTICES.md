# Third-Party Notices — AdBot

AdBot is a Unreal Engine integration layer. **Third-party Android SDK binaries are not included in the plugin ZIP.** At Android package time, Gradle resolves the dependencies below from Maven (see `Source/AdBot/AdBot_UPL.xml`).

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
4. **SDK terms:** Use of Yandex, Google, Huawei, and mediation SDKs is governed by each vendor's terms of service and license agreements. Review:
   - [Yandex Mobile Ads](https://ads.yandex.com/helpcenter/en/)
   - [AppMetrica](https://appmetrica.yandex.com/)
   - [Firebase](https://firebase.google.com/terms)
   - [Huawei HMS](https://developer.huawei.com/)

## AdBot-authored code

Java bridge under `Source/ThirdParty/Android/java/com/adbot/` and C++ under `Source/AdBot/` are part of the AdBot plugin and licensed under `LICENSE.txt` (plugin EULA), not under the third-party SDK licenses above.
