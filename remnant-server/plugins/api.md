---
description: This page describes how plugins are created and their basic principles
---

# API

All plugins are written in C#.

Plugins support [Unity](https://docs.unity3d.com/Manual/index.html), [Mirror Networking](https://mirror-networking.gitbook.io/docs/) and [Steamworks Facepunch](https://wiki.facepunch.com/steamworks/) libraries

## Return Values

<mark style="color:red;">`Server.GetPlayersCount()`</mark> — Gets the number of players on the server in **int**

<mark style="color:red;">`Server.GetPlayerList()`</mark> — Gets all **SteamId64** on the server in an **array**

<mark style="color:red;">`Server.GetNameBySteamId(string id)`</mark> — Gets the player's nickname using **SteamId64** in a **string**

<mark style="color:red;">`Server.GetVehiclesCount()`</mark> — Gets the number of vehicles on the server that have been created by players in **int**

<mark style="color:red;">`Server.GetVehiclesList()`</mark> — Gets all vehicles ids on the server that have been created by players in an **array**

<mark style="color:red;">`Server.GetServerOnlineTime()`</mark> — Gets server uptime in **float**&#x20;

<mark style="color:red;">`Server.GetPluginsCount()`</mark> — Gets the number of all runned plugins to an **int**

<mark style="color:red;">`Server.GetPluginsList()`</mark> — Gets all runned plugins names on the server in an **array**

<mark style="color:red;">`Server.AddCommand(string name, string methodName)`</mark> — Gets all runned plugins names on the server in an **array**
