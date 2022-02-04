---
title: 'Короткі приклади'
description: 'Короткі приклади використання Axios'
prev_title: 'Початок роботи'
prev_link: '/uk/docs/intro'
next_title: 'POST запити'
next_link: '/uk/docs/post_example'
---

## Примітка: використання CommonJS
Для того, щоб отримати типи TypeScript (для intellisense / автозаповнення) використовуючи CommonJS імпорти з `require()`, використовуйте такий підхід:

```js
const axios = require('axios').default;

// axios.<method> тепер забезпечуватиме автозаповнення та типізацію параметрів
```

# Example

Виконання `GET` запиту

```js
const axios = require('axios');

// Робимо запит для користувача з даним ID
axios.get('/user?ID=12345')
  .then(function (response) {
    // обробка успішного запиту
    console.log(response);
  })
  .catch(function (error) {
    // обробка помилки
    console.log(error);
  })
  .then(function () {
    // виконується завжди
  });

// За бажанням вищевказаний запит також можна виконати так
axios.get('/user', {
    params: {
      ID: 12345
    }
  })
  .then(function (response) {
    console.log(response);
  })
  .catch(function (error) {
    console.log(error);
  })
  .then(function () {
    // виконується завжди
  });  

// Хочете використовувати async/await? Додайте ключове слово `async` до своєї зовнішньої функції/методу.
async function getUser() {
  try {
    const response = await axios.get('/user?ID=12345');
    console.log(response);
  } catch (error) {
    console.error(error);
  }
}
```

> ** ПРИМІТКА: ** `async/await` є частиною ECMAScript 2017 і не підтримується в Internet
> Explorer та старіших веб-переглядачах, тому використовуйте їх з обережністю.
