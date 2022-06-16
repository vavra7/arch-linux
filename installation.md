# INSTALLATION
https://wiki.archlinux.org/title/installation_guide

## SET KEYBOARD LAYOUT
1) run
```
# ls /usr/share/kbd/keymaps/**/cz*.map.gz
# loadkeys cz-qwertz
```

## CONNECT TO WI-FI
1) use iwctl utility
```
iwctl
```
2) find device name in device list
```
device list
```
3) scan for networks (command will not output anything)
```
station <device> scan
```
4) list of all available networks
```
station <device> get-networks
```
5) connect to a network
```
station <device> connect <network>
```
6) exit iwctl utility
```
exit
```
7) verify connection
```
ping google.com
```

##  LAUNCH INSTALL SCRIPT

https://wiki.archlinux.org/title/Archinstall

1) run
```
archinstall
```