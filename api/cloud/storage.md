---
description: Cloud storage
---

# Storage

***

## Upload file

<mark style="color:green;">`POST`</mark> [`https://api.screwltd.com/v3/cloud/storage/upload`](https://api.screwltd.com/v3/cloud/storage/upload)

Uploads a file to the server

**Headers**

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Body**

| Name   | Type    | Description            |
| ------ | ------- | ---------------------- |
| `file` | byte\[] | File to be transferred |

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
    message: "File uploaded successfully",
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}

***

## Get file

<mark style="color:green;">`GET`</mark> [`https://api.screwltd.com/v3/cloud/storage/get/:filename`\
](https://api.screwltd.com/v3/cloud/storage/get/:filename)

Download a file from storage

**Params**

| Name        | Type   | Description      |
| ----------- | ------ | ---------------- |
| `:filename` | string | Name of the file |

**Response**

{% tabs %}
{% tab title="400" %}
```json
{
  "error": "File not found"
}
```
{% endtab %}
{% endtabs %}
