# gentoo-dwl-setup

Minimal Gentoo setup based on **dwl (Wayland)** with NVIDIA, PipeWire and custom Portage configuration.

This is **not a dotfiles repository**.
There are no `~/.config` files here.

This repository contains:

* system-level configuration (`/etc/portage`)
* build configs (savedconfig, patches)
* manually built components (dwl, slstatus)

---

# What is inside

## Portage configuration

Located in:

```bash
portage/
```

Includes:

* `make.conf` → global build settings
* `package.use/*` → USE flags
* `package.accept_keywords/*` → ~arch packages
* `package.license` → accepted licenses
* `repos.conf/*` → overlays
* `savedconfig/*` → build-time configs (dwl, foot)

---

## Manual components

### dwl

* configured via `savedconfig`
* patched manually (`patches/`)
* built outside of Portage

### slstatus

Located in:

```bash
slstatus/
```

Minimal status bar (suckless-style).
Built manually:

```bash
make
sudo make install
```

---

## Runtime

```bash
autostart.sh
```

Example startup script for dwl.

---

# Repository structure

```bash
portage/
 ├── make.conf
 ├── package.use/
 ├── package.accept_keywords/
 ├── package.license
 ├── repos.conf/
 └── savedconfig/

patches/
slstatus/
autostart.sh
```

---

# Base packages

This setup expects at least:

## Core

* gui-wm/dwl
* gui-libs/wlroots
* x11-terms/foot
* sys-auth/seatd

## Graphics

* x11-drivers/nvidia-drivers

## Audio

* media-video/pipewire
* media-sound/pulseaudio

## Tools / apps

* app-editors/neovim
* media-video/obs-studio
* dev-qt/qtbase

Additional packages are implied by configs and must be resolved manually.

---

# Overlays

Required overlays are defined in:

```bash
portage/repos.conf/*
```

## Enable GURU

```bash
emerge -av app-eselect/eselect-repository
eselect repository enable guru
emerge --sync
```

---

# How to use

No automated setup.

Basic flow:

```bash
cp -r portage/* /etc/portage/
```

Then:

1. Enable overlays
2. Sync repositories
3. Install required packages
4. Build dwl manually (with patches)
5. Build slstatus
6. Adapt to your system

---

# For whom

* users familiar with Gentoo
* people using Wayland + minimal WM (dwl)
* those who want to see a real `/etc/portage` setup

Not intended for beginners.
