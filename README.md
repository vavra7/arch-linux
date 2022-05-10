# Arch Linux Up and Running

installation and post-installation guide

## installation
https://wiki.archlinux.org/title/installation_guide

### set keyboard layout 

```
# ls /usr/share/kbd/keymaps/**/cz*.map.gz
# loadkeys cz-qwertz
```

### connect to wi-fi
use iwctl utility
```
iwctl
```

find device name in device list
```
device list
```

scan for networks (command will not output anything)
```
station <device> scan
```

list of all available networks
```
station <device> get-networks
```

connect to a network
```
station <device> connect <network>
```

exit iwctl utility
```
exit
```

verify connection
```
ping google.com
```

###  official install script
https://wiki.archlinux.org/title/Archinstall

run
```
archinstall
```
## post-installation

### add user to sudoers

switch to root
```
su root
```

add user to wheel group
```
usermod -G wheel <user>
```

set default editor to vim
```
export EDITOR="vim"
```

uncomment wheel group in sudoers file
```
visudo
```

back to your user
```
su <user>
```

check user is in wheel group
```
groups
```

### change keyboard layout for GNOME Display Manager
https://wiki.archlinux.org/title/GDM#Keyboard_layout
```
localectl set-x11-keymap cz
```

### install arch packages (pacman)
#### fonts
```
sudo pacman -S adobe-source-code-pro-fonts adobe-source-sans-fonts adobe-source-serif-fonts cantarell-fonts freetype2 noto-fonts ttf-bitstream-vera ttf-dejavu ttf-liberation ttf-opensans
```
#### other
- gst-libav - codec for gnome player
- pacman-contrib - necessary for "Arch Linux Updates Indicator" extension
```
sudo pacman -S keepassxc git vlc libreoffice-still gst-libav neofetch thunderbird pacman-contrib kdenlive
```

### install yay

clone official repo
```
git clone https://aur.archlinux.org/yay.git
```

enter yay directory
```
cd ./yay
```

use the makepkg command to build and install yay
```
makepkg -si
```

### install AUR packages (yay)
### nvm
```
# yay -S nvm
# echo 'source /usr/share/nvm/init-nvm.sh' >> ~/.bashrc
```
terminal restart is needed
#### other
- chrome-gnome-shell - allows installing gnome extensions from chromium based browsers
```
yay -S brave-bin onedriver chrome-gnome-shell visual-studio-code-bin
```

### fish shell
install
```
sudo pacman -S fish
```
#### change Arch default shell

https://wiki.archlinux.org/title/Command-line_shell#Changing_your_default_shell

list available shells & change shell
```
# chsh -l
# chsh -s <full-path-to-shell>
```

#### change GNOME Terminal default shell
- launch Terminal app 
- navigate "Preferences -> 'profile' -> Command"
- check "Run a custom command instead of my shell"
- custom command "fish"

#### VS Code change default terminal
- navigate "Terminal: Select Default Profile"
- select "fish"

### GNOME extensions
- https://extensions.gnome.org/extension/1010/archlinux-updates-indicator/
- https://extensions.gnome.org/extension/1460/vitals/
- https://extensions.gnome.org/extension/517/caffeine/
- https://extensions.gnome.org/extension/779/clipboard-indicator/
- https://extensions.gnome.org/extension/3396/color-picker/



