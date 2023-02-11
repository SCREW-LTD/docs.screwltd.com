---
description: This document describes the steps to create your own server in REMNANT
---

# Getting Started

Download the server assembly from the [official repository on GitHub](https://github.com/SCREW-LTD/REMNANT-server-launcher) and unpack the server for the OC you need.

In the `Linux` and `Windows` folders you will find the `server.cfg` file. He is responsible for setting up the server.

## Server Configuration

This subsection will describe what the lines in your server's configuration file are responsible for.

`[Header]` —  Gives a name to your server (e.g. `[Header]="My cool server"`)

`[MaxPlayers]` — Sets the maximum number of players on your server (e.g. `[MaxPlayers]=`[`250`](#user-content-fn-1)[^1])

`[ServerPort]` — Sets the port for your server (e.g. `[ServerPort]=`[`25565`](#user-content-fn-2)[^2])

`[DisablePlayerDamage]` — Disables taking damage from players (e.g. `[DisablePlayerDamage]=`[`true`](#user-content-fn-3)[^3])

`[AllowNight]` — Disables change from day to night (e.g. `[AllowNight]=`[`false`](#user-content-fn-4)[^4])

`[SteamCheckup]` — Enables checking each client by their unique SteamId64. When enabled, you exclude game clients obtained by hacking and give access to players who have purchased the game. We recommend that you leave this setting enabled (e.g. `[SteamCheckup]=`[`true`](#user-content-fn-5)[^5])

`[AllowEAC]` — Enables checking players with EasyAntiCheat. We recommend that you leave this setting enabled (e.g. `[AllowEAC]=`[`true`](#user-content-fn-6)[^6])

`[GameMode]` — Sets the default game mode. Of the available there are sandbox, deathmatch (e.g. `[GameMode]=`[`sandbox`](#user-content-fn-7)[^7] )

`[UseFriendSystem]` — Enables the friendship system on the server. If this option is enabled, the player will first need to make friends with him in order to see the nickname of another player (e.g. `[UseFriendSystem]=`[`false`](#user-content-fn-8)[^8])

`[AllowRepeatingNames]` — If enabled, duplicate names will not be assigned a digit. It will be possible to distinguish clients only by a unique ID (e.g. `[AllowRepeatingNames]=`[`false`](#user-content-fn-9)[^9])

`[CustomMap]` — TEMPORARILY NOT WORKING! An experimental feature that will allow you to specify the path to your own map (e.g. `[CustomMap]=`[`maps/mymap.map`](#user-content-fn-10)[^10])

`[Webhooks]` — Specify in this paragraph a link to your url handler to receive notifications about the server status (e.g. `[Webhooks]=`[`null`](#user-content-fn-11)[^11])

`[UsePlugins]` — Enables and starts server applications. Keep your plugins only in the `plugins/` folder at the root (e.g. `[UsePlugins]=`[`true`](#user-content-fn-12)[^12])

`[ServerLogo]` — Specify the name of the image of your server uploaded to its directory (e.g. `[ServerLogo]=`[`myserverlogo.png`](#user-content-fn-13)[^13])

`[ServerMaxRamUsage]` — Sets a limit on the use of RAM in megabytes (e.g. `[ServerMaxRamUsage]=16384`)

`[ServerMaxDriveUsage]` — Sets the disk memory usage limit in megabytes (e.g. `[ServerMaxDriveUsage]=65536`)

`[AdminGodMode]` — Forces all administrators into immortality mode (e.g. `[AdminGodMode]=`[`false`](#user-content-fn-14)[^14])

`[AllowQueue]` — When enabled, allows users to be in queue mode if the server is full (e.g. `[AllowQueue]=`[`true`](#user-content-fn-15)[^15])

`[ConnectTimeout]` — Sets the maximum amount of time to wait for a response from the client to the server in milliseconds (e.g. `[ConnectTimeout]=`[`300000`](#user-content-fn-16)[^16])

`[AfkTimeout]` — Sets the maximum amount of idle time for a player in milliseconds (e.g. `[AfkTimeout]=`[`300000`](#user-content-fn-17)[^17])

`[DisableVehicles]` — Disables the ability to use all vehicles on the server (e.g. `[DisableVehicles]=`[`false`](#user-content-fn-18)[^18])

`[WaterKill]` — When enabled, kills the player when they enter the ocean (e.g. `[WaterKill]=`[`false`](#user-content-fn-19)[^19])

`[DisableRagdoll]` — Disables all ragdoll on the server. It has a great effect on the performance of the server and all connected clients, but makes the game less realistic and dynamic. We recommend disabling it solely for performance reasons. (e.g. `[DisableRagdoll]=`[`false`](#user-content-fn-20)[^20])

`[DisableBotPlayers]` — Removes all AI people from the server (e.g. `[DisableBotPlayers]=`[`false`](#user-content-fn-21)[^21])

`[DisableBotVehicles]` — Removes all AI vehicles from the server (e.g. `[DisableBotVehicles]=`[`false`](#user-content-fn-22)[^22])

`[VehiclesSpawnRate]` — Sets the maximum number of AI vehicles on the server. Default is 2000 (e.g. `[VehiclesSpawnRate]=`[`2000`](#user-content-fn-23)[^23])

`[BotSpawnRate]` — Sets the maximum number of AI peoples on the server. Default is 16000 (e.g. `[VehiclesSpawnRate]=`[`16000`](#user-content-fn-24)[^24])

`[AllowHandguns]` — Allows use handguns on the server (e.g. `[AllowHandguns]=`[`true`](#user-content-fn-25)[^25])

`[AllowRifles]` — Allows use rifles on the server (e.g. `[AllowRifles]=`[`true`](#user-content-fn-26)[^26])

`[AllowSnipers]` — Allows use snipers on the server (e.g. `[AllowSnipers]=`[`true`](#user-content-fn-27)[^27])

`[AllowShotguns]` — Allows use shotguns on the server (e.g. `[AllowShotguns]=`[`true`](#user-content-fn-28)[^28])

`[ServerTickRate]` — Sets the number of server updates per second. The higher the value, the better the shots and other player interactions on the server are registered. A high score significantly degrades server performance. We recommend setting it to 96 or choosing the optimal value for each server yourself (e.g. `[ServerTickRate]=`[`96`](#user-content-fn-29)[^29])

`[ServerOwnerIds]` — Enter the unique SteamId64 of users who can use the administrator tools on the server (e.g. `[ServerOwnerIds]=76561198268835196`)

`[ServerRconPassword]` — Enables the ability to send commands to the console via the RCON client. Set your password with quotes (e.g. `[ServerRconPassword]=`[`null`](#user-content-fn-30)[^30])

`[DisableMobileApp]` — Disconnects your server from the REMNANT: MOBILE app. Statistics from your server will not be displayed in this app (e.g. `[DisableMobileApp]=`[`false`](#user-content-fn-31)[^31])

`[RemoveWindowsPlayers]` — Prevents Windows players from entering your server (e.g. `[RemoveWindowsPlayers]=`[`false`](#user-content-fn-32)[^32])

`[RemoveMacPlayers]` — Prevents Mac players from entering your server (e.g. `[RemoveMacPlayers]=`[`false`](#user-content-fn-33)[^33])

`[RemoveLinuxPlayers]` — Prevents Linux players from entering your server (e.g.`[RemoveLinuxPlayers]=`[`false`](#user-content-fn-34)[^34])

`[RemoveAndroidPlayers]` — Prevents Android players from entering your server (e.g. `[RemoveAndroidPlayers]=`[`false`](#user-content-fn-35)[^35])

`[RemoveIosPlayers]` — Prevents IOS players from entering your server (e.g. `[RemoveIosPlayers]=`[`false`](#user-content-fn-36)[^36])

`[RemoveXboxPlayers]` — Prevents Xbox players from entering your server (e.g. `[RemoveXboxPlayers]=`[`false`](#user-content-fn-37)[^37])

`[RemovePlayStationPlayers]` — Prevents Play Station players from entering your server (e.g. `[RemovePlayStationPlayers]=`[`false`](#user-content-fn-38)[^38])

`[ServerPassword]` — Sets a password on your server that you will need to specify before connecting. Write your password in quotes (e.g. `[ServerPassword]=`[`null`](#user-content-fn-39)[^39])

`[ServerAutoSaveRate]` — Sets the server save speed in milliseconds. Default is 300000 (e.g. `[ServerAutoSaveRate]=`[`300000`](#user-content-fn-40)[^40])

`[ServerLogLevel]` — Sets the logging level of the server. The higher the number, the more information the console will output. Default is 3 (e.g. `[ServerLogLevel]=`[`3`](#user-content-fn-41)[^41])

`[TrustServerCommands]` — Enables encryption of data in transit from the server to the client and from the client to the server. The function slightly degrades performance, but leads to minimization of server file leaks and DDoS attacks. We recommend leaving it enabled. Turn it off only if you know what you're doing (e.g. `[TrustServerCommands]=`[`true`](#user-content-fn-42)[^42])

`[Whitelist]` — Enables whitelisting on the server (e.g. `[Whitelist]=`[`true`](#user-content-fn-43)[^43])

{% file src="../.gitbook/assets/server.cfg" %}
default `server.cfg` file
{% endfile %}

[^1]: 1-10000

[^2]: 0-65535

[^3]: true/false

[^4]: true/false

[^5]: true/false

[^6]: true/false

[^7]: sandbox/deathmatch

[^8]: true/false

[^9]: true/false

[^10]: null is disables this feature

[^11]: null is disables webhooks

[^12]: true/false

[^13]: null is disables this feature

[^14]: true/false

[^15]: true/false

[^16]: \>30000

[^17]: null is disables this feature

[^18]: true/false

[^19]: true/false

[^20]: true/false

[^21]: true/false

[^22]: true/false

[^23]: 1-50000

[^24]: 1-50000

[^25]: true/false

[^26]: true/false

[^27]: true/false

[^28]: true/false

[^29]: 16-256

[^30]: null is disables webhooks

[^31]: true/false

[^32]: true/false

[^33]: true/false

[^34]: true/false

[^35]: true/false

[^36]: true/false

[^37]: true/false

[^38]: true/false

[^39]: null is disables webhooks

[^40]: \>30000

[^41]: 0-3

[^42]: true/false

[^43]: true/false
