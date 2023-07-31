---
description: Integration examples
---

# How to use

Before you start using, you need to download the latest version of the dll:

Add dependencies to your project and move on to the next step.

{% embed url="https://github.com/SCREW-LTD/four-threading-tools/releases" %}
download lastest verison
{% endembed %}

## Code Samples

Link the dll to your project:

```csharp
using SCREW.Auth.System4TT;
```

Next, you need to generate and encode a new key for the user:

```csharp
System4TT generator = new System4TT();
string Base64Key = generator.EncodeSecretKey(generator.GenerateSecretKey());
```

Once generated, you can send this key to your application's database, or use another save method that suits you.

To authorize a user using this code, do the following:

```csharp
TwoFactorAuthenticator authenticator = new TwoFactorAuthenticator(generator.DecodeSecretKey(Base64Key));
string userInput = Console.ReadLine();
if(authenticator.VerifyAuthenticationCode(userInput))
{
    Console.WriteLine("Authentication successful!");
}
else
{
    Console.WriteLine("Authentication failed!");
}
```

Also, you can just upload the code without using encryption when checking, for debug purposes

{% hint style="warning" %}
Only upload code this way if you know what you're doing.&#x20;

By using the following command, attackers can get access to your user codes!
{% endhint %}

```csharp
string code = authenticator.GenerateAuthenticationCode();
```

Now, after integration, you can use this system in your project, then you can see the whole script: [Code snippet](code-snippet.md)
