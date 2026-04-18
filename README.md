# Arch Linux Hyprland Config

Minimal, reproducible dotfiles for a Hyprland-based setup with Waybar.

## Overview

* Window Manager: Hyprland
* Status Bar: Waybar
* Terminal: kitty
* File Manager: nemo
* Launcher: wofi
* Browser: brave

## Waybar

![Waybar Screenshot](/screenshot/waybar.png)



## Dependencies

Install required packages:

```bash
sudo pacman -S hyprland waybar kitty nemo wofi brave \
wl-clipboard grim slurp brightnessctl playerctl \
pipewire wireplumber hyprpaper
```



## Installation

```bash
git clone https://github.com/935lngabriel/arch-linux-hyprland-cfg.git
cd arch-linux-hyprland-cfg

# install
mkdir -p ~/.config/hypr
cp hyprland.conf ~/.config/hypr/hyprland.conf
mkdir -p ~/.config/waybar
cp config.jsonc ~/.config/waybar/config.jsonc
cp style.css ~/.config/waybar/style.css
```



## Hyprland Configuration

### Core Behavior

* Layout: `dwindle`
* Gaps: inner `2`, outer `10`
* Border: `2px`
* Blur + shadows enabled
* Animations enabled

### Theme

* GTK dark mode via `gsettings`
* Qt theme via `qt6ct`
* Cursor size: `24`

### Monitor

```conf
monitor=,1920x1080,0x0,1
```

### Autostart

```conf
exec-once = waybar & hyprpaper
```



## Keybindings

### Core

| Action       | Key         |
| ------------ | ----------- |
| Terminal     | SUPER + T   |
| File Manager | SUPER + E   |
| Browser      | SUPER + B   |
| Launcher     | SUPER + P   |
| Kill Window  | SUPER + C   |
| Exit         | SUPER + ESC |
| Toggle Float | SUPER + V   |

### Window Management

| Action        | Key                 |
| ------------- | ------------------- |
| Move focus    | SUPER + Arrows      |
| Move window   | SUPER + Mouse Drag  |
| Resize window | SUPER + Right Mouse |

### Workspaces

| Action                   | Key                   |
| ------------------------ | --------------------- |
| Switch workspace         | SUPER + [0-9]         |
| Move window to workspace | SUPER + SHIFT + [0-9] |
| Scroll workspaces        | SUPER + Mouse Wheel   |

### Special Workspace

| Action             | Key               |
| ------------------ | ----------------- |
| Toggle scratchpad  | SUPER + S         |
| Send to scratchpad | SUPER + SHIFT + S |

### Media / System

| Action          | Key                   |
| --------------- | --------------------- |
| Volume Up       | XF86AudioRaiseVolume  |
| Volume Down     | XF86AudioLowerVolume  |
| Mute            | XF86AudioMute         |
| Mic Mute        | XF86AudioMicMute      |
| Brightness Up   | XF86MonBrightnessUp   |
| Brightness Down | XF86MonBrightnessDown |

### Screenshot

```conf
bind = $mainMod, PRINT, exec, hyprshot -m region -o /home/gabriel/pictures/screenshots
```


## Waybar

* `config`: modules and layout
* `style.css`: theme and styling

Restart:

```bash
killall waybar; waybar
```

## Customization

### Change Apps

```conf
$terminal = kitty
$fileManager = nemo
$menu = wofi --show drun
$browser = brave
```

### Input

* Layout: `br`
* Variant: `abnt2`

### Adjust Monitor

Edit:

```conf
monitor=,1920x1080,0x0,1
```