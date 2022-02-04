---
title: 'Axios API'
description: 'Посилання на API Axios'
prev_title: 'POST запити'
prev_link: '/uk/docs/post_example'
next_title: 'Екземпляр Axios'
next_link: '/uk/docs/instance'
---

Запити можна виконувати, передавши відповідну конфігурацію `axios`.

##### axios(config)

```js
// Надіслати POST-запит
axios({
  method: 'post',
  url: '/user/12345',
  data: {
    firstName: 'Fred',
    lastName: 'Flintstone'
  }
});
```

```js
// GET-запит на отримання зображення у node.js
axios({
  method: 'get',
  url: 'http://bit.ly/2mTM3nY',
  responseType: 'stream'
})
  .then(function (response) {
    response.data.pipe(fs.createWriteStream('ada_lovelace.jpg'))
  });
```

##### axios(url[, config])

```js
// Надіслати запит GET (метод за замовчуванням)
axios('/user/12345');
```

### Псевдоніми методу запиту

Для зручності існують псевдоніми для всіх підтримуваних методів запиту.

##### axios.request(config)
##### axios.get(url[, config])
##### axios.delete(url[, config])
##### axios.head(url[, config])
##### axios.options(url[, config])
##### axios.post(url[, data[, config]])
##### axios.put(url[, data[, config]])
##### axios.patch(url[, data[, config]])

###### ПРИМІТКА
При використанні методів-псевдонімів, властивості `url`,` method` та `data` не потрібно вказувати в config.
