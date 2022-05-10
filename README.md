# arch-linux

installation and post-installation guide

## installation
https://wiki.archlinux.org/title/installation_guide

### set keyboard layout 
see available
```
ls /usr/share/kbd/keymaps/**/cz*.map.gz
```
load layout
```
loadkeys cz-qwertz
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

### install arch packages (pacman)
```
sudo pacman -S keepassxc git vlc libreoffice-still
```

### install yay (AUR)

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

### install aur packages (yay)
```
yay -S brave-bin onedriver
```
