# FAST ШИНА — сайт шиномонтажу

Статичний сайт для GitHub Pages. Без бекенду, без збірки — чистий HTML/CSS/JS.

## Структура

```
index.html            головна сторінка
config.js             налаштування (адреса endpoint для заявок)
privacy.html          політика конфіденційності
.nojekyll             вимикає обробку Jekyll на GitHub Pages
data/fitment-db.json  база авто для підбору шин/дисків
README.md             цей файл
```

## Як заявки приходять у Telegram

1. Форма на сайті відправляє POST-запит на адресу з `config.js`
   (змінна `window.FASTSHUNA_BOOKING_ENDPOINT`).
2. Ця адреса — ваш Google Apps Script Web App URL.
3. Скрипт отримує дані й пересилає їх у Telegram.

**Щоб підключити:** відкрийте `config.js` і вставте ваш Web App URL:
```js
window.FASTSHUNA_BOOKING_ENDPOINT = "https://script.google.com/macros/s/.../exec";
```
Якщо залишити порожнім — форма покаже «Форма тимчасово не підключена» (сайт не зламається).

## Як оновити базу авто

База лежить у `data/fitment-db.json`. Кожен запис — одне покоління авто
з розмірами шин і параметрами диска. Додавайте нові марки в тому ж форматі.

## Як опублікувати на GitHub Pages

1. Залийте всі файли в репозиторій (index.html має бути в корені).
2. Settings → Pages → Source: гілка `main`, папка `/root`.
3. Через 1–2 хвилини сайт буде доступний за адресою GitHub Pages.

## Контакти

FAST ШИНА · вул. Степана Будного, 9, Тернопіль · +380 68 772 71 10
