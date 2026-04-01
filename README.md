> [!WARNING]
> This is an **unofficial fork** of the original project [uiriansan/SilentSDDM](https://github.com/uiriansan/SilentSDDM), based on commit [34f82e1fb8412fff78b82a0dcce763492b36054c](https://github.com/uiriansan/SilentSDDM/commit/34f82e1fb8412fff78b82a0dcce763492b36054c).
> It exists for **my personal use only**; if you decide to use it, you do so **entirely at your own risk**.
> Thank you to the original project for the inspiration and work.

> [!WARNING]
> This theme requires **SDDM v0.21.0 or newer**. Make sure your distro provides the correct version before installing.

> [!IMPORTANT]
> Want SilentSDDM to also be available as a lockscreen service? Take a look into [this discussion (in the original project)](https://github.com/uiriansan/SilentSDDM/discussions/78).

# Dependencies

- SDDM ≥ 0.21;
- QT ≥ 6.5;
- qt6-svg;
- qt6-virtualkeyboard
- qt6-multimedia

# Installation
[`Install script`](#Install-script) [`Manual installation`](#Manual-installation)

## Install script
Just clone the repo and run the script:

```bash
git clone -b main --depth=1 https://github.com/hendrikboeck/SilentSDDM && cd SilentSDDM && ./install.sh
```

> [!IMPORTANT]
> Make sure to test the theme before rebooting by running `./test.sh`, otherwise you might end up with a broken login screen.

### Local development and testing under nix
First git clone the repository and cd into the resulting directory
```bash
git clone https://github.com/hendrikboeck/SilentSDDM.git
cd SilentSDDM/
```

Now you may make changes to the contents and test them out using the
following

```bash
nix run .#test
```

## Manual installation

### 1. Install dependencies:

#### Arch Linux

```bash
sudo pacman -S --needed sddm qt6-svg qt6-virtualkeyboard qt6-multimedia-ffmpeg
```

#### Void Linux

```bash
sudo xbps-install sddm qt6-svg qt6-virtualkeyboard qt6-multimedia
```

#### Fedora

```bash
sudo dnf install sddm qt6-qtsvg qt6-qtvirtualkeyboard qt6-qtmultimedia
```

#### OpenSUSE

```bash
sudo zypper install sddm-qt6 libQt6Svg6 qt6-virtualkeyboard qt6-virtualkeyboard-imports qt6-multimedia qt6-multimedia-imports
```

### 2. Clone this repo:
```bash
git clone -b main --depth=1 https://github.com/hendrikboeck/SilentSDDM
cd SilentSDDM/
```

### 3. Test the theme to make sure you have all dependencies:
```bash
./test.sh
```

### 4. Copy the theme to `/usr/share/sddm/themes/`:
```bash
cd SilentSDDM/
sudo mkdir -p /usr/share/sddm/themes/silent
sudo cp -rf . /usr/share/sddm/themes/silent/
```

### 5. Install the fonts:
```bash
sudo cp -r /usr/share/sddm/themes/silent/fonts/* /usr/share/fonts/
```

### 6. Replace the current theme and set the environment variables in `/etc/sddm.conf`:
```bash
sudoedit /etc/sddm.conf

    # Make sure these options are correct:
    [General]
    InputMethod=qtvirtualkeyboard
    GreeterEnvironment=QML2_IMPORT_PATH=/usr/share/sddm/themes/silent/components/,QT_IM_MODULE=qtvirtualkeyboard

    [Theme]
    Current=silent
```

# Acknowledgements

- [uiriansan/SilentSDDM](https://github.com/uiriansan/SilentSDDM): original project;
- [Keyitdev/sddm-astronaut-theme](https://github.com/Keyitdev/sddm-astronaut-theme): inspiration and code reference;
- [Match-Yang/sddm-deepin](https://github.com/Match-Yang/sddm-deepin): inspiration and code reference;
- [qt/qtvirtualkeyboard](https://github.com/qt/qtvirtualkeyboard): code reference;
- [Joyston Judah](https://www.pexels.com/photo/white-and-black-mountain-wallpaper-933054/): background;
- [DesktopHut](https://www.desktophut.com/blue-light-anime-girl-6794): background;
- [MoeWalls](https://moewalls.com/anime/ken-kaneki-tokyo-ghoul-re-3-live-wallpaper/): background;
- [MoeWalls](https://moewalls.com/anime/anime-girl-nissan-silvia-live-wallpaper/): background;
- [iconify.design](https://iconify.design/): icons
