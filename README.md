# Make Linux Look Like MacOS - GNOME Desktop Environment

This Project is to make Ubuntu and other derivative distributions (Mint, PopOS, etc.) look like MacOS. *Version 20+ is required*

_Source Files in this project_
- https://www.gnome-look.org/p/1148692/ - Capitine Cursors
- https://www.pling.com/p/1403328/ - WhiteSur GTK Theme
- https://www.pling.com/p/1399044/ - BigSur Icon Theme
- https://github.com/PRATAP-KUMAR/focalgdm3 - Login Theme
- https://albertlauncher.github.io/docs/installing/ - Albert
- https://www.pling.com/p/1401527/ - Cairo Dock

## Installation

### Dependency Installs

```bash
sudo apt install git gnome-tweak-tool gnome-shell-extensions chrome-gnome-shell cairo-dock -y
git clone https://github.com/ChrisTitusTech/Linux-MacOS-GNOME.git ~/MacOS
mkdir ~/.themes
mkdir ~/.icons
mv ~/MacOS/themes/* ~/.themes
mv ~/MacOS/icons/* ~/.icons
sudo mv ~/MacOS/walls/* /usr/share/backgrounds/
```

### Gnome Tweaks

```bash
gsettings set org.gnome.mutter center-new-windows 'true'
gsettings set org.gnome.desktop.wm.preferences button-layout 'close,minimize,maximize:'
gsettings set org.gnome.desktop.interface gtk-theme "WhiteSur-dark"
gsettings set org.gnome.desktop.wm.preferences theme "WhiteSur-dark"
gsettings set org.gnome.desktop.interface icon-theme 'BigSur'
gsettings set org.gnome.desktop.interface cursor-theme 'capitaine-cursors-light'
gsettings set org.gnome.desktop.background picture-uri 'file:///usr/share/backgrounds/macOS-BS3.jpg'
gsettings set org.gnome.desktop.screensaver picture-uri 'file:///usr/share/backgrounds/macOS-BS1.jpg'
```

### Albert

For Pop!_OS 20.04 LTS
```bash
curl -fsSL 'https://download.opensuse.org/repositories/home:manuelschneid3r/xUbuntu_20.04/Release.key' | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/home_manuelschneid3r.gpg > /dev/null
echo 'deb http://download.opensuse.org/repositories/home:/manuelschneid3r/xUbuntu_20.04/ /' | sudo tee /etc/apt/sources.list.d/home:manuelschneid3r.list
sudo apt update
sudo apt install albert -y
```
For Pop!_OS 21.04
```bash
curl -fsSL 'https://download.opensuse.org/repositories/home:manuelschneid3r/xUbuntu_21.04/Release.key' | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/home_manuelschneid3r.gpg > /dev/null
echo 'deb http://download.opensuse.org/repositories/home:/manuelschneid3r/xUbuntu_21.04/ /' | sudo tee /etc/apt/sources.list.d/home:manuelschneid3r.list
sudo apt update
sudo apt install albert -y
```

- Launch Albert
- Set Hotkey - Meta + F
- Set Theme Arc Dark Blue
- Enable Albert Extensions

### Gnome Extensions

Enable Extensions by visiting https://extensions.gnome.org/ install add-on and reload browser

Install the Following Extensions
- User Themes - https://extensions.gnome.org/extension/19/user-themes/
- Frippery Move Clock - https://extensions.gnome.org/extension/2/move-clock/
- Dynamic Panel Transparency - https://extensions.gnome.org/extension/1011/dynamic-panel-transparency/
- Panel OSD - https://extensions.gnome.org/extension/708/panel-osd/

### Manual Extension Configurations

- Panel OSD - Change Horizontal and Vertical to 98
- Cairo Dock - Set to Startup Applications
- Cairo Dock Themes - Import all gz files to Cairo configure in ~/MacOS/cairo
- Cairo Dock Configure - Turn of Icon effects and animations and hide dock when overlapping windows
- Cairo Dock Launchpad - Add Custom Launchpad Shortcut `dbus-send --session --type=method_call --dest=org.gnome.Shell /org/gnome/Shell org.gnome.Shell.Eval string:'Main.shellDBusService.ShowApplications();'`
- Disable Ubuntu Dock (Not Needed on PopOS)
- Dynamic Panel Transparency - Background Tab - Max Opacity 100 - Min Opacity 50
