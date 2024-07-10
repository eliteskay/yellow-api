---
description: Returns all possible exchange rates
---

# allRates

<mark style="color:green;">`GET`</mark> `/trades/allRates`

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |
| Y\_API\_KEY  | `Public API Key`   |

**Response**

{% tabs %}
{% tab title="200" %}
{% code overflow="wrap" fullWidth="false" %}
```json
{
	"SBERRUB": {
		"name": "Сбербанк",
		"withdraw_networks": {
			"RUB": 0
		},
		"min_withdraw": {
			"RUB": 9000
		},
		"deposit_networks": {},
		"min_deposit": {},
		"to": {
			"SOL": 0.009000000000000001,
			"TON": 0.117,
			"BCH": 0,
			"XMR": 0.009000000000000001,
			"LTC": 0.009000000000000001,
			"DASH": 0.036000000000000004,
			"VERSE": 4539.735,
			"AVAX": 0.027,
			"BTC": 0,
			"MATIC": 1.557,
			"DOGE": 7.029,
			"DAI": 0.873,
			"USDT": 0.882,
			"USDC": 0.873,
			"ETH": 0,
			"TRX": 7.029,
			"BNB": 0
		}
	},
...
```
{% endcode %}
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

let url = 'https://api.yellowchanger.com/trades/allRates';

let options = {
  method: 'GET',
  headers: {'Content-Type': 'application/json', Y_API_KEY: 'Your API Key'}
};

fetch(url, options)
  .then(res => res.json())
  .then(json => console.log(json))
  .catch(err => console.error('error:' + err));
```
{% endtab %}

{% tab title="JavaScript Axios" %}
```javascript
import axios from "axios";

const options = {
  method: 'GET',
  url: 'https://api.yellowchanger.com/trades/allRates',
  headers: {'Content-Type': 'application/json', Y_API_KEY: 'Your API Key'}
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

url = "https://api.yellowchanger.com/trades/allRates"

headers = {
    "Content-Type": "application/json",
    "Y_API_KEY": "Your API Key"
}

response = requests.request("GET", url, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="cURL" %}
```sh
curl --request GET \
  --url https://api.yellowchanger.com/trades/allRates \
  --header 'Content-Type: application/json' \
  --header 'Y_API_KEY: qweqwe'
```
{% endtab %}
{% endtabs %}
