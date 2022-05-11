# post-installation

## add user to sudoers

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

## change keyboard layout for GNOME Display Manager
https://wiki.archlinux.org/title/GDM#Keyboard_layout
```
localectl set-x11-keymap cz
```

## allow locales
uncomment locale in file
```
sudo vim /etc/locale.gen
```
generate locale
```
sudo locale-gen
```
verify 
```
locale -l
```

## add my SSH
https://wiki.archlinux.org/title/SSH_keys

copy ".ssh" folder in "/home/\<user\>"

change permission of the folder
```
sudo chmod 700 -R ./.ssh/
```
add ssh key
```
ssh-add
```

## install arch packages (pacman)
### fonts
```
sudo pacman -S adobe-source-code-pro-fonts adobe-source-sans-fonts adobe-source-serif-fonts cantarell-fonts freetype2 noto-fonts ttf-bitstream-vera ttf-dejavu ttf-liberation ttf-opensans
```
### other
- gst-libav - codec for gnome player
- pacman-contrib - necessary for "Arch Linux Updates Indicator" extension
```
sudo pacman -S keepassxc git vlc libreoffice-still gst-libav neofetch thunderbird pacman-contrib kdenlive
```

## install yay

from official repo build and install
```
# git clone https://aur.archlinux.org/yay.git
# cd ./yay
# makepkg -si
```

## install AUR packages (yay)
### nvm
```
# yay -S nvm
# echo 'source /usr/share/nvm/init-nvm.sh' >> ~/.bashrc
```
terminal restart is needed
### other
- chrome-gnome-shell - allows installing gnome extensions from chromium based browsers
```
yay -S brave-bin onedriver chrome-gnome-shell visual-studio-code-bin gnome-text-editor
```

## remove packages
```
sudo pacman -R gedit
```

## fish shell
install
```
sudo pacman -S fish
```
### change Arch default shell

https://wiki.archlinux.org/title/Command-line_shell#Changing_your_default_shell

list available shells & change shell
```
# chsh -l
# chsh -s <full-path-to-shell>
```

### change GNOME Terminal default shell
- launch Terminal app 
- navigate "Preferences -> 'profile' -> Command"
- check "Run a custom command instead of my shell"
- custom command "fish"

### change VS Code default terminal
- navigate "Terminal: Select Default Profile"
- select "fish"

## add GNOME extensions
- https://extensions.gnome.org/extension/1010/archlinux-updates-indicator/
- https://extensions.gnome.org/extension/1460/vitals/
- https://extensions.gnome.org/extension/517/caffeine/
- https://extensions.gnome.org/extension/779/clipboard-indicator/
- https://extensions.gnome.org/extension/3396/color-picker/
