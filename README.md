# AdBot — документация (GitHub Pages)

Unreal Engine Android plugin: Yandex Mobile Ads SDK 8 — banner, interstitial, rewarded, app open. VK Ads mediation (Yandex myTarget adapter). Blueprint: privacy (consent, location tracking, age-restricted, logging, debug panel) & targeting (age, gender, geo, context).

Публичный сайт: [https://xaser3d.github.io/AdBot/](https://xaser3d.github.io/AdBot/)

## Локальный просмотр и символ `#` в пути Windows

Если репозиторий лежит в папке вроде `D:\#AdBot_backUP\web\`, **не открывайте `index.html` через `file://` двойным щелчком**: в URL символ `#` воспринимается как разделитель фрагмента, и браузер «ломает» путь — стили (`css/style.css`) могут не подгрузиться, главная выглядит «сырой».

**Варианты:**

1. Запустить статический сервер из каталога `web` (рекомендуется), например: `npx --yes serve .` и открыть `http://localhost:3000`.
2. Переименовать родительскую папку без `#` (например `AdBot_backUP`).
3. Для GitHub Pages относительная ссылка `css/style.css` в корне репозитория работает: страница [хаба](https://xaser3d.github.io/AdBot/) подхватывает тот же `css/style.css` с сайта.

