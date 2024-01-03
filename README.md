   <!-- MANPAGE: BEGIN EXCLUDED SECTION -->
# Ubuntu Mod
This is my ubuntu customization, includes the initial process, very useful tools and everyday use apps. plus the gnome-extensions i use to make the interface look amazing and alot more
<div align="center">

[![Ubuntu-Mod](https://github.com/zaeemali272/Ubuntu-Mod/blob/main/imgs/main.png)](#readme)

</div>
<!-- MANPAGE: END EXCLUDED SECTION -->

<!-- MANPAGE: BEGIN EXCLUDED SECTION -->
* [UBUNTU MOD](#ubuntu-mod)
* [INSTALLATION](#installation)
    * [Updating And Upgrading Ubuntu](#updating-and-upgrading-ubuntu)
    * [Installing Nala To Replace Apt](#installing-nala-to-replace-apt)
    * [Installing Flatpak And Useful Apps](#installing-flatpak-and-useful-apps)
    * [Installing Gnome Tweaks And Extension Manager](#installing-gnome-tweaks-and-extension-manager)
    * [Extra Tools](#extra-tools)
    * [Setting Up Spicetify](#setting-up-spicetify)
    * [Installing Thorium Browser( Chromium Fork )](#installing-thorium-browser-chromium-fork-)
    * [Installing Mercury Browser( Firefox Fork )](#installing-mercury-browser-firefox-fork-)
    * [Installing Visual Studio Code](#installing-visual-studio-code)
* [REMOVING SNAP](#removing-snap)
<!-- MANPAGE: END EXCLUDED SECTION -->

# INSTALLATION
**You can either auto-install the whole setup or or install manually according to your preference**

## Updating And Upgrading Ubuntu
```
#First Update & Upgrade Ubuntu
sudo apt update && sudo apt upgrade -y

```

## Installing Nala To Replace Apt
```
sudo apt install nala -y
sudo nala fetch
sudo nala update && sudo nala upgrade -y
```

**Important**: If warning appear while upgrading then remove those repositories from  `Software & Updates -> Other Software -> Remove repos causing error` and repeat previous step

## Installing Flatpak And Useful Apps
**Note**: Remove link to any app you dont want
```
sudo nala install flatpak -y
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```
**Important**: Restart your device after installing flatpak or after installing apps, **Flatpak apps will be visible after restart**

```
flatpak install flathub -y tv.kodi.Kodi com.spotify.Client com.discordapp.Discord org.qbittorrent.qBittorrent org.videolan.VLC com.github.IsmaelMartinez.teams_for_linux com.github.GradienceTeam.Gradience
```

## Installing Gnome Tweaks And Extension Manager
```
sudo nala install gnome-tweaks -y
sudo nala install gnome-shell-extension-manager -y
```

### Installing Gnome Extenions
[![Installing Gnome Extenions](https://github.com/zaeemali272/Ubuntu-Mod/blob/main/imgs/extension-manager.png)](#readme)
**Open the Extension Manager and from the browse tab search and install the following extenxions**:

`Blur My Shell` / `Burn My Window`  / `Just Perfection` / `Hide Top Bar` / `Caffeine` / `User Themes` / `Clipboard Indicator` / `Fullscreen Notifications` / `Dash To Dock` / `Aylur's Widgets` / `Gnome 4x Improvements` / `Impatience` / `Net Speed Simplified` / `Removable Drive Menu` / `Simple System Monitor` / `Todo.txt` / `Unite`

## Extra Tools
```
sudo nala install stacer curl git neofetch -y
```

## Installing YT-DLP
```
sudo curl -L https://github.com/yt-dlp/yt-dlp/releases/latest/download/yt-dlp -o /usr/local/bin/yt-dlp
sudo chmod a+rx /usr/local/bin/yt-dlp  # Make executable
```
To update, run:
```
sudo yt-dlp -U
```

### Enabling Restricted Codecs
```
sudo apt install ubuntu-restricted-extras -y
```

### Enabling Minimizing And Maximing From Dock
```
gsettings set org.gnome.shell.extensions.dash-to-dock click-action 'minimize-or-previews'
```

## Setting Up Spicetify
[![Setting Up Spicetify](https://github.com/zaeemali272/Ubuntu-Mod/blob/main/imgs/spicetify.png)](#readme)
**Spicetify is a multiplatform command-line tool to customize the official Spotify client**

### Installation
```
curl -fsSL https://raw.githubusercontent.com/spicetify/spicetify-cli/master/install.sh | sh
flatpak run com.spotify.Client
curl -fsSL https://raw.githubusercontent.com/spicetify/spicetify-marketplace/main/resources/install.sh | sh
```
**NOTE**:The process of adding marketplace will fail to fix this close spotfiy and do the following:

```
# open config-xpui.ini and add the below line to the prefs_path
#   /home/zaeem/.var/app/com.spotify.Client/config/spotify/prefs
```

**Then run this in terminal**:
```
curl -fsSL https://raw.githubusercontent.com/spicetify/spicetify-marketplace/main/resources/install.sh | sh
```

**Finally in terminal, set read/write permission for it**:
```
sudo chmod a+wr /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify
sudo chmod a+wr -R /var/lib/flatpak/app/com.spotify.Client/x86_64/stable/active/files/extra/share/spotify/Apps
spicetify backup apply
```

### Customization
**Open Spotify and go to Marketplace -> Extensions and install these extensions**
`Adblocker` / `Autoplay`

**Then Go to the Themes and install Galaxy or try any other**


## Installing Thorium Browser( Chromium Fork )
```
wget https://dl.thorium.rocks/debian/dists/stable/thorium.list
sudo mv thorium.list /etc/apt/sources.list.d/
sudo apt update
sudo apt install thorium-browser
```

## Installing Mercury Browser( Firefox Fork )
**Download the Deb file for [Mercury Browser](https://github.com/Alex313031/Mercury/releases/download/v.115.4.0/mercury-browser_115.4.0_amd64.deb)**


**After the download is finished run the following in a new terminal window**:
```
cd Downloads
sudo nala install mercury-browser_115.4.0_amd64.deb
```

### Replacing the mercury icon
To change the icon:
```
sudo nano /usr/share/applications/mercury-browser.desktop
```
Add the location of the png after Icon=
```
/home/zaeem/.icons/firefox-nightly.png
```
[![Replacing the mercury icon](https://github.com/zaeemali272/Ubuntu-Mod/blob/main/imgs/iconch.png)](#readme)
**NOTE**: Just change the zaeem with your username.


### Useful Browser Extensions
**Open the Mercury Browser and install these useful extensions**:

`Ublock Origin` / `Bonjour` / `Auto Discard Tab` / `'Improve YouTube!' 🎧 (for YouTube & Videos)`

**IMPORTANT**: Go to mercury settings and under `Performance` disable `Use recommended performance settings` for smoother video( Fix buffer )

**NOTE**: If the video is still laging disable `Use hardware acceleration when available` as well

**NOTE**: To disable menu-bar on alt key in browser(Firefox) than go to `about:config` and set `ui.key.menuAccessKeyFocuses` to `false`

## Installing Visual Studio Code
```
sudo apt install software-properties-common apt-transport-https wget
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
sudo apt install code -y
```

## Installing ProtonVPN
**Download the Deb file for [Proton VPN](https://repo.protonvpn.com/debian/dists/stable/main/binary-all/protonvpn-stable-release_1.0.3-2_all.deb)**

**After the download is finished run the following in a new terminal window**:
```
cd Downloads
sudo dpkg --install protonvpn-stable-release_1.0.3-2_all.deb
sudo apt-get update
sudo apt-get install proton-vpn-gnome-desktop
sudo apt install libayatana-appindicator3-1 gir1.2-ayatanaappindicator3-0.1 gnome-shell-extension-appindicator
```

# Install Tlauncher For Minecraft 
```
sudo apt-get install openjdk-8-jre
sudo apt-get install openjfx
mv Downloads/TLauncher-2.895/TLauncher-2.895.jar .config/
java -jar .config/TLauncher-2.895.jar

```
To get a free 6GB neverending server head over to [Scalacube](https://scalacube.com)

# REMOVING SNAP
To remove snap completely from ubuntu:
```
snap list
```
[![REMOVING SNAP](https://github.com/zaeemali272/Ubuntu-Mod/blob/main/imgs/snap-list.png)](#readme)

```
sudo snap remove --purge firefox
sudo snap remove --purge snap-store
sudo snap remove --purge gnome-3-38-2004
sudo snap remove --purge gnome-42-2204
sudo snap remove --purge gtk-common-themes
sudo snap remove --purge snapd-desktop-integration
sudo snap remove --purge bare
sudo snap remove --purge core22
sudo snap remove --purge core20
sudo snap remove --purge snapd
```
After removing all the snap packages:
```
sudo apt remove --autoremove snapd
```
That’s not all. Even if you removed the snaps using the above command, the sudo apt update command again brings back the snap if you don’t stop the apt trigger. 
So, to stop that, we need to create an apt preference file in /etc/apt/preferences.d/ and create a new preference file to stop snap. Create a new file called nosnap.pref in /etc/apt/preferences.d/
```
sudo nano /etc/apt/preferences.d/nosnap.pref
```
And add the following lines, then save the file.
```
Package: snapd
Pin: release a=*
Pin-Priority: -10
```


**NOTE**: To Disable Logout and Shutdown prompts:
```
gsettings set org.gnome.SessionManager logout-prompt false
```
