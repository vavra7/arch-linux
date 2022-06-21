# POST-INSTALLATION

## ADD USER TO SUDOERS

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

## CHANGE KEYBOARD LAYOUT
### in GNOME Display Manager
https://wiki.archlinux.org/title/GDM#Keyboard_layout
```
localectl set-x11-keymap cz
```

### in GNOME
https://github.com/michalkahle/czech-coder-xkb

1) allow selecting all layouts
```
gsettings set org.gnome.desktop.input-sources show-all-sources true
```
2) select in keyboard layout in GNOME *Settings -> Keyboard*

## INSTALL ARCH PACKAGES (PACMAN)
### fonts
```
sudo pacman -S adobe-source-code-pro-fonts adobe-source-sans-fonts adobe-source-serif-fonts cantarell-fonts freetype2 noto-fonts ttf-bitstream-vera ttf-dejavu ttf-liberation ttf-opensans
```
### other
- `gst-libav` - codec for gnome player
- `pacman-contrib` - necessary for "Arch Linux Updates Indicator" extension
- `cups`, `system-config-printer`, `ghostscript`, `gsfonts` - printing
- `ntfs-3g` - allows to read Microsoft ntfs file system
- `sane-airscan`, `simple-scan` - scanner
```
sudo pacman -S keepassxc git vlc libreoffice-still gst-libav neofetch thunderbird pacman-contrib kdenlive fish gnome-bluetooth cups system-config-printer ghostscript gsfonts transmission-gtk vi gimp drawing ntfs-3g sane-airscan simple-scan
```

## INSTALL YAY
1) from official repo build and install
```
# git clone https://aur.archlinux.org/yay.git
# cd ./yay
# makepkg -si
```

## INSTALL AUR PACKAGES (YAY)
- `chrome-gnome-shell` - allows installing gnome extensions from chromium based browsers
- `evdi-git`, `displaylink` - dependency for connecting monitors via docking station (https://wiki.archlinux.org/title/DisplayLink)
- `imagewriter` - writes .iso files on usb drive
```
yay -S brave-bin onedriver chrome-gnome-shell visual-studio-code-bin gnome-text-editor evdi-git displaylink imagewriter
```

## ALLOW LOCALES
1) uncomment locale in file `/etc/locale.gen`
2) generate locale
```
sudo locale-gen
```
3) verify 
```
locale -l
```

## ADD MY SSH
https://wiki.archlinux.org/title/SSH_keys

1) copy ".ssh" folder in `/home/<user>`
2) change permission of the folder
```
sudo chmod 700 -R ~/.ssh/
```
3) add ssh key
```
ssh-add
```

## BLUETOOTH
precondition: installed `gnome-bluetooth` (pacman)

1) enable service
```
# sudo systemctl enable bluetooth
# sudo systemctl start bluetooth
# sudo systemctl status bluetooth
```
2) set `AutoEnable=true` in `/etc/bluetooth/main.conf`

## PRINTER
https://wiki.archlinux.org/title/CUPS

https://wiki.archlinux.org/title/CUPS/Troubleshooting#Unable_to_add_printer_or_message_%22print_in_progress%22_but_nothing_happens

precondition: installed `cups`, `system-config-printer`, `ghostscript`, `gsfonts`  (pacman)

1) enable service
```
# sudo systemctl enable cups.service
# sudo systemctl start cups.service
# sudo systemctl status cups.service
```

## SCANNER
https://wiki.archlinux.org/title/SANE

precondition: installed `sane-airscan`, `simple-scan`

## REMOVE PACKAGES
```
sudo pacman -R gedit gnome-boxes gnome-books gnome-photos gnome-user-docs yelp
```

## SET DEFAULT FISH SHELL
precondition: installed `fish` (pacman)

### customize
1) install oh-my-fish - https://github.com/oh-my-fish/oh-my-fish
2) configure `fish_config`

### disable time stamp
https://askubuntu.com/questions/1010641/how-to-remove-the-time-stamp-on-the-right-side-of-the-fish-shell
1) `fish_config`
2) add at the end of `~/.config/fish/config.fish`
```
function fish_right_prompt
  #intentionally left blank
end
```

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
4) set custom command to `fish`

### change VS Code default terminal
1) navigate "Terminal: Select Default Profile"
2) select "fish"


## NVM
### for bash
1) install
```
# yay -S nvm
# echo 'source /usr/share/nvm/init-nvm.sh' >> ~/.bashrc
```
2) restart terminal
### for fish
1) install oh-my-fish - https://github.com/oh-my-fish/oh-my-fish
2) install fish-nvm - https://github.com/FabioAntunes/fish-nvm
3) return back prompt - `fish_config`

## ADD GNOME EXTENSIONS
- https://extensions.gnome.org/extension/1010/archlinux-updates-indicator/
- https://extensions.gnome.org/extension/1460/vitals/
- https://extensions.gnome.org/extension/517/caffeine/
- https://extensions.gnome.org/extension/779/clipboard-indicator/
- https://extensions.gnome.org/extension/3396/color-picker/
- https://extensions.gnome.org/extension/3780/ddterm/
