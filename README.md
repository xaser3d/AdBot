# AdBot — documentation (GitHub Pages)

Unreal Engine **Android** plugin: **Yandex Mobile Ads SDK 8**, **AppMetrica Analytics 8.2**, optional **AppMetrica Push 4.3** (FCM/HMS) with **Push Startup Policy** (Ads First / Push First / Manual), and **Yandex Mediation** adapters (VK, Mintegral, BIGO, Liftoff, InMobi). Ad formats: banner, interstitial, **rewarded video**, and app open — Blueprint async nodes for load/show. Rewarded nodes expose Video tokens, reward type/count, and structured Yandex error data.

**Live site:** [https://xaser3d.github.io/AdBot/](https://xaser3d.github.io/AdBot/)

## What’s documented

| Topic | Page |
|--------|------|
| Whisper2Text — offline STT, models, Blueprint | [Whisper2Text docs](https://xaser3d.github.io/AdBot/whisper2text/index.html) |
| Overview, setup, Project Settings | [AdBot docs](https://xaser3d.github.io/AdBot/adbot/index.html) |
| **What changed** (ini, push policy, notifications, banner) | [Integration checklist](https://xaser3d.github.io/AdBot/adbot/index.html#integration-changes) |
| AppMetrica statistics (events, profiles, nodes) | Analytics + Blueprint: AppMetrica |
| AppMetrica Push (Firebase + HMS setup) | Push Notifications + Blueprint: Push |
| **Android 13+ notifications** (cannot enable by default) | [POST_NOTIFICATIONS](https://xaser3d.github.io/AdBot/adbot/index.html#push-setup) |
| Yandex Mediation (5 networks) | Mediation |
| SDK versions & APK rebuild | SDK & Android Build |
| License, EULA & third-party SDKs | [License & Legal](https://xaser3d.github.io/AdBot/legal/index.html) · [in docs](https://xaser3d.github.io/AdBot/adbot/index.html#legal) |
| Bugs & feature requests | [GitHub Issues](https://github.com/xaser3d/AdBot/issues) · [Open new issue](https://github.com/xaser3d/AdBot/issues/new) |

## Local preview (Windows)

If the repo path contains `#`, do not open `index.html` via `file://` — the browser may break CSS paths.

```bash
cd C:\AdBot
npx --yes serve .
# open http://localhost:3000
```

## Publish to GitHub Pages

```bash
cd C:\AdBot
git add .
git commit -m "docs: mediation, AppMetrica push setup, English hub"
git push origin main
```

Plugin source lives in your UE project under `Plugins/AdBot/`.
