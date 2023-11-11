---
description: External anti-cheat for your games
cover: ../.gitbook/assets/gitbookcover.png
coverY: 0
layout:
  cover:
    visible: true
    size: hero
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# About

**NexGuard** is an innovative solution for your projects.&#x20;



What this anti-cheat can do:

* Checking connected dlls to the game process
* Working with API
* Keeping logs and sending them to the server
* Ability to communicate with [**SCREW API**](../api/about.md), view suspicious dlls and their statistics
* When working with [**SCREW API**](../api/about.md), the ability to permanently block dlls and set rules of behavior (Issuing an unconditional block to a player, an error starting the game, maintaining an increased log and recording game actions)

Anti-cheat is fully adapted to any game engine, unlike its analogues (EAC, Battleye, etc.).&#x20;

It doesn't have an SDK and works exclusively using WinAPI, which makes it a little complicated to set up, but you can connect it to any engine, even your own.&#x20;

The anti-cheat was tested on games written in Unity, Unreal Engine 5, Godot and the Clickteam Fusion constructor.

Next, read how to set it up: [Setup](setup.md)
