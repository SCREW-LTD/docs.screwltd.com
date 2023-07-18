---
description: Example code for use library
---

# Code snippet

c

```csharp
using System;
using System.IO;
using SCREW.Auth.System4TT;

class Program
{
    static void Main()
    {
        if (!File.Exists("secret.txt") && !IsFileNotEmpty("secret.txt"))
        {
            SaveSecret();
        }
        Authenticate();
    }

    static void Authenticate()
    {
        System4TT generator = new System4TT();
        TwoFactorAuthenticator authenticator = new TwoFactorAuthenticator(generator.DecodeSecretKey(File.ReadAllText("secret.txt")));
        string userInput = Console.ReadLine();
        if (authenticator.VerifyAuthenticationCode(userInput))
        {
            Console.WriteLine("Authentication successful!");
        }
        else
        {
            Console.WriteLine("Authentication failed!");
        }
    }

    static void SaveSecret()
    {
        System4TT generator = new System4TT();
        string Base64Key = generator.EncodeSecretKey(generator.GenerateSecretKey());
        File.WriteAllText("secret.txt", Base64Key);
    }

    static bool IsFileNotEmpty(string filePath)
    {
        FileInfo fileInfo = new FileInfo(filePath);
        return fileInfo.Length > 0;
    }
}
```
