# MAC Scout

**Find every device on your network.** MAC Scout finds every computer, printer, phone, camera and gadget on a network and shows its IP address, MAC address and manufacturer. It spots IP conflicts and cloned or made-up MAC addresses, keeps notes and scan history per client location, and has ping, telnet (BBS-ready) and SSH built in.

By Dialsoft LLC ([dialsoft.com](https://dialsoft.com)), for IT technicians.

## Download

Version 1.8.8 · released November 11, 2026 · keeps itself up to date

| | Download | What it is |
|---|---|---|
| **Installer** (recommended) | [⬇ MacScout-Setup.exe](https://github.com/Dialsoft/macscout-releases/raw/main/MacScout-Setup.exe) (4.9 MB) | Installs MAC Scout for your Windows account (no administrator password), with Start menu shortcuts for the program and the user manual, an optional desktop shortcut, and an uninstaller in Settings > Apps. |
| **Portable** | [⬇ MacScout.exe](https://github.com/Dialsoft/macscout-releases/raw/main/MacScout.exe) (3.6 MB) | The program as one file, nothing to install. For USB sticks, customer PCs and network shares. |
| **User manual** | [📄 MacScout-User-Manual.pdf](https://github.com/Dialsoft/macscout-releases/raw/main/MacScout-User-Manual.pdf) | Everything MAC Scout does, step by step, with pictures (also installed with the installer). |
| **Explainer video** | [▶ MacScout-explainer.mp4](https://github.com/Dialsoft/macscout-releases/raw/main/MacScout-explainer.mp4) | A 1 minute 40 second introduction: what MAC Scout is and who it is for. |

Both versions are the same program and share their settings (`%APPDATA%\MacScout`), so you can switch between them.

SHA-256 fingerprints (check with `Get-FileHash <file>` in PowerShell):
- MacScout.exe: `1FF9F0743559615161339EFF4652D7CE46D50B5D2EE5A01B8D6B5C29D2207A00`
- MacScout-Setup.exe: `125F7BFF9C08EEEAD0E43CDEC5AFC0E92037061A9BC723D401F536A66910F360`

## System requirements

- **Windows 10 or 11** (32- or 64-bit), or **Windows Server 2012 / 2012 R2 or later** with the desktop installed. Server Core is not supported.
- **Microsoft .NET Framework 4.8.** Up-to-date Windows 10 and 11 already have it. On Windows Server 2012, 2012 R2, 2016 or Windows 8.1, MAC Scout offers to download Microsoft's offline installer and install it for you the first time you run it. It checks that the installer is genuinely signed by Microsoft first. Windows usually needs a restart, and MAC Scout opens again by itself afterwards. You can also install it yourself from [Microsoft's download page](https://dotnet.microsoft.com/download/dotnet-framework/net48) (Runtime > Offline installer).
- Administrator rights on the remote computers for the WMI and NET API scan methods and remote shutdown. Everything else runs as a normal user.

## Getting started

1. **Install or run.** Run MacScout-Setup.exe and follow the steps, or save the portable MacScout.exe to a folder you can write to, such as Desktop, Documents or `C:\Tools` (not Program Files), so it can update itself, and double-click it.
2. **Scan.** Choose the addresses to scan (your own network is a good start) and press **Scan**. Every device appears with its IP, MAC address, manufacturer and type. A guided tour shows you around on the first start.
3. **It stays current.** MAC Scout checks this page a few seconds after it starts and every 6 hours. It downloads new versions in the background, checks their SHA-256 fingerprint, and installs them when you close it. You can switch this off in Preferences > Updates.

## What's new in 1.8.8

- **New installer:** MacScout-Setup.exe installs MAC Scout for your Windows account (no administrator password), with Start menu shortcuts for the program and the user manual, an optional desktop shortcut, and an uninstaller in Settings > Apps. Uninstalling keeps your locations and history unless you choose to delete them. The portable MacScout.exe is still available for USB sticks and customer PCs.
- Installed copies keep the version shown in Settings > Apps up to date after updating themselves.
- New user manual (27 pages) covering the installer, searching the list, the This computer box, automatic updates, sharing and proxy ARP. Also on the download page, with the explainer video.

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
- The SSH library (SSH.NET, MIT license) is embedded too, loaded straight from memory.

**Network protocols, hand-built**
- Five ways to find devices: **ARP** (Windows IP Helper API), **NetBIOS** name queries (RFC 1001/1002), **NET API**, **WMI**, and **SNMP v1** with MAC Scout's own encoder and decoder.
- The scanner is multi-threaded, with up to 256 queries at once.
- It detects **proxy ARP**, where a router answers for addresses it doesn't own.
- Telnet option negotiation is MAC Scout's own code.

**Its own terminal**
- A VT100/xterm emulator written from scratch drives the telnet and SSH windows.
- It supports 256-color and true-color programs and full-screen apps like top, nano and less.
- A **BBS mode** uses IBM code page 437, DOS colors and blinking, and draws ANSI art cell-perfect.

**Safe self-updates**
- Every download is checked against the SHA-256 fingerprint published with it.
- The new version replaces the running program using a Windows rename trick. The old copy is kept until the next start.
- Settings are saved in `%APPDATA%\MacScout`, written to a temporary file first so a crash never corrupts them.

**How it was made**
- Designed by **Marc Frega** (Dialsoft LLC, theITguy.com) for the car-dealer networks his team looks after.
- Programmed with **Claude** by Anthropic.
- About 13,900 lines of code in 44 files, with every file commented.

## Files here

| File | What it is |
|---|---|
| `MacScout-Setup.exe` | The installer |
| `MacScout.exe` | The portable program (one file, nothing to install) |
| `MacScout-User-Manual.pdf` | The user manual |
| `MacScout-explainer.mp4` | The explainer video |
| `*.sha256` | SHA-256 fingerprints of the installer and the program |
| `version.json` | Read by MAC Scout to update itself |
| `latest.json` | Read by dialsoft.com to show the current version |
| `RELEASE_NOTES.md` | Every version and what changed |

---

© 2026 Dialsoft LLC, Wharton, New Jersey. Created by Marc Frega. Built with Claude by Anthropic. MAC Scout includes Microsoft Fluent UI System Icons (MIT), SSH.NET (MIT) and IEEE registry data via oui-data (BSD 2-Clause); full credits are in Help > Credits & licenses. This repository contains releases only; the source code is not public.
