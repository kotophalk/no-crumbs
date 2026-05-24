# Текущее состояние (State)

## Последнее обновление
Минорный релиз v1.3.0: обновлён Author URI и подтверждена совместимость с WordPress 7.0.

## Что сделано в версии 1.3.0:
1. Author URI обновлён на `https://delosvod.ru/`.
2. Совместимость подтверждена до WordPress 7.0 (`Tested up to`).
3. Обновлена вся документация (CHANGELOG, readme.txt, STATE.md).

## Что было сделано в версии 1.2.0:
1. Ребрендинг: Plugin Name → «NoCrumbs Cookie Notice», Text Domain → `nocrumbs-cookie-notice`.
2. Переименованы файлы ассетов: `no-crumbs.css` → `nocrumbs-cookie-notice.css`, `no-crumbs.js` → `nocrumbs-cookie-notice.js`.
3. Переименован POT-файл: `no-crumbs.pot` → `nocrumbs-cookie-notice.pot`.
4. Обновлены хэндлы `wp_enqueue_style` / `wp_enqueue_script`.
5. Обновлена вся документация (README, CHANGELOG, readme.txt, docs/).

## Итог разработки:
Архитектура (SDD) соблюдена на 100%. User Stories (PRD) покрыты в полном объеме.
Можно упаковывать каталог `nocrumbs-cookie-notice` в `.zip` и устанавливать на рабочий сайт!
