# dotfiles

you were born to use linux but forced to use windows? i got you. anyway, you can jump to: [preview](#preview) · [components](#components) · [setup](#setup) · [prerequisites](#prerequisites) · [install dependencies](#install-dependencies) · [step-by-step installation](#step-by-step-installation)

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

## setup

### prerequisites

- Windows 11
- [Scoop](https://scoop.sh) or [winget](https://aka.ms/getwinget) (usually pre-installed on Windows 11)

**Scoop:**
```powershell
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
irm get.scoop.sh | iex
```

**winget:** ships with Windows 11 by default.

---

### step-by-step installation
you can actually follow this step to have the exact output, or you can skip to the desire part : [cursors](#cursors) · [ExplorerBlurMica](#ExplorerBlurMica) · [flow-launcher](#flow-launcher) · [komorebi](#komorebi) · [windhawk](#windhawk) · [windows-terminal](#windows-terminal) · [winfetch](#winfetch) · [yasb](#yasb) · [hide-taskbar](#hide-taskbar)

---

### cursors

this is the cursor i use: [![cursors](https://github.com/user-attachments/assets/a79f7d6f-f61d-4d43-8962-c7a3a72b76bb)](https://vsthemes.org/en/cursors/anime/70655-miyabi-zzz.html)

install by running `install.inf` → right click → install, then apply via mouse settings.

shoutout to **aliline** for making this cursor. if you want to explore more, visit [vsthemes](https://vsthemes.org/en/cursors/).

---

### ExplorerBlurMica

download the latest release from the [repository](https://github.com/Maplespe/ExplorerBlurMica/releases), extract, and run `ExplorerBlurMica.exe`. it all set actually, but you can import your preferred preset or configure manually via the GUI.

---

### flow-launcher

<div align="center">
  <img src="https://github.com/user-attachments/assets/98d2f0d6-1072-482d-84ea-25350d832d5f">
</div>

download and install [Flow Launcher](https://github.com/Flow-Launcher/Flow.Launcher/releases), then copy the theme file to your themes folder:

copy `flow-launcher/calm-blue.xaml` to `%APPDATA%\FlowLauncher\Themes\`

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

install via scoop:

```powershell
scoop bucket add extras
scoop install komorebi whkd
```

or via winget:

```powershell
winget install LGUG2Z.komorebi
winget install LGUG2Z.whkd
```

quickstart:

```powershell
komorebic start --whkd
```

enable autostart:

```powershell
komorebic enable-autostart --whkd
```

apply config by copying `komorebi/komorebi.json` to `%USERPROFILE%\komorebi.json`, then reload:

```powershell
komorebic reload-configuration
```
