---
description: Text generation neural network
---

# Capricorn

Avalible models:

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th></tr></thead><tbody><tr><td><strong>Capricorn (3.8)</strong></td><td>The fastest model. </td><td>Suitable for those who value response speed.</td></tr><tr><td><strong>Capricorn (4.0)</strong></td><td>Latest model.</td><td>Smarter than his predecessor, but takes longer to respond.</td></tr></tbody></table>

***

## Chat response

<mark style="color:green;">`POST`</mark> [`https://api.screwltd.com/v3/ai/generate`](https://api.screwltd.com/v3/ai/generate)

Makes a request to the Capricorn AI.

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |
| X-API-KEY    | `api/uuid`         |

**Body**

| Name                                         | Type     | Description                         |
| -------------------------------------------- | -------- | ----------------------------------- |
| `message`<mark style="color:red;">`*`</mark> | string   | Message requiring a response        |
| `version`<mark style="color:red;">`*`</mark> | 3.8 or 4 | Selects model version               |
| `instructions`                               | string   | Instructions for the bot            |
| `history`                                    | array    | Chat history                        |
| `chatId`                                     | uuid     | Chat history ID saved in the cloud. |
| `userData`                                   | json     | Information about the current user  |

Using the `history` attribute together with `chatId` is not possible. Please save the data either on our servers or on your own resources.

{% code title="Local save" %}
```json
{
  "message": "Hello!",
  "instructions": "Use a formal communication style",
  "version": "3.8",
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
  "version": "3.8",
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
