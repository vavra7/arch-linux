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
station some-device-name scan
```

list of all available networks
```
station some-device-name get-networks
```

connect to a network
```
station some-device-name connect some-network-name
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
