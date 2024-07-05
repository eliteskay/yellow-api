---
description: Returns status of trade
---

# getInfo

<mark style="color:green;">`GET`</mark> `/trades/getInfo`

**Headers**

| Name                         | Value                 |
| ---------------------------- | --------------------- |
| Content-Type                 | `application/json`    |
| Y\_API\_KEY                  | `Public API Key`      |
| [Signature](../signature.md) | `HMAC SHA256 of Body` |

**Body**

| Name      | Type   | Description        |
| --------- | ------ | ------------------ |
| `uniq_id` | string | Unique ID of trade |

**Response**

{% tabs %}
{% tab title="200" %}
<pre class="language-json"><code class="lang-json"><strong>{
</strong>	"send_name": "USDT",
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


</code></pre>
{% endtab %}

{% tab title="40X" %}
<pre class="language-json"><code class="lang-json"><strong>{
</strong>	"statusCode": 40X,
	"message": "Some error message"
}
</code></pre>
{% endtab %}
{% endtabs %}

#### Example

{% tabs %}
{% tab title="JavaScript Fetch" %}
```javascript
const options = {
  method: 'GET',
  headers: {
    'Content-Type': 'application/json',
    Y_API_KEY: 'Your API Key',
    Signature: 'e4ae46c268b77ad7fb7d12da1eeb8ad3218779c52c926c63407971da7537848e'
  },
  body: '{"uniq_id":"0sv0c0c02da105aa6b7fbzf1zv05444d8a0ccd4c"}'
};

fetch('/trades/tradeStatus', options)
  .then(response => response.json())
  .then(response => console.log(response))
  .catch(err => console.error(err));
```
{% endtab %}

{% tab title="JavaScript Axios" %}
```javascript
import axios from "axios";

const options = {
  method: 'GET',
  url: '/trades/tradeStatus',
  headers: {
    'Content-Type': 'application/json',
    Y_API_KEY: 'Your API Key',
    Signature: 'e4ae46c268b77ad7fb7d12da1eeb8ad3218779c52c926c63407971da7537848e'
  },
  data: {uniq_id: '0sv0c0c02da105aa6b7fbzf1zv05444d8a0ccd4c'}
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

url = "/trades/tradeStatus"

payload = {"uniq_id": "0sv0c0c02da105aa6b7fbzf1zv05444d8a0ccd4c"}
headers = {
    "Content-Type": "application/json",
    "Y_API_KEY": "Your API Key",
    "Signature": "e4ae46c268b77ad7fb7d12da1eeb8ad3218779c52c926c63407971da7537848e"
}

response = requests.request("GET", url, json=payload, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="cURL" %}
```bash
curl --request GET \
  --url https://localhost:3000/trades/tradeStatus \
  --header 'Content-Type: application/json' \
  --header 'Signature: e4ae46c268b77ad7fb7d12da1eeb8ad3218779c52c926c63407971da7537848e' \
  --header 'Y_API_KEY: Your API Key' \
  --data '{"uniq_id":"0sv0c0c02da105aa6b7fbzf1zv05444d8a0ccd4c"}'
```
{% endtab %}
{% endtabs %}

