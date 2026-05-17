# AdBot — документация (GitHub Pages)

Unreal Engine Android plugin: **Yandex Mobile Ads SDK 8.0.0**, **AppMetrica 8.2.x**, VK Ads mediation. Форматы: баннер, межстраничная, app open. **Rewarded** — см. Known Issues (нестабилен в текущей сборке).

Публичный сайт: [https://xaser3d.github.io/AdBot/](https://xaser3d.github.io/AdBot/)

## Новое в документации

- **AppMetrica 8** — события, профили, сессии, Blueprint-примеры (`AdBot|AppMetrica`)
- **Project Settings** — startup init, Default Banner Size Preset (90 dp = индекс 7)
- **SDK & Android Build** — версии Gradle, пересборка APK после UPL
- **Known Issues** — rewarded video, Invalid SDK state, interstitial delay

## Локальный просмотр и символ `#` в пути Windows

Если репозиторий лежит в папке вроде `D:\#AdBot_backUP\web\`, **не открывайте `index.html` через `file://` двойным щелчком**: в URL символ `#` воспринимается как разделитель фрагмента, и браузер «ломает» путь — стили (`css/style.css`) могут не подгрузиться.

**Варианты:**

1. `npx --yes serve .` из каталога `web` → `http://localhost:3000`
2. Переименовать родительскую папку без `#` (например `AdBot_backUP`)
3. GitHub Pages: [https://xaser3d.github.io/AdBot/](https://xaser3d.github.io/AdBot/)

## Публикация на GitHub Pages

```bash
cd D:\#AdBot_backUP\web
git add adbot/index.html index.html README.md
git commit -m "docs: AppMetrica 8, SDK build, known issues (rewarded)"
git push origin main
```
