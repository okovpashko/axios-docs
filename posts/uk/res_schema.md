---
title: 'Схема відповіді'
prev_title: 'Конфігурація запиту'
prev_link: '/uk/docs/req_config'
next_title: 'Конфігурація за замовчуванням'
next_link: '/uk/docs/config_defaults'
---

Відповідь на запит містить наступну інформацію.

```js
{
  // `data` - це відповідь, надана сервером
  data: {},

  // `status` - це код стану HTTP з відповіді сервера
  status: 200,

  // `statusText` - це повідомлення HTTP статусу з відповіді сервера
  statusText: 'OK',

  // `headers` — це HTTP заголовки з відповіді сервера
  // Усі назви заголовків записані в нижньому регістрі та доступні за допомогою дужок.
  // Приклад: `response.headers['content-type']`
  headers: {},

  // `config` - це конфігурація запиту, яка була надана Axios
  config: {},

  // `запит` - це запит, який згенерував цю відповідь
  // Це останній екземпляр ClientRequest у Node.js (при переспрямуваннях)
  // і екземпляр XMLHttpRequest у веб-переглядачі
  request: {}
}
```

При використанні "then" ви отримаєте відповідь наступним чином:

```js
axios.get('/user/12345')
  .then(function (response) {
    console.log(response.data);
    console.log(response.status);
    console.log(response.statusText);
    console.log(response.headers);
    console.log(response.config);
  });
```

При використанні `catch` або передачі [rejection колбеку](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/then) як другого параметра `then`, відповідь буде доступна через об'єкт `error`, як пояснюється в розділі [Обробка помилок](/uk/docs/handling_errors).
