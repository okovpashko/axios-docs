---
title: 'Початок роботи'
description: 'HTTP клієнт для браузеру та Nodejs на базі Promise'
next_title: 'Короткі приклади'
next_link: '/uk/docs/example'
---

# Що таке Axios?
Axios-це HTTP клієнт на основі *[Promise](https://javascript.info/promise-basics)* для [`node.js`](https://nodejs.org) та браузера. Він *[ізоморфний](https://www.lullabot.com/articles/what-is-an-isomorphic-application)* (= він може працювати у браузері та nodejs з тією ж кодовою базою). На стороні сервера він використовує нативний `http` модуль Node.js, тоді як на клієнті (в браузері) він використовує `XMLHttpRequest`.

# Переваги

- Виконання [XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) запити з браузеру
- Виконання [http](http://nodejs.org/api/http.html) запити з node.js
- Підтримка [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise) API
- Перехоплення запиту і відповіді
- Перетворення даних в запиті та відповіді
- Скасування запитів
- Автоматичне перетворення даних JSON
- Підтримка захисту від [XSRF](http://en.wikipedia.org/wiki/Cross-site_request_forgery) на стороні клієнта

# Встановлення

Використовуючи npm:

```bash
$ npm install axios
```

Використовуючи bower:

```bash
$ bower install axios
```

Використовуючи yarn:

```bash
$ yarn add axios
```

Використовуючи jsDelivr CDN:

```html
<script src="https://cdn.jsdelivr.net/npm/axios/dist/axios.min.js"></script>
```

Використовуючи unpkg CDN:

```html
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
```
