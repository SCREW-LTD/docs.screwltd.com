---
description: Integration examples
---

# How to use

Before you start using, you need to download the latest version of the dll:

Add dependencies to your project and move on to the next step.

{% embed url="https://github.com/SCREW-LTD/screw-api-client/releases" %}
download lastest verison
{% endembed %}

## Code Samples

Link the dll to your project:

```csharp
using SCREW.Api;
```

Now you can connect to the API server:

```csharp
ScrewApiClient client = new ScrewApiClient();
```

Before you start using the library, you must authenticate once in our system and create an application.&#x20;

You can do this with a simple request, or use our plugin for Unity (currently in development):

```csharp
string credentials = await client.Authenticate(username, password);
string[] credentialsData = credentials.Split('|');
string access_key = credentialsData[0];
string api_key = credentialsData[1];
```

Now let's create an application and get its secret key:

```csharp
string app_key = await client.CreateAppKey(access_key);
```

Congratulations! Your application has been created! It has 5000 activations.&#x20;

By default, one account can have up to three keys.&#x20;

To increase the volume of activations, you can purchase them on the site (temporarily unavailable).&#x20;

1000 activations cost $10.

To check activations, enter the following:

```csharp
await client.CheckAppKeyActivations(app_key);
```

**Now let's deploy the authentication system in your app:**

```csharp
if(await client.AuthenticateApp("app_key", "api_key", username, password))
{
    //Successfull
}
else
{
    //Authentification failed
}
```

This code represents username and password.&#x20;

This is not your personal data, this is the data of the user who uses your application.&#x20;

Our API creates a profile for it in your application and you can authenticate.
