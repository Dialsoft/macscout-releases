# MAC Scout

**Find every device on your network.** MAC Scout finds every computer, printer, phone, camera and gadget on a network and shows its IP address, MAC address and manufacturer. It spots IP conflicts and cloned or made-up MAC addresses, keeps notes and scan history per client location, and has ping, telnet (BBS-ready) and SSH built in.

By Dialsoft LLC ([dialsoft.com](https://dialsoft.com)), for IT technicians.

## Download

### [⬇ Download MAC Scout 1.8.4](https://github.com/Dialsoft/macscout-releases/raw/main/MacScout.exe)

Version 1.8.4 · released November 2, 2026 · 3.6 MB · portable, nothing to install · updates itself

SHA-256: `D2FC3BC8D38F5FE6CC45B5F1079159F80B772A9E8BA56CFFE3B3D87E49330A97` (check with `Get-FileHash MacScout.exe` in PowerShell)

## System requirements

- **Windows 10 or 11** (32- or 64-bit), or **Windows Server 2012 / 2012 R2 or later** with the desktop installed. Server Core is not supported.
- **Microsoft .NET Framework 4.8.** Up-to-date Windows 10 and 11 already have it. On Windows Server 2012, 2012 R2, 2016 or Windows 8.1, MAC Scout offers to download Microsoft's offline installer and install it for you the first time you run it. It checks that the installer is genuinely signed by Microsoft first. Windows usually needs a restart, and MAC Scout opens again by itself afterwards. You can also install it yourself from [Microsoft's download page](https://dotnet.microsoft.com/download/dotnet-framework/net48) (Runtime > Offline installer).
- Administrator rights on the remote computers for the WMI and NET API scan methods and remote shutdown. Everything else runs as a normal user.

## Getting started

1. **Download and run.** Save MacScout.exe to a folder you can write to, such as Desktop, Documents or `C:\Tools` (not Program Files), so it can update itself. Double-click it. There is no installer.
2. **Scan.** Choose the addresses to scan (your own network is a good start) and press **Scan**. Every device appears with its IP, MAC address, manufacturer and type. A guided tour shows you around on the first start.
3. **It stays current.** MAC Scout checks this page a few seconds after it starts and every 6 hours. It downloads new versions in the background, checks their SHA-256 fingerprint, and installs them when you close it. You can switch this off in Preferences > Updates.

## What's new in 1.8.4

- MAC Scout's download page and updates now live on GitHub at github.com/Dialsoft/macscout-releases (like Dialsoft's other tools). Copies set to the old dialsoft.com location switch over by themselves; dialsoft.com/macscout keeps forwarding there, so nothing is missed.
- Share MAC Scout now sends people to the GitHub download page.

[All release notes](RELEASE_NOTES.md)

## Under the hood

**Language and platform**
- Written in **C#**, using the latest C# language features.
- Runs on the **Microsoft .NET Framework 4.8** with Windows Forms.
- Compiled with Microsoft's Roslyn compiler.

**One file, everything inside**
- A single 3.6 MB program holds everything.
- It contains the full IEEE manufacturer registry (54,000+ MAC address prefixes).
- It contains 129 Microsoft Fluent icons, each pre-drawn at 7 sizes so they stay sharp at any display scaling.
- The SSH library (SSH.NET, MIT licence) is embedded too, loaded straight from memory.

**Network protocols, hand-built**
- Five ways to find devices: **ARP** (Windows IP Helper API), **NetBIOS** name queries (RFC 1001/1002), **NET API**, **WMI**, and **SNMP v1** with MAC Scout's own encoder and decoder.
- The scanner is multi-threaded, with up to 256 queries at once.
- It detects **proxy ARP**, where a router answers for addresses it doesn't own.
- Telnet option negotiation is MAC Scout's own code.

**Its own terminal**
- A VT100/xterm emulator written from scratch drives the telnet and SSH windows.
- It supports 256-colour and true-colour programs and full-screen apps like top, nano and less.
- A **BBS mode** uses IBM code page 437, DOS colours and blinking, and draws ANSI art cell-perfect.

**Safe self-updates**
- Every download is checked against the SHA-256 fingerprint published with it.
- The new version replaces the running program using a Windows rename trick. The old copy is kept until the next start.
- Settings are saved in `%APPDATA%\MacScout`, written to a temporary file first so a crash never corrupts them.

**How it was made**
- Designed by **Marc Frega** (Dialsoft LLC, theITguy.com) for the car-dealer networks his team looks after.
- Programmed with **Claude** by Anthropic.
- About 13,800 lines of code in 43 files, with every file commented.

## Files here

| File | What it is |
|---|---|
| `MacScout.exe` | The program (the only file you need) |
| `MacScout.exe.sha256` | Its SHA-256 fingerprint |
| `version.json` | Read by MAC Scout to update itself |
| `latest.json` | Read by dialsoft.com to show the current version |
| `RELEASE_NOTES.md` | Every version and what changed |

---

© 2026 Dialsoft LLC, Wharton, New Jersey. Created by Marc Frega. Built with Claude by Anthropic. MAC Scout includes Microsoft Fluent UI System Icons (MIT), SSH.NET (MIT) and IEEE registry data via oui-data (BSD 2-Clause); full credits are in Help > Credits & licenses. This repository contains releases only; the source code is not public.
