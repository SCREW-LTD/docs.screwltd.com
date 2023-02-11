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
using REMNANT.Console;
using REMNANT.Player;

public class TeleportToPlayerPlugin : CommandBehaviour 
{
    [Command]
    public void Teleport(string SteamId64)
    {
        bool canUseTp = ServerController.GetPerms(localPlayer.gameObject.GetComponemt<RemnantPlayerController>().SteamId, "Teleport");
        GameObject otherPlayer = ServerController.GetPlayerById(SteamId64);
        if(canUseTp)
        {
            localPlayer.gameObject. transform.position = otherPlayer.transform.position;
        }
    }
}
```
{% endcode %}

All commands can be found on the [Commands page](../commands.md).
