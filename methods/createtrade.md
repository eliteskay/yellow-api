---
description: Create new trade and returns trade info
---

# createTrade

<mark style="color:green;">`POST`</mark> `/trades/createTrade`

\<Description of the endpoint>

**Headers**

| Name                         | Value                 |
| ---------------------------- | --------------------- |
| Content-Type                 | `application/json`    |
| Y\_API\_KEY                  | `Public API Key`      |
| [Signature](../signature.md) | `HMAC SHA256 of Body` |

**Body**

<table><thead><tr><th width="270">Name</th><th width="100">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>send_name</code></td><td>string</td><td>Currency being sent</td></tr><tr><td><code>get_name</code></td><td>string</td><td>Currency being received</td></tr><tr><td><code>send_network</code></td><td>string</td><td>Network of currency being sent</td></tr><tr><td><code>get_network</code></td><td>string</td><td>Network of currency being received</td></tr><tr><td><code>send_value</code> or <code>get_value</code></td><td>number</td><td>Amount of the exchange you will receive or pay</td></tr><tr><td><code>get_creds</code></td><td>string</td><td>Сredentials</td></tr></tbody></table>

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
	"send_name": "USDT",
	"send_network": "TRC20",
	"get_network": "ERC20",
	"uniq_id": "0sv0c0c02da105aa6b7fbzf1zv05444d8a0ccd4c",
	"status": 1,
	"payment_wallet": "WalletForPay",
	"userPaidHash": "someHash",
	"ourHash": "someHash",
	"get_creds": "WalletForRecive",
	"network_commission": 0,
	"date": 1720120863,
	"time_expire": 1720142463,
	"send_value": "112",
	"get_value": "100"
}
```
{% endtab %}

{% tab title="40X" %}
```json
{
	"statusCode": 40X,
	"message": "Some error message"
}
```
{% endtab %}
{% endtabs %}

#### Example

{% tabs %}
{% tab title="JavaScript Fetch" %}
```javascript
const fetch = require('node-fetch');

let url = 'https://localhost:3000/trades/createTrade';

let options = {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    Y_API_KEY: 'Your API Key',
    Signature: '0002b135569a4a29b7e7bf9489114eca8fa31e7f61a9e8e26b89bb7dfd4dcf5c'
  },
  body: '{"send_name":"USDT","get_name":"USDT","send_value":100,"send_network":"TRC20","get_network":"ERC20"}'
};

fetch(url, options)
  .then(res => res.json())
  .then(json => console.log(json))
  .catch(err => console.error('error:' + err));
```
{% endtab %}

{% tab title="JavaScript Axios" %}
```javascript
var axios = require("axios").default;

var options = {
  method: 'POST',
  url: '/trades/createTrade',
  headers: {
    'Content-Type': 'application/json',
    Y_API_KEY: 'Your API Key',
    Signature: '0002b135569a4a29b7e7bf9489114eca8fa31e7f61a9e8e26b89bb7dfd4dcf5c'
  },
  data: {
    send_name: 'USDT',
    get_name: 'USDT',
    send_value: 100,
    send_network: 'TRC20',
    get_network: 'ERC20'
  }
};

axios.request(options).then(function (response) {
  console.log(response.data);
}).catch(function (error) {
  console.error(error);
});
```
{% endtab %}

{% tab title="Python" %}
```python
import requests

url = "https://localhost:3000/trades/createTrade"

payload = {
    "send_name": "USDT",
    "get_name": "USDT",
    "send_value": 100,
    "send_network": "TRC20",
    "get_network": "ERC20"
}
headers = {
    "Content-Type": "application/json",
    "Y_API_KEY": "Your API Key",
    "Signature": "0002b135569a4a29b7e7bf9489114eca8fa31e7f61a9e8e26b89bb7dfd4dcf5c"
}

response = requests.request("POST", url, json=payload, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="cURL" %}
```bash
curl --request POST \
  --url /trades/createTrade \
  --header 'Content-Type: application/json' \
  --header 'Signature: 0002b135569a4a29b7e7bf9489114eca8fa31e7f61a9e8e26b89bb7dfd4dcf5c' \
  --header 'Y_API_KEY: Your API Key' \
  --data '{"send_name": "USDT", "get_name": "USDT", "send_value": 100, "send_network": "TRC20", "get_network": "ERC20"}'
```
{% endtab %}
{% endtabs %}

