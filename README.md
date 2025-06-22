# Cinnamon Dotfiles

This repository contains my custom Linux Mint Cinnamon desktop configuration, themes, cursors, applets, and extensions. It tracks:

* **`cinnamon-settings.dconf`**: a full Dconf dump of my Cinnamon settings
* **Icon Themes & Cursors**:

  * `Future-cyan-cursors`
  * `Metatron-Cyan`
  * `Nordic-darker-standard-buttons-v40`
  * `Tela-circle-nord-dark`
* **Cinnamon Spices** (applets, extensions, desklets, etc.) under `cinnamon/`

---

## Features

* Version-controlled backup of all your Cinnamon tweaks
* Easy to clone & apply on a fresh install
* Track icon/theme modifications alongside applets and extensions

---

## Getting Started

### Prerequisites

* Linux Mint (or any distribution running Cinnamon)
* Git
* `dconf` command-line tool

### Clone the repository

```bash
git clone git@github.com:lukantozi/cinnamon-dotfiles.git ~/.dotfiles/cinnamon
cd ~/.dotfiles/cinnamon
```

### Apply Cinnamon settings

Load the Dconf dump to apply your settings:

```bash
dconf load /org/cinnamon/ < cinnamon-settings.dconf
```

### Install Themes & Cursors

Copy your custom themes and cursors into the appropriate user directories:

```bash
# Icon themes
cp -r Future-cyan-cursors ~/.icons/
cp -r Metatron-Cyan ~/.themes/
cp -r Nordic-darker-standard-buttons-v40 ~/.icons/
cp -r Tela-circle-nord-dark ~/.themes/
```

Then select them in **System Settings → Themes/Cursors**.

### Install Applets & Extensions

Copy the `cinnamon/` folder contents into your Cinnamon `spices` directory (usually `~/.local/share/cinnamon/`):

```bash
cp -r cinnamon/* ~/.local/share/cinnamon/
```

Restart Cinnamon or log out/in to activate your applets and extensions.

---

## Customization & Updates

When you tweak settings or install new spices:

1. Dump your settings:

   ```bash
   dconf dump /org/cinnamon/ > cinnamon-settings.dconf
   ```
2. Stage & commit:

   ```bash
   git add .
   git commit -m "Update settings or add new spice"
   git push
   ```

---

## Repository Structure

```
.
├── Future-cyan-cursors/
├── Metatron-Cyan/
├── Nordic-darker-standard-buttons-v40/
├── Tela-circle-nord-dark/
├── cinnamon/                # Custom applets, desklets & extensions
├── cinnamon-settings.dconf  # Dconf dump of Cinnamon settings
├── .gitignore
└── README.md
```

---
