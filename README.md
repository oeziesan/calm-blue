# windows ricing dotfiles.

born to use linux but forced to use windows? i got you.

jump to: [preview](#preview) · [components](#components) · [prerequisites](#prerequisites) · [step-by-step installation](#step-by-step-installation)

---

## preview

![preview](preview/SS1.png)
![preview](preview/SS2.png)
[![Watch the video](preview/previewvideo.png)](https://youtu.be/wwuWRU4wgBU)

---

## components

| tool | purpose |
|---|---|
| [komorebi](https://github.com/LGUG2Z/komorebi) | tiling window manager |
| [yasb](https://github.com/amnweb/yasb) | status bar |
| [whkd](https://github.com/LGUG2Z/whkd) | hotkey daemon |
| [windows terminal](https://github.com/microsoft/terminal) | terminal |
| [flow launcher](https://github.com/Flow-Launcher/Flow.Launcher) | app launcher |
| [windhawk](https://windhawk.net) | system tweaks |
| [winfetch](https://github.com/lptstr/winfetch) | system info |
| [cursors](https://vsthemes.org/en/cursors/anime/70655-miyabi-zzz.html) | cursor theme |
| [ExplorerBlurMica](https://github.com/Maplespe/ExplorerBlurMica) | explorer blur effect |

---

## prerequisites

- windows 11
- [scoop](https://scoop.sh) or [winget](https://aka.ms/getwinget) (usually pre-installed on Windows 11)

**scoop:**
```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
irm get.scoop.sh | iex
```

**winget** ships with Windows 11 by default, no setup needed.

---

## step-by-step installation

follow all steps for the exact same output, or jump to a specific part:

[cursors](#cursors) · [ExplorerBlurMica](#explorerblurmica) · [flow launcher](#flow-launcher) · [komorebi](#komorebi) · [windhawk](#windhawk) · [windows terminal](#windows-terminal) · [winfetch](#winfetch) · [yasb](#yasb) · [hide taskbar](#hide-taskbar)

---

### cursors

[![cursors](https://github.com/user-attachments/assets/a79f7d6f-f61d-4d43-8962-c7a3a72b76bb)](https://vsthemes.org/en/cursors/anime/70655-miyabi-zzz.html) (click that cute anime girl bro)

run `install.inf` → right click → install, then apply via mouse settings.

shoutout to **aliline** for making this cursor. explore more at [vsthemes](https://vsthemes.org/en/cursors/).

---

### ExplorerBlurMica

download the latest release from the [repository](https://github.com/Maplespe/ExplorerBlurMica/releases), extract, and run `register.cmd`. that's it, it's optional to import a preset.

---

### flow launcher

<div align="center">
  <img src="https://github.com/user-attachments/assets/98d2f0d6-1072-482d-84ea-25350d832d5f">
</div>

download and install [Flow Launcher](https://github.com/Flow-Launcher/Flow.Launcher/releases), then copy the theme file:

```
flow-launcher/calm-blue.xaml → %APPDATA%\FlowLauncher\Themes\
```

open Flow Launcher settings → appearance → select `calm-blue`.

**recommended font:**

| size | weight |
|---|---|
| 16pt | JetBrains Mono Regular |
| 14pt | JetBrains Mono Thin |
| 12pt | JetBrains Mono Light |

apply via settings → appearance → font.

---

### komorebi

**install via scoop:**
```powershell
scoop bucket add extras
scoop install komorebi whkd
```

**or winget:**
```powershell
winget install LGUG2Z.komorebi
winget install LGUG2Z.whkd
```

**quickstart:**
```powershell
komorebic start --whkd
```

**enable autostart:**
```powershell
komorebic enable-autostart --whkd
```

**apply config:**
```
komorebi/komorebi.json → %USERPROFILE%\komorebi.json
```

**reload komorebi**
```powershell
komorebic reload-configuration
```

---

### windows terminal

<div align="center">
  <img src="https://github.com/user-attachments/assets/8fe41676-f1a5-4a00-981c-16cbbbc30952">
</div>

right click the title bar → settings → open JSON file → paste everything from `windows-terminal/settings.json`.

in appearance → application theme → select `Catppuccin Mocha`. do the same for color schemes.

**for the liquid glass effect:**
profiles → defaults → appearance → transparency → set background opacity to 40% and enable acrylic material.

---

### winfetch

**powershell gallery** (recommended):
```powershell
Install-Script winfetch
```

**winget:**
```powershell
winget install winfetch
```

**scoop:**
```powershell
scoop install winfetch
```

**(optional) run on terminal startup:**
```powershell
notepad $PROFILE
```
add this line:
```powershell
winfetch
```

---

### yasb

**install via .msi** from the [yasb releases page](https://github.com/amnweb/yasb), or:

**winget:**
```powershell
winget install AmN.yasb
```

**scoop:**
```powershell
scoop bucket add extras
scoop install extras/yasb
```

**apply config:**
```
yasb/config.yaml + style.css → %USERPROFILE%\.config\yasb\
```
then reload the bar.

---

### windhawk

i use windhawk to hide the default taskbar and replace it with yasb, and to move quick settings + notification center to the top.

| mod | purpose | theme |
|---|---|---|
| Resource Indirect | icon theme switcher | macOS DarkMode (by Niivu) |
| Taskbar on top for Windows 11 | moves taskbar and start menu to top | — |
| Windows 11 Notification Center Styler | styles and repositions notification center | Translucent Shell |
| Windows 11 Start Menu Styler | styles the start menu | Down Aero |

themes are optional, use whatever fits your setup.

**to move notification center to the top:**
advanced → mod settings → paste content from `windhawk/notification-center.json` → save.

---

### hide taskbar

download [thide](https://github.com/amnweb/thide) and install via the .msi installer.

```powershell
#start
thide start

#enable autostart
thide enable-autostart

#disable autostart
thide disable-autostart
```

and that's it, you're done.
