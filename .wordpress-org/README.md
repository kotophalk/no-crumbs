# Ассеты для каталога WordPress.org

Содержимое папки `assets/` в SVN плагина (`https://plugins.svn.wordpress.org/nocrumbs-cookie-notice/assets/`).
В zip плагина не входит.

| Файл | Что |
|---|---|
| `banner-772x250.png`, `banner-1544x500.png` | шапка карточки (1x / 2x) |
| `icon-128x128.png`, `icon-256x256.png` | иконка `[ ОК ]` |
| `screenshot-1.png`, `screenshot-2.png` | десктоп 1280×800 @2x, телефон 390×780 @2x; подписи — в `readme.txt`, секция `== Screenshots ==` |

## Перерисовать

Исходники — `src/*.html`. Стиль бренда Делосвода (Geist, `#171717`, лейбл `[ БЕРИТЕ И ПОЛЬЗУЙТЕСЬ ]`).
Скриншоты — не макет: `shot.html` подключает настоящие `assets/css/nocrumbs-cookie-notice.css` и `assets/js/nocrumbs-cookie-notice.js`.

Рядом с HTML нужны `Geist-Variable.woff2`, `GeistMono-Variable.woff2` (лежат в теме хаба, `delosvod/theme/generatepress_child/fonts/`)
и копии css/js плагина. Рендер — любой headless Chromium:

```bash
CH=~/.cache/ms-playwright/chromium_headless_shell-*/chrome-linux/headless_shell
$CH --headless --no-sandbox --hide-scrollbars --force-device-scale-factor=2 --window-size=772,250 --screenshot=banner-1544x500.png file://$PWD/banner.html
convert banner-1544x500.png -resize 772x250 banner-772x250.png
$CH --headless --no-sandbox --hide-scrollbars --window-size=256,256 --screenshot=icon-256x256.png file://$PWD/icon.html
convert icon-256x256.png -resize 128x128 -type TrueColor icon-128x128.png
$CH --headless --no-sandbox --hide-scrollbars --force-device-scale-factor=2 --virtual-time-budget=2000 --window-size=1280,800 --screenshot=screenshot-1.png file://$PWD/shot.html
$CH --headless --no-sandbox --hide-scrollbars --force-device-scale-factor=2 --virtual-time-budget=2000 --window-size=390,780  --screenshot=screenshot-2.png file://$PWD/shot.html
```

Потом — в SVN-чекаут `my-plugin-svn/nocrumbs-cookie-notice/assets/` и `svn commit`.
