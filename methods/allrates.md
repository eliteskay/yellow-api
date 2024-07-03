---
description: Возвращает все возможные направления и курсы обмено
---

# allRates

### Method

* GET

### Headers

* Y\_API\_KEY: публичный API ключ

### Пример

{% code overflow="wrap" lineNumbers="true" fullWidth="false" %}
```javascript
const fetch = require('node-fetch');

let url = 'https://localhost:3000/trades/allRates';

let options = {
  method: 'GET',
  headers: {
    Y_API_KEY: 'публичный API ключ',
  }
};

fetch(url, options)
  .then(res => res.json())
  .then(json => console.log(json))
  .catch(err => console.error('error:' + err));
```
{% endcode %}

