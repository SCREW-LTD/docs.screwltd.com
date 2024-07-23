# Captcha

***

## Create a new user

<mark style="color:green;">`GET`</mark> [`https://api.screwltd.com/v3/captcha/generate`](https://api.screwltd.com/v3/captcha/generate)

Captcha generation

| Name          | Value              |
| ------------- | ------------------ |
| Content-Type  | `application/json` |
| Authorization | `Bearer <token>`   |

**Response**

{% tabs %}
{% tab title="400" %}
```json
{
  "error": "Invalid request"
}
```
{% endtab %}
{% endtabs %}

***

## Captcha validity check

<mark style="color:green;">`POST`</mark> [`https://api.screwltd.com/v3/captcha/generate/verify`](https://api.screwltd.com/v3/captcha/generate/verify)

Checks the correctness of the passage

**Headers**

| Name         | Value              |
| ------------ | ------------------ |
| Content-Type | `application/json` |

**Body**

<table><thead><tr><th>Name</th><th width="150">Type</th><th>Description</th></tr></thead><tbody><tr><td><code>token</code></td><td>uuid</td><td>Captcha ID (valid for 5 minutes)</td></tr><tr><td><code>captcha</code></td><td>string</td><td>Data entered by the user</td></tr></tbody></table>

**Response**

{% tabs %}
{% tab title="200" %}
```json
{
  "success": true, 
  "message": "CAPTCHA passed"
}
```
{% endtab %}

{% tab title="400" %}
```json
{
  "success": false, 
  "message": "CAPTCHA failed"
}
```
{% endtab %}
{% endtabs %}

***

## Example integration

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CAPTCHA Integration</title>
</head>
<body>
    <form id="captchaForm">
        <img id="captchaImage" alt="CAPTCHA">
        <input type="text" id="captchaInput" name="captcha" placeholder="Enter CAPTCHA">
        <input type="hidden" id="captchaToken" name="token">
        <button type="submit">Submit</button>
    </form>
    <p id="captchaResult"></p>

    <script>
        function loadCaptcha() {
            fetch('https://api.screwltd.com/v3/captcha/generate')
                .then(response => response.json())
                .then(data => {
                    document.getElementById('captchaImage').src = 'data:image/svg+xml;base64,' + btoa(data.captcha);
                    document.getElementById('captchaToken').value = data.token;
                });
        }

        document.getElementById('captchaForm').addEventListener('submit', function(event) {
            event.preventDefault();

            const captchaInput = document.getElementById('captchaInput').value;
            const captchaToken = document.getElementById('captchaToken').value;

            fetch('https://api.screwltd.com/v3/captcha/verify', {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json'
                },
                body: JSON.stringify({ token: captchaToken, captcha: captchaInput })
            })
            .then(response => response.json())
            .then(data => {
                if (data.success) {
                    document.getElementById('captchaResult').innerText = 'CAPTCHA passed';
                } else {
                    document.getElementById('captchaResult').innerText = 'CAPTCHA failed';
                }
                loadCaptcha(); // Reload CAPTCHA after each submission
            });
        });

        // Load CAPTCHA on page load
        window.onload = loadCaptcha;
    </script>
</body>
</html>
```
