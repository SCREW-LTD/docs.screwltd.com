---
description: Full anti-cheat setup
---

# Setup

### Access

Initially, to access all features you will need to request access to the anti-cheat on our website.&#x20;

Access is quite easy to obtain, but there are a couple of criteria:

* Your project must have multiplayer
* Copyright logo "SCREW LTD." must be present in your project
* Your project must be 70% complete or more (a skeptical figure, meaning that the project must look at least like a playable prototype)

### Project setup

Once you have access, let's look at a few steps to initially set up your project:

* Install the build of your project on Windows x64 architecture
* When using .NET engines, you must use .NET Framework version 4 or later
* Find out what dlls your project uses (more details here) and what system dlls it needs (this is needed to create a whitelist)
* If desired, create background and logo images in .png format



### NexGuard files

And so, after the initial setup, let’s look at the settings of the anti-cheat itself. There is a config.ini file in the NexGuard folder, let's look at it:

```ini
[Game Settings]
ExecutionFile=""
DefaultArguments=""
```

Let's look at each point

**ExecutionFile** — the name of your application's executable and process to search for.

Example based on popular games: csgo, hl2, RustClient, Fortnite.

It is important to consider the syntax; if you did everything correctly, your game will start after running the anti-cheat.



**DefaultArguments** — optional field, used to create starting arguments.&#x20;

For example: `-windowed` `-d3d9` etc.

### Dashboard

Now let's move on to the control panel!

You can use your API and custom control panel if your project is larger than the criteria specified at the beginning, otherwise you are limited to the **SCREW API**.&#x20;

It's actually not that bad! In fact, the only thing that is not available to you is customizing the parameters and calls of the anti-cheat.

Let's get back to the point.&#x20;

After authorization using the data from the email, you get access to editing server files.



Open the **BaseLib** tab, here you will see two items:&#x20;

**AllowedSystemDlls** and **AllowedGameDlls**.&#x20;

Let's look at each separately.&#x20;

**AllowedGameDlls** — a list of game dlls that you should have found out earlier. An example of such a file (Sample UE5 project):

{% code overflow="wrap" %}
```ini
AllowedGameDlls = { "d3dcompiler_47.dll", "libcef.dll", "libEGL.dll", "libGLESv2.dll", "libEGL.dll", "libGLESv2.dll", "dbghelp.dll", "msquic.dll", "libogg_64.dll", "libvorbisfile_64.dll", "libvorbis_64.dll", "WinPixEventRuntime.dll", "xaudio2_9redist.dll", "OpenImageDenoise.dll", "tbb.dll", "tbb12.dll", "tbbmalloc.dll", "D3D12Core.dll" };
```
{% endcode %}

**AllowedSystemDlls** — respectively system dlls. Example from the same project:

{% code overflow="wrap" %}
```ini
AllowedSystemDlls = { "kernel32.dll", "ntdll.dll", "apphelp.dll", "AcGenral.DLL", "msvcrt.dll", "sechost.dll", "SHLWAPI.dll", "USER32.dll", "win32u.dll", "GDI32.dll", "gdi32full.dll", "msvcp_win.dll", "ucrtbase.dll", "ole32.dll", "combase.dll", "RPCRT4.dll", "advapi32.dll", "shcore.dll", "SHELL32.dll", "USERENV.dll", "MPR.dll", "SspiCli.dll", "IMM32.DLL", "WS2_32.dll", "COMDLG32.dll", "XINPUT1_3.dll", "dxgi.dll", "OLEAUT32.dll", "SETUPAPI.dll", "CRYPT32.dll", "DSOUND.dll", "COMCTL32.dll", "WINMM.dll", "NETAPI32.dll", "IPHLPAPI.DLL", "UIAutomationCore.DLL", "dwmapi.dll", "WINHTTP.dll", "CFGMGR32.dll", "MSVCP140.dll", "OPENGL32.dll", "VERSION.dll", "bcrypt.dll", "UxTheme.dll", "PROPSYS.dll", "POWRPROF.dll", "VCRUNTIME140.dll", "VCRUNTIME140_1.dll", "ResampleDmo.DLL", "winmmbase.dll", "GLU32.dll", "msdmo.dll", "NETUTILS.DLL", "dxcore.dll", "SRVCLI.DLL", "UMPDC.dll", "bcryptprimitives.dll", "windows.storage.dll", "wintypes.dll", "profapi.dll", "directxdatabasehelper.dll", "kernel.appcore.dll", "d3d11.dll", "msasn1.dll", "cryptnet.dll", "drvstore.dll", "devobj.dll", "wldp.dll", "cryptbase.dll", "wintrust.dll", "imagehlp.dll", "CRYPTSP.dll", "rsaenh.dll", "nvspcap64.dll", "ntmarta.dll", "DINPUT8.dll", "inputhost.dll", "CoreMessaging.dll", "NSI.dll", "dhcpcsvc.DLL", "nvapi64.dll", "mf.dll", "mfplat.dll", "RTWorkQ.DLL", "mfplay.dll", "dhcpcsvc6.DLL", "mswsock.dll", "napinsp.dll", "pnrpnsp.dll", "DNSAPI.dll", "winrnr.dll", "wshbth.dll", "nlansp_c.dll", "clbcatq.dll", "gameux.dll", "msctf.dll", "textinputframework.dll", "explorerframe.dll", "nvldumdx.dll", "nvwgf2umx.dll", "NvCamera64.dll", "XINPUT9_1_0.dll", "HID.DLL", "WindowsCodecs.dll", "MessageBus.dll", "d3dcompiler_47_64.dll", "gpapi.dll", "WINNSI.DLL", "dbgcore.DLL", "d3d12.dll", "_nvngx.dll", "DEVRTL.dll", "SPINF.dll", "dataexchange.dll", "twinapi.appcore.dll", "dcomp.dll", "d3d9.dll", "MessageBus.dll", "Secur32.dll", "OLEACC.dll", "WTSAPI32.dll", "DWrite.dll", "WINSPOOL.DRV", "dxva2.dll", "credui.dll", "USP10.dll", "CRYPTUI.dll", "urlmon.dll", "wevtapi.dll", "ncrypt.dll", "ESENT.dll", "WININET.dll", "iertutil.dll", "WKSCLI.DLL", "SAMCLI.DLL", "NTASN1.dll", "DPAPI.dll", "WINSTA.dll", "MMDevApi.dll", "mscms.dll", "Windows.UI.dll", "AVRT.dll", "xaudio2_9.dll", "AUDIOSES.DLL", "resourcepolicyclient.dll", "TestProject.exe", "KERNELBASE.dll", "msvcp140_2.dll", "rasadhlp.dll", "fwpuclnt.dll" };
```
{% endcode %}



After setting up the dll, you have three more tabs:

* Analytics
* Rules
* Settings

**Analytics** — in this tab you can see all detected dlls and trigger statistics.&#x20;

You can also add dll to the list of rules.

Available rules:

* Keeping an enhanced player log (if detected, keeps a log of all the player’s actions and according to his client’s data)
* Closing the game (if detected, closes your game with an error)
* User blocking (if detected, issues a block according to your API)

You can also attach an API call to each of these points with passing arguments.



**Rules** — this tab contains all blocked dlls, you can apply new rules to them or open sent logs.

**Settings** — here you can set all API callbacks and values that the anti-cheat will accept.&#x20;

Example: userid, etc.

{% hint style="warning" %}
In order for the anti-cheat to accept reverse arguments, you need to implement the logic in your project!
{% endhint %}

An example of setting up an API callback to block a user using his UserID as a variable:

```css
https://api.example.com/blockuser/?userid={var:uid}&api_key={var:apikey}
```
