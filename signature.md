---
description: >-
  The "Signature" header is a body converted from JSON to a string and then HMAC
  SHA256 signed with a private key.
---

# Signature

#### Example

{% tabs %}
{% tab title="JavaScript" %}
```javascript
import * as crypto from 'crypto';

function createHmacSHA256(message, key) {
  const hmac = crypto.createHmac('sha256', key);
  hmac.update(message);
  const hmacDigest = hmac.digest('hex');
  return hmacDigest;
}

const body = { "uniq_id": "0sv0c0c02da105aa6b7fbzf1zv05444d8a0ccd4c" }

console.log(createHmacSHA256(JSON.stringify(body), "Your Private Key");
```
{% endtab %}
{% endtabs %}
