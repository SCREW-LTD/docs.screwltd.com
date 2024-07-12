---
description: Integration examples
---

# How to use

***

## Chat response

<mark style="color:green;">`POST`</mark> [`https://api.screwltd.com/v3/ai/generate`](https://api.screwltd.com/v3/ai/generate)

Makes a request to the Capricorn neural network.

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

| Name           | Type   | Description                  |
| -------------- | ------ | ---------------------------- |
| `message`      | string | Message requiring a response |
| `instructions` | string | Instructions for the bot     |
| `history`      | array  | Chat history                 |

```json
{
  "message": "Hello!",
  "instructions": "Use a formal communication style",
  "history": [
    {
      "role": "user",
      "parts": [{"text": ""}]
    },
    {
      "role": "model",
      "parts": [{"text": ""}]
    }
  ]
}
```

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "text": "Hello my friend!"
}
```
{% endtab %}

{% tab title="500" %}
```json
{
  "error": "Failed to fetch data"
}
```
{% endtab %}
{% endtabs %}
