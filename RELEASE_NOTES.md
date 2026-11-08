# MAC Scout release notes

Every version of MAC Scout and what changed. Download the latest: [MacScout.exe](https://github.com/Dialsoft/macscout-releases/raw/main/MacScout.exe)

## 1.8.5

- **Search is now always there:** a search box sits above the device list. Type part of a name, IP address or MAC address and the list shrinks as you type; MAC addresses match in any format (5c3a, 5C-3A-45, 5c:3a:45). It searches every column by default, or pick one column next to it.
- Shows how many devices match ("3 of 19 devices"), and when other location tabs also have matches it says so ("Also in: Store B (2)") - click to jump to that tab with the same search.
- **Fixed:** searching for a short piece of a MAC address in another format (like 5c3a for 5C-3A-...) found nothing; MAC searches now match from 2 characters in any format.
- Ctrl+F puts the cursor in the search box; Esc clears it. Find next (F3) still jumps from match to match without hiding the others.

## 1.8.4

- MAC Scout's download page and updates now live on GitHub at github.com/Dialsoft/macscout-releases (like Dialsoft's other tools). Copies set to the old dialsoft.com location switch over by themselves; dialsoft.com/macscout keeps forwarding there, so nothing is missed.
- Share MAC Scout now sends people to the GitHub download page.

## 1.8.3

- **Installs .NET Framework 4.8 for you:** on a computer that doesn't have it (Windows Server 2012 / 2012 R2 come with .NET 4.5), MAC Scout now explains what's missing and offers to download Microsoft's official offline installer (about 112 MB), checks that it is genuinely signed by Microsoft, and installs it (one administrator prompt). When setup needs a restart, MAC Scout asks before restarting Windows and opens again by itself afterwards. Say no, or if anything goes wrong, and it offers Microsoft's download page instead.

## 1.8.2

- The activity log and status bar now say "Found 19 devices" instead of "computers", since MAC Scout finds printers, phones, cameras and everything else too. "Couldn't find MAC address" messages now say the device may be switched off or not answering.

## 1.8.1

- System requirements spelled out everywhere (Help, About box, manual, download page): Windows 10 or 11, or Windows Server 2012 / 2012 R2 or later, with the Microsoft .NET Framework 4.8. Up-to-date Windows 10 and 11 already have it; on Windows Server 2012, 2012 R2, 2016 or Windows 8.1, install it first from https://dotnet.microsoft.com/download/dotnet-framework/net48 (Runtime, Offline installer).
- On a PC without .NET Framework 4.8, a clear message now appears instead of MAC Scout starting and then failing.

## 1.8.0

- **Automatic updates:** MAC Scout now updates itself. It checks dialsoft.com a few seconds after it starts and every 6 hours while open, downloads a new version in the background, checks its SHA-256 fingerprint, and installs it when you close MAC Scout. Or click the status bar to restart into it right away. Settings, locations and notes are kept. Nothing to set up; switch it off in Preferences > Updates if you prefer to install by hand.
- After an update, the status bar says so and links to what's new.
- **Fixed:** a router or firewall doing "proxy ARP" (Cisco does by default) made one MAC address show up on hundreds of IP addresses, each flagged "Same MAC on ... IP addresses" and "IP changed". MAC Scout now keeps the router, leaves the phantom addresses out and explains why in the activity log. Preferences > Scanning can show them again.
- **Share MAC Scout (Help ribbon, File menu or About box):** send someone the download link by e-mail, Gmail, Outlook on the web, Facebook Messenger, WhatsApp, text message (Phone Link), Teams, a Facebook post or LinkedIn. Edit the message first; your name is remembered. Nothing is sent until you press Send.

## 1.7.1

- Credits list tidied up.

## 1.7.0

- Built-in SSH client (Tools > SSH, or right-click a device > Network tools > ssh): password, keyboard-interactive or key-file login, colour xterm terminal that resizes with the window, full-screen programs (top, nano, less), copy/paste. The first connection shows the device fingerprint to trust; a changed fingerprint gets a clear warning. User names are remembered per device; passwords are never saved.
- **Choose the browser for web pages:** Preferences > Browser (any installed browser or another program, with optional extra options such as --incognito), or quickly from Open as > Open web pages with.
- **Credits updated:** SSH.NET (MIT) is built in.

## 1.6.2

- **Help > Credits & licenses:** every third-party component, data source and standard MAC Scout uses, with the full licence texts. Also linked from the About box.
- Copyright now shown as Dialsoft LLC.
- **Source code:** every file has a header, and classes, methods and the tricky parts (network protocols, terminal, scanner threads) are now commented throughout.

## 1.6.1

- **Ping window redesigned:** status tiles (online / no reply and for how long, last reply, average, packet loss), a reply-time graph with a scale, and a reply list with icons. Options open in a panel under the address bar and apply while pinging.
- **Telnet:** new BBS mode (Type: BBS) - CP437 characters, DOS colours, blinking text, fixed 80 x 25 screen, and ANSI art drawn cell-perfect (blocks, shading and box lines join with no gaps). Tells the BBS it is an ANSI terminal; Enter sends a plain CR. The choice is remembered.
- **Telnet:** box and block characters are drawn the same cell-perfect way in network-device mode too.

## 1.6.0

- **Built-in Ping window:** no command prompt or ping.exe needed. Runs until stopped (or a set count), live reply-time graph, lost replies in red, totals, Copy.
- **Built-in Telnet window:** no telnet.exe needed (it is not installed on Windows by default). VT100 terminal with colours and menus, copy/paste, scroll-back. Clear messages when a port is closed or blocked, so it also works as a port tester (any port).
- Network tools > ping and telnet now open these windows; also on the Tools tab (Built-in > Ping / Telnet). Existing tool lists are updated automatically.

## 1.5.8

- **Admin tools:** Shutdown/Restart and Send message no longer block the main window. With several devices selected, a window opens for each one at the same time (titled with the device name) instead of one after another.

## 1.5.7

- The Adapter column (network card name) now stays hidden until a scan actually finds adapter names - only the WMI and SNMP methods can. It appears by itself after such a scan, in its usual place.

## 1.5.6

- **Fixed:** buttons beside a text box (such as Lookup in the MAC lookup window) sat higher than the box and stuck out past the edge. They now line up exactly.

## 1.5.5

- **New device type window:** shorter label (examples now shown inside the name box), wider window and more room for each icon name.

## 1.5.4

- **Fixed:** small windows (Rename location, Lookup MAC and others) cut off their text and OK/Cancel buttons with larger Windows display scaling or fonts. They now size themselves to fit.

## 1.5.3

- **Problems explained in plain English:** point at a device's Problems cell for what it means and what to do, or right-click > What does this problem mean? to keep it open.
- Pointing at the "N problems" link under Devices found lists which devices have which problem.
- IP conflicts now name the other device, not just its MAC address.

## 1.5.2

- **Fixed:** the Method choices (ARP, Netbios, NET API, WMI, SNMP) could be selected several at once and could not be turned off. Now exactly one is selected; arrow keys move between them.

## 1.5.1

- Tutorial button now always visible at the top right of the ribbon; the tour's last step points to it.
- **Location tabs redesigned:** each tab is a distinct card on a darker band, with a clearer selected tab.
- **Device types:** double-click a device's Type cell (or Home > Device type) to change it.
- Add your own device types with your own icon (Tools > Device types).
- **Type rules:** "every device from this manufacturer is a ..." - teach MAC Scout once and it applies to every location and future scan (Tools > Type rules).
- **New built-in types for dealerships:** card terminal / POS, time clock, key cabinet, door / access control, digital sign, kiosk, scanner, shop / diagnostic equipment.

## 1.5.0

- Guided tour with speech bubbles on first start (Help > Tutorial to run it again; 'Don't show this tour at startup' checkbox).
- **Left column tightened:** the Target and Devices found boxes fit their contents, so Method stays visible in smaller windows.

## 1.4.0

- Print, Print preview and Save as PDF (File menu, Home and Location tabs, Ctrl+P).
- **"First seen" column shown by default:** the date each MAC address was first found at this location.
- Preferences moved to Ctrl+, (Ctrl+P now prints).
- **About:** created by Marc Frega, built with Claude by Anthropic (claude.ai).

## 1.3.2

- The version number is shown in the top menu next to Help (click it for About / Check for updates).

## 1.3.1

- **Fixed:** Start IP showed only ".1" when the program opened (the box was scrolled to the end).
- **Fixed:** the bookmark button next to B and C was cut off on some screens.

## 1.3.0

- Check for updates (Help tab, File menu and About box), with an optional quiet check at start-up.
- **Scan history per location:** compare any two scans (new / gone / changed devices), first and last seen.
- **Problems column:** IP conflicts, cloned or made-up MAC addresses, gateway MAC changes (possible ARP spoofing).
- Device type icons (Microsoft Fluent icons) with manual override.
- Big live "Devices found" counter.
- Layout rebuilt to line up at every Windows display scale.
