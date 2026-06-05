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
you can actually follow this step to have the same exact output, or you can skip to the desire part : [cursors](#cursors) · [ExplorerBlurMica](#ExplorerBlurMica) · [flow-launcher](#flow-launcher) · [komorebi](#komorebi) · [windhawk](#windhawk) · [windows-terminal](#windows-terminal) · [winfetch](#winfetch) · [yasb](#yasb) · [hide-taskbar](#hide-taskbar)

---

### cursors

this is the cursor i use: [![cursors](https://github.com/user-attachments/assets/a79f7d6f-f61d-4d43-8962-c7a3a72b76bb)](https://vsthemes.org/en/cursors/anime/70655-miyabi-zzz.html)

install by running `install.inf` → right click → install, then apply via mouse settings.

shoutout to **aliline** for making this cursor. if you want to explore more, visit [vsthemes](https://vsthemes.org/en/cursors/).

---

### ExplorerBlurMica

download the latest release from the [repository](https://github.com/Maplespe/ExplorerBlurMica/releases), extract, and run `register.cmd`. it all set actually, but you can import your preferred preset or configure manually via the GUI.

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

---

### windows-terminal

<div align="center">
  <img src="https://github.com/user-attachments/assets/8fe41676-f1a5-4a00-981c-16cbbbc30952">
</div>

for applying config, press terminal then click right on the bar → settings → Open JSON file → Copy everything from `windows-terminal\settings.json` and paste it to terminal JSON file. In Appearance → Application Theme → Choose `Catppuccin Mocha`. And in Color Schemes, choose `Catppuccin Mocha` too.  Yes, i use [catppuccin mocha](https://github.com/catppuccin/windows-terminal/tree/main) for this theme.

For make the liquid glass effect, go to defaults in profile → Appearance → Scroll down to `transparency` and turn the background opacity to 40% and enable acrylic material. 

---

### winfetch 

you can install winfetch using the following methods:

**Powershell Gallery** (reccomended) offers the fastest execution and tab completion.
```powershell
Install-Script winfetch
```

winget
```powershell
winget install winfetch
```

scoop
```powershell
scoop install winfetch
```

(optional) and for make it run everytime you open terminal, you need to write `winfetch` command in your profile.
```powershell
notepad $PROFILE
```
then,
```powershell
winfetch
```

---

### yasb

download and install the lastest version of [yasb](https://github.com/amnweb/yasb). i use .msi installer. but you can use:

winget
```powershell
winget install AmN.yasb
```

scoop
```powershell
scoop bucket add extras
scoop install extras/yasb
```

for applying config
copy `config.yaml` & `style.css` in my [yasb](https://github.com/oeziesan/calm-blue/tree/main/yasb) folder to `%USER%\.config\yasb`. then reload bar.

---

### windhawk

in my mod, i'll hide default taskbar and change to yasb. i use windhawk for moving the `quicksettings` and `notification center` on the top.

| mods | purpose | theme used |
|---|---| --- |
| Resource Indirect | change icon themes | macOS DarkMode (by Niivu) |
| Taskbar on top for Windows 11 | move taskbar and start menu on top | - |
| Windows 11 Notification Center Styler | styler for notification center, but also to make notification center is on top | Translucent Shell |
| Windows 11 Start Menu Styler | styler for start menu | Down Aero |

you can actually follow my theme or not, it's really optional.

for moving the notification center to the top, copy the content of `windhawk/notification-center.json` to advanced → mod settings → save.

---

### hide-taskbar

download [thide](https://github.com/amnweb/thide) and install using the .msi installer.

CLI
```powershell
#start
thide start

#enable autostart
thide enable-autostart

#disable autostart
thide disable-autostart
```

done, it all set.

