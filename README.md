<div align="center">

# PodcastMagic 360

**Your 360° podcast recording, directed like a camera operator – inside DaVinci Resolve Studio.**

[Website](https://marcvannuffel.github.io/podcastmagic360-site/) ·
[Installation guide](https://marcvannuffel.github.io/podcastmagic360-site/install.html) ·
[Buy a licence – $99](https://buy.polar.sh/polar_cl_GSkvM6gTHxN5hH15pHMuJXTHpOJ09WWcmPKVu2kIavP) ·
[Latest release](https://github.com/marcvannuffel/dm360-releases/releases/latest)

![Windows 10/11](https://img.shields.io/badge/Windows-10%20%2F%2011-2b2d31)
![macOS Apple Silicon](https://img.shields.io/badge/macOS-Apple%20Silicon-2b2d31)
![DaVinci Resolve Studio 21.1+](https://img.shields.io/badge/DaVinci%20Resolve%20Studio-21.1%2B-2b2d31)

</div>

One 360° camera in the middle of the table, and PodcastMagic 360 turns the
recording into a multicam edit: it finds the people, cuts to whoever speaks,
moves the camera like an operator, catches reactions and writes everything to
your Resolve timeline – also as vertical clips for Reels, Shorts and TikTok.

Works with GoPro MAX (`.360`), Insta360 (`.insv`) and any
equirectangular 360° MP4.

This repository holds the installers and the signed releases. The plugin's
source code is not public.

## Requirements

- [DaVinci Resolve Studio](https://www.blackmagicdesign.com/products/davinciresolve/studio)
  21.1 or later. The free DaVinci Resolve does not run workflow integration plugins.
- Windows 10/11 or macOS on Apple Silicon.
- In Resolve: **Preferences › System › General › External scripting using: Local**.

## Install

Once per computer. After that the plugin updates itself.

**Windows** – open PowerShell **as administrator** and paste:

```powershell
irm https://github.com/marcvannuffel/dm360-releases/releases/latest/download/install.ps1 | iex
```

**macOS** (Apple Silicon) – open Terminal and paste (asks for your password once):

```bash
curl -fsSL https://github.com/marcvannuffel/dm360-releases/releases/latest/download/install.sh | bash
```

Restart DaVinci Resolve and open **Workspace › Workflow Integrations ›
PodcastMagic 360**.

Step by step, with first start and troubleshooting:
**[installation guide](https://marcvannuffel.github.io/podcastmagic360-site/install.html)**.

## Free trial and licence

The installer is the same for the trial and the full version. Without a
licence everything works, but writing to the timeline and finishing the
picture cover the first two minutes of each episode.

[Buy a licence](https://buy.polar.sh/polar_cl_GSkvM6gTHxN5hH15pHMuJXTHpOJ09WWcmPKVu2kIavP)
($99, one-time, one computer, all 1.x updates), then paste the key under
**Settings › Licence** in the plugin. Moving to a new computer: **Free this
computer** on the old one, activate on the new one.

## Updates

When the plugin opens it checks for a newer version, downloads it in the
background and verifies its signature. The next time you open it, the new
version runs; the previous one stays as a fallback.

## What gets installed

| What | Windows | macOS |
| --- | --- | --- |
| The plugin (updates itself) | `%LOCALAPPDATA%\DM360` | `~/Library/Application Support/DM360` |
| Starter for Resolve | `%ProgramData%\Blackmagic Design\DaVinci Resolve\Support\Workflow Integration Plugins\com.dudagroup.dm360` | `/Library/Application Support/Blackmagic Design/DaVinci Resolve/Workflow Integration Plugins/com.dudagroup.dm360` |
| Fusion tool DM360 Reframe | `%APPDATA%\Blackmagic Design\DaVinci Resolve\Support\Fusion\Fuses` | `~/Library/Application Support/Blackmagic Design/DaVinci Resolve/Fusion/Fuses` |

To uninstall, delete these three folders (free the licence first if you
want to use it elsewhere).

## Help

- **Settings › System check** in the plugin shows what is missing and how to fix it.
- Log file: `%LOCALAPPDATA%\DM360\panel.log` (Windows),
  `~/Library/Logs/DM360/panel.log` (macOS).
- Questions and bugs: [open an issue](https://github.com/marcvannuffel/dm360-releases/issues).

## Bundled software

`ffmpeg` (only to split GoPro `.360` files, without re-encoding), built from
the official source at [ffmpeg.org](https://ffmpeg.org) with a minimal
configuration, licence LGPL 2.1 or later. Licence and build details are in
the package under `ffmpeg/`.

---

PodcastMagic 360 is made by NuNu Soft. DaVinci Resolve is a trademark of
Blackmagic Design. GoPro and Insta360 are
trademarks of their owners. PodcastMagic 360 is not affiliated with them.
