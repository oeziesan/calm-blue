# calm-blue dotfiles

> make windows 11 not look like windows. tiling layout, custom status bar, blurred explorer, and a cohesive calm-blue aesthetic — all wired together and ready to drop in.

**tags:** `windows-ricing` `tiling-wm` `komorebi` `yasb` `catppuccin`

jump to: [preview](#preview) · [stack](#stack) · [prerequisites](#prerequisites) · [installation](#installation)

---

## preview

![preview](preview/SS1.png)
![preview](preview/SS2.png)
[![Watch the video](preview/previewvideo.png)](https://youtu.be/wwuWRU4wgBU)

---

## stack

> windows ricing = customizing windows' visual appearance and workflow beyond what the OS provides out of the box. this setup replaces the taskbar, adds tiling window management, and applies a consistent blue-tinted theme across all components.

| tool | role |
|---|---|
| [komorebi](https://github.com/LGUG2Z/komorebi) | tiling window manager — auto-arranges windows, keyboard-driven |
| [yasb](https://github.com/amnweb/yasb) | custom status bar — replaces the default windows taskbar |
| [whkd](https://github.com/LGUG2Z/whkd) | hotkey daemon — handles keyboard shortcuts for komorebi |
| [windows terminal](https://github.com/microsoft/terminal) | terminal — catppuccin mocha + liquid glass transparency |
| [flow launcher](https://github.com/Flow-Launcher/Flow.Launcher) | spotlight-style app launcher with calm-blue theme |
| [windhawk](https://windhawk.net) | system-level tweaks — notification center, icon themes |
| [winfetch](https://github.com/lptstr/winfetch) | neofetch-style system info display in terminal |
| [cursors](https://vsthemes.org/en/cursors/anime/70655-miyabi-zzz.html) | miyabi cursor theme |
| [ExplorerBlurMica](https://github.com/Maplespe/ExplorerBlurMica) | blur/mica effect on file explorer |

---

## prerequisites

- **Windows 11** — required. some tools are Win11-specific.
- **scoop** or **winget** — winget ships with Windows 11 by default.

set up scoop if you don't have it:

```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
irm get.scoop.sh | iex
```

---

## installation

you can follow every step for the exact same output, or jump to a specific component:

[cursors](#1-cursors) · [ExplorerBlurMica](#2-explorerblurmica) · [flow launcher](#3-flow-launcher) · [komorebi](#4-komorebi) · [windows terminal](#5-windows-terminal) · [winfetch](#6-winfetch) · [yasb](#7-yasb) · [windhawk](#8-windhawk) · [hide taskbar](#9-hide-taskbar)

---

### 1. cursors

`optional`

[![cursors](https://github.com/user-attachments/assets/a79f7d6f-f61d-4d43-8962-c7a3a72b76bb)](https://vsthemes.org/en/cursors/anime/70655-miyabi-zzz.html)

run `install.inf` → right click → install, then apply via mouse settings.

shoutout to **aliline** for the cursor. explore more at [vsthemes](https://vsthemes.org/en/cursors/).

---

### 2. ExplorerBlurMica

`optional`

download from the [repository](https://github.com/Maplespe/ExplorerBlurMica/releases), extract, run `register.cmd`. optionally import a preset or configure manually via the GUI.

---

### 3. flow launcher

`optional`

<div align="center">
  <img src="https://github.com/user-attachments/assets/98d2f0d6-1072-482d-84ea-25350d832d5f">
</div>

download and install [Flow Launcher](https://github.com/Flow-Launcher/Flow.Launcher/releases), then copy the theme:

```
flow-launcher/calm-blue.xaml → %APPDATA%\FlowLauncher\Themes\
```

open settings → appearance → select `calm-blue`.

**recommended font:**

| size | weight |
|---|---|
| 16pt | JetBrains Mono Regular |
| 14pt | JetBrains Mono Thin |
| 12pt | JetBrains Mono Light |

apply via settings → appearance → font.

---

### 4. komorebi

`core`

**install:**

```powershell
# scoop
scoop bucket add extras
scoop install komorebi whkd

# or winget
winget install LGUG2Z.komorebi
winget install LGUG2Z.whkd
```

**start and enable autostart:**

```powershell
komorebic start --whkd
komorebic enable-autostart --whkd
```

**apply config:**

```
komorebi/komorebi.json → %USERPROFILE%\komorebi.json
```

```powershell
komorebic reload-configuration
```

---

### 5. windows terminal

`optional`

<div align="center">
  <img src="https://github.com/user-attachments/assets/8fe41676-f1a5-4a00-981c-16cbbbc30952">
</div>

right click the title bar → settings → open JSON file → paste everything from `windows-terminal/settings.json`.

set appearance → application theme → `Catppuccin Mocha`. do the same for color schemes.

**liquid glass effect:** profiles → defaults → appearance → transparency → set opacity to 40% and enable acrylic material.

---

### 6. winfetch

`optional`

```powershell
# powershell gallery (recommended)
Install-Script winfetch

# winget
winget install winfetch

# scoop
scoop install winfetch
```

**run on terminal startup** — add to `$PROFILE`:

```powershell
notepad $PROFILE
# add: winfetch
```

---

### 7. yasb

`core`

```powershell
# winget
winget install AmN.yasb

# scoop
scoop bucket add extras
scoop install extras/yasb
```

**apply config:**

```
yasb/config.yaml + style.css → %USERPROFILE%\.config\yasb\
```

then reload the bar.

---

### 8. windhawk

`optional`

used to hide the default taskbar, reposition quick settings and notification center to the top, and swap the icon pack.

| mod | what it does | theme |
|---|---|---|
| Resource Indirect | swaps icon pack | macOS DarkMode (by Niivu) |
| Taskbar on top for Windows 11 | moves taskbar and start menu to top | — |
| Windows 11 Notification Center Styler | styles and repositions notification center | Translucent Shell |
| Windows 11 Start Menu Styler | reskins the start menu | Down Aero |

themes are optional — use whatever fits your setup.

**to move notification center to the top:** advanced → mod settings → paste content of `windhawk/notification-center.json` → save.

---

### 9. hide taskbar

`core`

download [thide](https://github.com/amnweb/thide) and install via the .msi installer.

```powershell
thide start
thide enable-autostart
```

this hides the default windows taskbar so yasb can take over cleanly.

---

done.
