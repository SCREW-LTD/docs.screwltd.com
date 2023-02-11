---
description: Step-by-step instructions for setting up a white list
---

# Whitelist

## Feature Information

**Whitelist** — is a system for creating private servers. Only those players who have received access to enter the server by the administrator will be able to enter such servers.

When **whitelist** is enabled, your server will not appear in the server list.

Before using the **whitelist**, make sure that the `[SteamCheckup]` feature is enabled in your config file. Without it, the server will not be able to let players through, as their unique SteamId64 will not be transmitted.

## How to set up a whitelist

After setting up the config and taking into account the information above, you can start setting up the whitelist itself.

Start your server via `start.bat` or your own executable.

If a **whitelist** is enabled and has not been created, your console will notify you that the **whitelist** has been enabled and will generate an empty `whitelist.cfg` file for you.

You can add allowed clients in two ways.

{% hint style="success" %}
**Through the console.**&#x20;

Just write `whitelist.add SteamId64` to your console
{% endhint %}

{% hint style="warning" %}
**Through the whitelist.cfg.**

Open the whitelist.cfg file and write down the unique SteamId64 of allowed players, entering each identifier on a new line.



<mark style="color:orange;">**IMPORTANT!**</mark> This method has several disadvantages compared to the previous one. Added players will not be able to connect until the server is completely rebooted. Use this method only if your whitelist does not have dynamic changes.
{% endhint %}

After the done actions and activation of the **whitelist**, just send the `ip:port` of your server to the right players.&#x20;

Have a good game!
