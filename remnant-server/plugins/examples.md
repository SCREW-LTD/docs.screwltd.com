---
description: Plugin examples for your server
---

# Examples

## Auto chat message

{% code title="autochat.cs" overflow="wrap" %}
```csharp
using System;
using REMNANT.Server;
 
class Program
{
    private string msg = "chat.say ONLINE NOW " + Server.GetPlayersCount().toString();
    private Timer _timer = null;
    private static void Main()
    {
        _timer = new Timer(TimerCallback, null, 0, 2000);
        Server.AddCommand("autochat.changemsg", "ChangeMessage");
        Console.ReadLine();
    }
    private static void TimerCallback(Object o) 
    {
        Console.WriteLine(msg);
    }
    
    private static void ChangeMessage(string a) 
    {
        msg = a;
    }
}
```
{% endcode %}

### Clear dropped items

{% code title="dropitems.cs" overflow="wrap" %}
```csharp
using System;
using REMNANT.Server;
 
class Program
{
    private Timer _timer = null;
    private static void Main()
    {
        _timer = new Timer(TimerCallback, null, 0, 600000);
        Console.ReadLine();
    }
    private static void TimerCallback(Object o) 
    {
        Console.WriteLine("dropitems.clear");
        Console.WriteLine("chat.say All dropped items deleted!");
    }
}
```
{% endcode %}

### Teleport to player

{% code title="teleport.cs" overflow="wrap" %}
```csharp
using UnityEngine;
using REMNANT.Server;
using REMNANT.Player;

public class Program 
{
    public void Teleport(string SteamId64_sender, string SteamId64_other)
    {
        bool canUseTp = ServerController.GetPerms(SteamId64_sender, "Teleport");
        if(canUseTp)
        {
            GameObject senderPlayer = ServerController.GetPlayerById(SteamId64_sender);
            GameObject otherPlayer = ServerController.GetPlayerById(SteamId64_other);
            senderPlayer.transform.position = otherPlayer.transform.position;
        }
    }
}
```
{% endcode %}
{% code title="In-game console" overflow="wrap" %}
```bash
How to use:
> server_command Teleport(me, SteamId64_other)
```
{% endcode %}

All commands can be found on the [Commands page](../commands.md).
