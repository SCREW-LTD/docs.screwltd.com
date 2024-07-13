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

| Name           | Type   | Description                         |
| -------------- | ------ | ----------------------------------- |
| `message`      | string | Message requiring a response        |
| `instructions` | string | Instructions for the bot            |
| `history`      | array  | Chat history                        |
| `chatId`       | uuid   | Chat history ID saved in the cloud. |

Using the `history` attribute together with `chatId` is not possible. Please save the data either on our servers or on your own resources.

{% code title="Local save" %}
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
{% endcode %}

{% code title="Cloud save" %}
```json
{
  "message": "Hello!",
  "instructions": "Use a formal communication style",
  "chatId": "uuid"
}
```
{% endcode %}

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
