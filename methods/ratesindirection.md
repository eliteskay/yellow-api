---
description: Returns rates in a certain direction
---

# ratesInDirection

<mark style="color:green;">`GET`</mark> `/trades/ratesInDirection`

**Headers**

| Name                         | Value                 |
| ---------------------------- | --------------------- |
| Content-Type                 | `application/json`    |
| Y\_API\_KEY                  | `Public API Key`      |
| [Signature](../signature.md) | `HMAC SHA256 of Body` |

**Body**

| Name        | Type   | Description |
| ----------- | ------ | ----------- |
| `direction` | string | Direction   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
	"name": "Tether",
	"withdraw_networks": {
		"ARBITRUM": "0.50000000",
		"ERC20": "0.63000000",
		"TRC20": "1.70000000",
		"AVALANCHE": "0.01000000",
		"SOL": "0.20000000",
		"BEP20": "0.30000000",
		"POLYGON": "0.01000000"
	},
	"min_withdraw": {
		"ARBITRUM": "1.00000000",
		"ERC20": "50.00000000",
		"TRC20": "1.00000000",
		"AVALANCHE": "1.00000000",
		"SOL": "1.00000000",
		"BEP20": "1.00000000",
		"POLYGON": "0.50000000"
	},
	"deposit_networks": {
		"TON": "0.00",
		"BEP20": "0.00",
		"ERC20": "0.00",
		"ARBITRUM": "0.00",
		"TRC20": "0.00",
		"SOL": "0.00",
		"AVALANCHE": "0.00",
		"POLYGON": "0.00"
	},
	"min_deposit": {
		"TON": "1.00000000",
		"BEP20": "0.50000000",
		"ERC20": "1.00000000",
		"ARBITRUM": "1.00000000",
		"TRC20": "1.00000000",
		"SOL": "1.00000000",
		"AVALANCHE": "1.00000000",
		"POLYGON": "0.50000000"
	},
	"to": {
		"SOL": 0.006061761,
		"TON": 0.11638302299999999,
		"BCH": 0.00225801,
		"XMR": 0.0052963739999999995,
		"LTC": 0.011812995,
		"DASH": 0.03600765,
		"VERSE": 4609.57534956,
		"AVAX": 0.030214152,
		"BTC": 0.000014157,
		"MATIC": 1.582416,
		"DOGE": 7.1322836579999995,
		"DAI": 0.888684822,
		"SBERRUB": 77.994,
		"SBPRUB": 76.824,
		"USDT": 0.891,
		"USDC": 0.8888290830000001,
		"ETH": 0.000258282,
		"TRX": 7.133998554000001,
		"BNB": 0.00152442
	}
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
const options = {
  method: 'GET',
  headers: {
    'Content-Type': 'application/json',
    Y_API_KEY: 'Your API Key',
    Signature: '02fe657ed8405c521fb3d5e3fd9ef7ff92f849c9ab976dcbe25e6ec4aacae0ed'
  },
  body: '{"direction":"USDT"}'
};

fetch('https://api.yellowchanger.com/trades/ratesInDirection', options)
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
  url: 'https://api.yellowchanger.com/trades/ratesInDirection',
  headers: {
    'Content-Type': 'application/json',
    Y_API_KEY: 'Your API Key',
    Signature: '02fe657ed8405c521fb3d5e3fd9ef7ff92f849c9ab976dcbe25e6ec4aacae0ed'
  },
  data: {direction: 'USDT'}
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

url = "https://api.yellowchanger.com/trades/ratesInDirection"

payload = {"direction": "USDT"}
headers = {
    "Content-Type": "application/json",
    "Y_API_KEY": "Your API Key",
    "Signature": "02fe657ed8405c521fb3d5e3fd9ef7ff92f849c9ab976dcbe25e6ec4aacae0ed"
}

response = requests.request("GET", url, json=payload, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="cURL" %}
```bash
curl --request GET \
  --url https://api.yellowchanger.com/trades/ratesInDirection \
  --header 'Content-Type: application/json' \
  --header 'Signature: 02fe657ed8405c521fb3d5e3fd9ef7ff92f849c9ab976dcbe25e6ec4aacae0ed' \
  --header 'Y_API_KEY: Your API Key' \
  --data '{"direction": "USDT"}'
```
{% endtab %}
{% endtabs %}

