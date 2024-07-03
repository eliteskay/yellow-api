---
description: Returns all possible exchange destinations
---

# destinationsList

<mark style="color:green;">`GET`</mark> `/trades/destinationsList`

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |
| Y\_API\_KEY  | `Public API Key`   |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    "payin": {
      "VERSE": [
        {
          "network": "ETH",
          "limit": {
            "min_amount": "2500.00000000",
            "max_amount": "10000000.00000000"
          }
        }
      ],
      "DAI": [
        {
          "network": "ETH",
          "limit": {
            "min_amount": "1.00000000",
            "max_amount": "10000000.00000000"
          }
        },
        {
          "network": "POLYGON",
          "limit": {
            "min_amount": "1.00000000",
            "max_amount": "10000000.00000000"
          }
        },
        {
          "network": "BSC",
          "limit": {
            "min_amount": "1.00000000",
            "max_amount": "10000000.00000000"
          }
        }
      ],
...
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
  headers: {'Content-Type': 'application/json', Y_API_KEY: 'Your API Key'},
  body: 'false'
};

fetch('/trades/destinationsList', options)
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
  url: '/trades/destinationsList',
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

url = "/trades/destinationsList"

headers = {
    "Content-Type": "application/json",
    "Y_API_KEY": "Your API Key"
}

response = requests.request("GET", url, headers=headers)

print(response.text)
```
{% endtab %}

{% tab title="cURL" %}
```bash
curl --request GET \
  --url /trades/destinationsList \
  --header 'Content-Type: application/json' \
  --header 'Y_API_KEY: Your API Key'
```
{% endtab %}
{% endtabs %}

