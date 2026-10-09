# 360 Switcher für DaVinci Resolve Studio

Schnitt-Panel für 360°-Podcast-Aufnahmen (GoPro MAX, Insta360, 360°-MP4) in
DaVinci Resolve Studio 21.1 oder neuer.

## Installation

Einmal pro Rechner, danach aktualisiert sich das Panel selbst.

**Windows** – PowerShell **als Administrator** öffnen und einfügen:

```powershell
irm https://github.com/marcvannuffel/dm360-releases/releases/latest/download/install.ps1 | iex
```

**macOS** (Apple Silicon) – Terminal öffnen und einfügen (fragt einmal nach dem Passwort):

```bash
curl -fsSL https://github.com/marcvannuffel/dm360-releases/releases/latest/download/install.sh | bash
```

Danach DaVinci Resolve neu starten und das Panel über
**Workspace › Workflow Integrations › 360 Switcher** öffnen.

In Resolve muss unter **Preferences › System › General › External scripting
using** „Local“ eingestellt sein.

## Updates

Beim Öffnen prüft das Panel, ob es eine neue Version gibt, lädt sie im
Hintergrund und prüft ihre Signatur. Beim nächsten Öffnen läuft die neue
Version. Die vorherige bleibt als Rückfall erhalten.

## Was installiert wird

| Was | Wo (Windows) | Wo (macOS) |
| --- | --- | --- |
| Panel (aktualisiert sich) | `%LOCALAPPDATA%\DM360` | `~/Library/Application Support/DM360` |
| Starter für Resolve | `%ProgramData%\Blackmagic Design\DaVinci Resolve\Support\Workflow Integration Plugins\com.dudagroup.dm360` | `/Library/Application Support/Blackmagic Design/DaVinci Resolve/Workflow Integration Plugins/com.dudagroup.dm360` |
| Fusion-Werkzeug DM360 Reframe | `%APPDATA%\Blackmagic Design\DaVinci Resolve\Support\Fusion\Fuses` | `~/Library/Application Support/Blackmagic Design/DaVinci Resolve/Fusion/Fuses` |

## Mitgelieferte Software

`ffmpeg` (nur zum Aufteilen von GoPro-`.360`-Dateien, ohne Neukodierung),
selbst gebaut aus dem offiziellen Quellcode von [ffmpeg.org](https://ffmpeg.org),
minimal konfiguriert, Lizenz LGPL 2.1 oder später. Lizenz und Bauangaben
liegen im Paket unter `ffmpeg/`.
