# post-installation

## add user to sudoers

1) switch to root
```
su root
```

2) add user to wheel group
```
usermod -G wheel <user>
```

3) set default editor to vim
```
export EDITOR="vim"
```

4) uncomment wheel group in sudoers file
```
visudo
```

5) back to your user
```
su <user>
```

6) check user is in wheel group
```
groups
```

## change keyboard layout for GNOME Display Manager
https://wiki.archlinux.org/title/GDM#Keyboard_layout
```
localectl set-x11-keymap cz
```

## allow locales
1) uncomment locale in file `/etc/locale.gen`
2) generate locale
```
sudo locale-gen
```
3) verify 
```
locale -l
```

## add my SSH
https://wiki.archlinux.org/title/SSH_keys

1) copy ".ssh" folder in `/home/<user>`
2) change permission of the folder
```
sudo chmod 700 -R ./.ssh/
```
3) add ssh key
```
ssh-add
```

## install arch packages (pacman)
### fonts
```
sudo pacman -S adobe-source-code-pro-fonts adobe-source-sans-fonts adobe-source-serif-fonts cantarell-fonts freetype2 noto-fonts ttf-bitstream-vera ttf-dejavu ttf-liberation ttf-opensans
```
### other
- `gst-libav` - codec for gnome player
- `pacman-contrib` - necessary for "Arch Linux Updates Indicator" extension
```
sudo pacman -S keepassxc git vlc libreoffice-still gst-libav neofetch thunderbird pacman-contrib kdenlive fish gnome-bluetooth
```

## bluetooth
precondition: installed `gnome-bluetooth` (pacman)

1) enable service
```
# sudo systemctl enable bluetooth
# sudo systemctl start bluetooth
# sudo systemctl status bluetooth
```
2) set `AutoEnable=true` in `/etc/bluetooth/main.conf`


## install yay
1) from official repo build and install
```
# git clone https://aur.archlinux.org/yay.git
# cd ./yay
# makepkg -si
```

## install AUR packages (yay)
### nvm
1) install
```
# yay -S nvm
# echo 'source /usr/share/nvm/init-nvm.sh' >> ~/.bashrc
```
2) restart terminal
### other
- `chrome-gnome-shell` - allows installing gnome extensions from chromium based browsers
```
yay -S brave-bin onedriver chrome-gnome-shell visual-studio-code-bin gnome-text-editor
```

## remove packages
```
sudo pacman -R gedit
```

## set default fish shell
precondition: installed `fish` (pacman)
### change Arch default shell
https://wiki.archlinux.org/title/Command-line_shell#Changing_your_default_shell
1) list available shells & change shell
```
# chsh -l
# chsh -s <full-path-to-shell>
```

### change GNOME Terminal default shell
1) launch Terminal app 
2) navigate "Preferences -> 'profile' -> Command"
3) check "Run a custom command instead of my shell"
4) custom command `fish`

### change VS Code default terminal
1) navigate "Terminal: Select Default Profile"
2) select "fish"

## add GNOME extensions
- https://extensions.gnome.org/extension/1010/archlinux-updates-indicator/
- https://extensions.gnome.org/extension/1460/vitals/
- https://extensions.gnome.org/extension/517/caffeine/
- https://extensions.gnome.org/extension/779/clipboard-indicator/
- https://extensions.gnome.org/extension/3396/color-picker/