---
title: 'Конфігурація запиту'
prev_title: 'Екземпляр Axios'
prev_link: '/uk/docs/instance'
next_title: 'Схема відповіді'
next_link: '/uk/docs/res_schema'
---


Нижче вказані доступні параметри конфігурації для відправки запитів. Лише `url` є обов’язковим. Запити за замовчуванням використовують метод `GET`, якщо` method` не вказано.

```js
{
  // `url` - це URL-адреса сервера, яка буде використовуватися для запиту
  url: '/user',

  // `метод` - це метод запиту, який слід використовувати під час відправки запиту
  method: 'get', // значення за замовчуванням

  // `baseURL` буде додаватися до `url`, якщо `url` не є абсолютним.
  // Може бути зручно встановити `baseURL` для екземпляра axios для передачі відносних URL-адрес
  // методам цього екземпляра.
  baseURL: 'https://some-domain.com/api',

  // `transformRequest` дозволяє змінювати дані запиту перед їх надсиланням на сервер
  // Це стосується лише методів запиту "PUT", "POST", "PATCH" та "DELETE"
  // Остання функція в масиві повинна повертати рядок або екземпляр Buffer, ArrayBuffer, FormData або Stream
  // Ви можете змінювати об'єкт із заголовками.
  transformRequest: [function (data, headers) {
    // Робіть все, що завгодно, щоб перетворити дані

    return data;
  }],

  // `transformResponse` дозволяє вносити зміни до даних відповідей перед їх передачею в then/catch
  transformResponse: [function (data) {
    // Робіть все, що завгодно, щоб перетворити дані

    return data;
  }],

  // `заголовки` - це спеціальні заголовки для надсилання
  headers: {'X-Requested-With': 'XMLHttpRequest'},

  // `params` - це параметри URL-адреси, які надсилаються разом із запитом
  // Має бути звичайним об’єктом або об’єктом URLSearchParams
  // ПРИМІТКА. Параметри, які є містять `null` або `undefined`, не відображаються в URL адресі.
  params: {
    ID: 12345
  },

  // `paramsSerializer` - це додаткова функція, яка відповідає за серіалізацію `params`
  // (наприклад https://www.npmjs.com/package/qs, http://api.jquery.com/jquery.param/)
  paramsSerializer: function (params) {
    return Qs.stringify(params, {arrayFormat: 'brackets'})
  },

  // `data` - це дані, які надсилаються в тілі запиту
  // Застосовується лише до методів запиту "PUT", "POST", "DELETE" та "PATCH"
  // Коли параметр `transformRequest` вказано, він повинен мати один із таких типів:
  // - рядок, звичайний об'єкт, ArrayBuffer, ArrayBufferView, URLSearchParams
  // - Лише для браузера: FormData, File, Blob
  // - Лише для Nodejs: Stream, Buffer
  data: {
    firstName: 'Fred'
  },
  
  // альтернативний синтаксис для надсилання даних в тілі запиту
  // POST метод
  // надсилається лише значення, без ключа
  data: 'Country=Brasil&City=Belo Horizonte',

  // `timeout` визначає кількість мілісекунд для очікування виконання запиту.
  // Якщо запит займає більше часу, ніж значення `timeout`, запит буде скасовано.
  timeout: 1000, // за замовчуванням `0" (без тайм-ауту)

  // `withCredentials` вказує, чи міжсайтові запити з контролем доступу
  // повинні бути зроблені з використанням облікових даних
  withCredentials: false, // значення за замовчуванням

  // `адаптер` дозволяє використовувати користувацьку обробку запитів, що полегшує тестування.
  // Повертає Promise та надає коректну відповідь (див. Lib/adapters/README.md).
  adapter: function (config) {
    /* ... */
  },

  // TODO: translate
  // `auth` indicates that HTTP Basic auth should be used, and supplies credentials.
  // This will set an `Authorization` header, overwriting any existing
  // `Authorization` custom headers you have set using `headers`.
  // Please note that only HTTP Basic auth is configurable through this parameter.
  // For Bearer tokens and such, use `Authorization` custom headers instead.

  // `auth` вказує, що слід використовувати HTTP Basic аутентифікацію і надає облікові дані.
  // Це встановить заголовок `Authorization` з перезаписуванням будь-якого існуючого
  // користувацького заголовка `Authorization`, який ви встановили за допомогою `headers`.
  // Зверніть увагу, що за допомогою цього параметра можна налаштувати лише HTTP Basic авторизацію.
  // Для Bearer і подіних токенів використовуйте спеціальні заголовки `Authorization`.
  auth: {
    username: 'janedoe',
    password: 's00pers3cret'
  },

  // `responseType` вказує на тип даних у відповіді сервера
  // доступні варіанти: 'arraybuffer', 'document', 'json', 'text', 'stream'
  // тільки для браузера: 'blob'
  responseType: 'json', // значення за замовчуванням

  // `responseEncoding` вказує кодування для декодування відповідей (лише для Node.js)
  // Примітка: Ігнорується для `responseType` запитів 'stream' або запитів на стороні клієнта
  responseEncoding: 'utf8', // значення за замовчуванням

  // `xsrfCookieName` - це ім’я cookie, яке буде використовуватися як значення xsrf токена
  xsrfCookieName: 'XSRF-TOKEN', // значення за замовчуванням

  // `xsrfHeaderName` - це назва http заголовка, що містить значення xsrf токена
  xsrfHeaderName: 'X-XSRF-TOKEN', // значення за замовчуванням

  // `onUploadProgress` дозволяє обробляти події прогресу відправки даних
  // тільки для браузера
  onUploadProgress: function (progressEvent) {
    // Робіть що завгодно з нативною подією прогресу
  },

  // `onDownloadProgress` дозволяє обробляти події прогресу отримання даних
  // тільки для браузера
  onDownloadProgress: function (progressEvent) {
    // Робіть що завгодно з нативною подією прогресу
  },

  // `maxContentLength` (лише для Node.js) визначає максимальний дозволений розмір вмісту http відповіді у байтах
  maxContentLength: 2000,

  // `maxBodyLength` (лише для Node.js) визначає максимальний дозволений розмір вмісту http запиту в байтах
  maxBodyLength: 2000,

  // `validateStatus` визначає, чи потрібно вирішувати чи відхиляти promise для отриманого коду
  // стутусу відповіді HTTP. Якщо `validateStatus` повертає` true` (або має значення `null` або` undefined`), 
  // promise буде `fulfilled`; в іншому випадку Promise буде `rejected`.
  validateStatus: function (status) {
    return status >= 200 && status < 300; // значення за замовчуванням
  },

  // `maxRedirects` визначає максимальну кількість переспрямувань у node.js.
  // Якщо вказано значення 0, переспрямування не будуть виконуватися.
  maxRedirects: 5, // значення за замовчуванням

  // `socketPath` визначає UNIX сокет для використання в node.js.
  // наприклад '/var/run/docker.sock' для надсилання запитів до демону docker.
  // Можна вказати лише `socketPath` або` proxy`.
  // Якщо вказано обидва, використовується `socketPath`.
  socketPath: null, // значення за замовачуванням

  // `httpAgent` та` httpsAgent` визначають користувацький агент, який буде використовуватися під час виконання, відповідно,
  // http та https запитів в node.js. Це дозволяє вкаувати такі параметри, як
  // `keepAlive`, які не включені за замовчуванням.
  httpAgent: new http.Agent({ keepAlive: true }),
  httpsAgent: new https.Agent({ keepAlive: true }),

  // `proxy` визначає ім’я хоста, порт та протокол проксі -сервера.
  // Ви також можете визначити свій проксі за допомогою зручних змінних оточення 
  // `http_proxy` та` https_proxy`. Якщо ви використовуєте змінні оточення для конфігурації 
  // проксі-сервера, ви також можете визначити змінну оточення `no_proxy`
  // у вигляді списку доменів розділених комами, для яких не слід використовувати проксі.
  // Використовуйте `false`, щоб вимкнути проксі, ігноруючи змінні оточення.
  // `auth` вказує, що для підключення до проксі-сервера слід використовувати базову аутентифікацію HTTP, а також 
  // надає облікові дані.
  // Це встановить заголовок `Proxy-Authorization`, який перезапише будь-які існуючі спеціальні заголовки `Proxy-Authorization`, які ви вказали за допомогою `headers`.
  // Якщо проксі-сервер використовує протокол HTTPS, потрібно вказати протокол `https`.
  proxy: {
    protocol: 'https',
    host: '127.0.0.1',
    port: 9000,
    auth: {
      username: 'mikeymike',
      password: 'rapunz3l'
    }
  },

  // `cancelToken` визначає токен скасування, який можна використати для скасування запиту (див. детальніше у розділі Скасування нижче)
  cancelToken: new CancelToken(function (cancel) {
  }),

  // `decompress` вказує, чи слід автоматично розпаковувати тіло відповіді. Якщо встановлено значення `true`, 
  // також буде видалено заголовок "content-encoding" з об'єктів відповідей усіх розпакованих відповідей
  // Лише для Node.js (XHR не може вимкнути декомпресію)
  decompress: true // значення за замовчуванням

}
```
