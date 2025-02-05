---
description: Text generation neural network.
---

# Capricorn AI

Best models:

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Capricorn Mini</strong></td><td>The fastest model. </td><td>Suitable for those who value response speed</td></tr><tr><td><strong>Capricorn (4.3)</strong></td><td>Latest model.</td><td>Has functions and better text generation</td></tr></tbody></table>

All models you can use: `Mini`, `3.8`, `4`, `4.1`, `4.2`, `4.3`, `4.3F`

***

## Chat response

<mark style="color:green;">`POST`</mark> [`https://api.screwltd.com/v3/ai/generate`](https://api.screwltd.com/v3/ai/generate)

Makes a request to the Capricorn AI.

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |
| X-API-KEY    | `uuid`             |

**Body**

| Name                                         | Type     | Description                            |
| -------------------------------------------- | -------- | -------------------------------------- |
| `message`<mark style="color:red;">`*`</mark> | string   | Message requiring a response           |
| `version`<mark style="color:red;">`*`</mark> | 3.8 or 4 | Selects model version                  |
| `instructions`                               | string   | Instructions for the bot               |
| `history`                                    | array    | Chat history                           |
| `chatId`                                     | uuid     | Chat history ID saved in the cloud.    |
| `userData`                                   | json     | Information about the current user     |
| `temperature`                                | int      | Creativity of the answer, from 0 to 2. |
| `files`                                      | byte\[]  | An array of files for AI analysis.     |

Using the `history` attribute together with `chatId` is not possible. Please save the data either on our servers or on your own resources.

{% code title="Local save" %}
```json
{
  "message": "Hello!",
  "instructions": "Use a formal communication style",
  "version": "4.3",
  "temperature": 0.7,
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
  "temperature": 0.7,
  "version": "4.3",
  "chatId": "uuid"
}
```
{% endcode %}

All models have **machine vision**. You can send up to **10** `pictures`/`audio`/`video` for neural network analysis.

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "text": "Hello my friend!",
  "duration": "0.00 ms"
}
```
{% endtab %}

{% tab title="200 (with functions)" %}
```json
{
  "text": "Hello my friend!",
  "duration": "0.00 ms",
  "func": "name" //e.g. fetchApi
}
```
{% endtab %}

{% tab title="500" %}
```json
{
  "error": "Capricorn was unable to generate text..."
}
```
{% endtab %}
{% endtabs %}
