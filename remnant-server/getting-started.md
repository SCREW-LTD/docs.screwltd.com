---
description: This document describes the steps to create your own server in REMNANT
---

# Getting Started

Download the server assembly from the [official repository on GitHub](https://github.com/SCREW-LTD/REMNANT-server-launcher) and unpack the server for the OC you need.

In the `Linux` and `Windows` folders you will find the `server.cfg` file. He is responsible for setting up the server.

## Server Configuration

This subsection will describe what the lines in your server's configuration file are responsible for.

`[Header]` — Gives a name to your server (e.g. `[Header]="My cool server"`)

`[MaxPlayers]` — Sets the maximum number of players on your server (e.g. `[MaxPlayers]=`[`250`](#user-content-fn-1)[^1])

`[ServerPort]` — Sets the port for your server (e.g. `[ServerPort]=25565`)

`[DisablePlayerDamage]` — Disables taking damage from players (e.g. `[DisablePlayerDamage]=`[`true`](#user-content-fn-2)[^2])

`[AllowNight]` — Disables change from day to night (e.g. `[AllowNight]=false`)

`[SteamCheckup]` — Enables checking each client by their unique SteamId64. When enabled, you exclude game clients obtained by hacking and give access to players who have purchased the game. We recommend that you leave this setting enabled (e.g. `[SteamCheckup]=`[`true`](#user-content-fn-3)[^3])

`[AllowEAC]` — Enables checking players with EasyAntiCheat. We recommend that you leave this setting enabled (e.g. `[AllowEAC]=true`)

`[GameMode]` — Sets the default game mode. Of the available there are sandbox, deathmatch (e.g. `[GameMode]=`[`sandbox`](#user-content-fn-4)[^4] )

`[UseFriendSystem]` — Enables the friendship system on the server. If this option is enabled, the player will first need to make friends with him in order to see the nickname of another player (e.g. `[UseFriendSystem]=false`)

`[AllowRepeatingNames]` — If enabled, duplicate names will not be assigned a digit. It will be possible to distinguish clients only by a unique ID (e.g. `[AllowRepeatingNames]=`[`false`](#user-content-fn-5)[^5])

`[CustomMap]` — TEMPORARILY NOT WORKING! An experimental feature that will allow you to specify the path to your own map (e.g. `[CustomMap]=maps/mymap.map`)

`[Webhooks]` — Specify in this paragraph a link to your url handler to receive notifications about the server status (e.g. `[Webhooks]=`[`null`](#user-content-fn-6)[^6])

`[UsePlugins]` — Enables and starts server applications. Keep your plugins only in the `plugins/` folder at the root (e.g. `[UsePlugins]=true`)

`[ServerLogo]` — Specify the name of the image of your server uploaded to its directory (e.g. `[ServerLogo]=`[`myserverlogo.png`](#user-content-fn-7)[^7])

`[ServerMaxRamUsage]` — Sets a limit on the use of RAM in megabytes (e.g. `[ServerMaxRamUsage]=16384`)

`[ServerMaxDriveUsage]` — Sets the disk memory usage limit in megabytes (e.g. `[ServerMaxDriveUsage]=65536`)

`[AdminGodMode]` — Forces all administrators into immortality mode (e.g. `[AdminGodMode]=false`)

`[AllowQueue]` — When enabled, allows users to be in queue mode if the server is full (e.g. `[AllowQueue]=`[`true`](#user-content-fn-8)[^8])

`[ConnectTimeout]` — Sets the maximum amount of time to wait for a response from the client to the server in milliseconds (e.g. `[ConnectTimeout]=300000`)

`[AfkTimeout]` — Sets the maximum amount of idle time for a player in milliseconds (e.g. `[AfkTimeout]=`[`300000`](#user-content-fn-9)[^9])

`[DisableVehicles]` — Disables the ability to use all vehicles on the server (e.g. `[DisableVehicles]=false`)

`[WaterKill]` — When enabled, kills the player when they enter the ocean (e.g. `[WaterKill]=`[`false`](#user-content-fn-10)[^10])

`[DisableRagdoll]` — Disables all ragdoll on the server. It has a great effect on the performance of the server and all connected clients, but makes the game less realistic and dynamic. We recommend disabling it solely for performance reasons. (e.g. `[DisableRagdoll]=false`)

`[DisableBotPlayers]` — Removes all AI people from the server (e.g. `[DisableBotPlayers]=`[`false`](#user-content-fn-11)[^11])

`[DisableBotVehicles]` — Removes all AI vehicles from the server (e.g. `[DisableBotVehicles]=false`)

`[VehiclesSpawnRate]` — Sets the maximum number of AI vehicles on the server. Default is 2000 (e.g. `[VehiclesSpawnRate]=`[`2000`](#user-content-fn-12)[^12])

`[BotSpawnRate]` — Sets the maximum number of AI peoples on the server. Default is 16000 (e.g. `[VehiclesSpawnRate]=16000`)

`[AllowHandguns]` — Allows use handguns on the server (e.g. `[AllowHandguns]=`[`true`](#user-content-fn-13)[^13])

`[AllowRifles]` — Allows use rifles on the server (e.g. `[AllowRifles]=true`)

`[AllowSnipers]` — Allows use snipers on the server (e.g. `[AllowSnipers]=`[`true`](#user-content-fn-14)[^14])

`[AllowShotguns]` — Allows use shotguns on the server (e.g. `[AllowShotguns]=true`)

`[ServerTickRate]` — Sets the number of server updates per second. The higher the value, the better the shots and other player interactions on the server are registered. A high score significantly degrades server performance. We recommend setting it to 96 or choosing the optimal value for each server yourself (e.g. `[ServerTickRate]=`[`96`](#user-content-fn-15)[^15])

`[ServerOwnerIds]` — Enter the unique SteamId64 of users who can use the administrator tools on the server (e.g. `[ServerOwnerIds]=76561198268835196`)

`[ServerRconPassword]` — Enables the ability to send commands to the console via the RCON client. Set your password with quotes (e.g. `[ServerRconPassword]=null`)

`[DisableMobileApp]` — Disconnects your server from the REMNANT: MOBILE app. Statistics from your server will not be displayed in this app (e.g. `[DisableMobileApp]=`[`false`](#user-content-fn-16)[^16])

`[RemoveWindowsPlayers]` — Prevents Windows players from entering your server (e.g. `[RemoveWindowsPlayers]=false`)

`[RemoveMacPlayers]` — Prevents Mac players from entering your server (e.g. `[RemoveMacPlayers]=`[`false`](#user-content-fn-17)[^17])

`[RemoveLinuxPlayers]` — Prevents Linux players from entering your server (e.g.`[RemoveLinuxPlayers]=false`)

`[RemoveAndroidPlayers]` — Prevents Android players from entering your server (e.g. `[RemoveAndroidPlayers]=`[`false`](#user-content-fn-18)[^18])

`[RemoveIosPlayers]` — Prevents IOS players from entering your server (e.g. `[RemoveIosPlayers]=false`)

`[RemoveXboxPlayers]` — Prevents Xbox players from entering your server (e.g. `[RemoveXboxPlayers]=`[`false`](#user-content-fn-19)[^19])

`[RemovePlayStationPlayers]` — Prevents Play Station players from entering your server (e.g. `[RemovePlayStationPlayers]=false`)

`[ServerPassword]` — Sets a password on your server that you will need to specify before connecting. Write your password in quotes (e.g. `[ServerPassword]=`[`null`](#user-content-fn-20)[^20])

`[ServerAutoSaveRate]` — Sets the server save speed in milliseconds. Default is 300000 (e.g. `[ServerAutoSaveRate]=300000`)

`[ServerLogLevel]` — Sets the logging level of the server. The higher the number, the more information the console will output. Default is 3 (e.g. `[ServerLogLevel]=`[`3`](#user-content-fn-21)[^21])

`[TrustServerCommands]` — Enables encryption of data in transit from the server to the client and from the client to the server. The function slightly degrades performance, but leads to minimization of server file leaks and DDoS attacks. We recommend leaving it enabled. Turn it off only if you know what you're doing (e.g. `[TrustServerCommands]=true`)

`[Whitelist]` — Enables whitelisting on the server (e.g. `[Whitelist]=`[`true`](#user-content-fn-22)[^22])

{% file src="../.gitbook/assets/server.cfg" %}
default `server.cfg` file
{% endfile %}

[^1]: 1-10000

[^2]: true/false

[^3]: true/false

[^4]: sandbox/deathmatch

[^5]: true/false

[^6]: null is disables webhooks

[^7]: null is disables this feature

[^8]: true/false

[^9]: null is disables this feature

[^10]: true/false

[^11]: true/false

[^12]: 1-50000

[^13]: true/false

[^14]: true/false

[^15]: 16-256

[^16]: true/false

[^17]: true/false

[^18]: true/false

[^19]: true/false

[^20]: null is disables webhooks

[^21]: 0-3

[^22]: true/false
