# installation
https://wiki.archlinux.org/title/installation_guide

## set keyboard layout 

```
# ls /usr/share/kbd/keymaps/**/cz*.map.gz
# loadkeys cz-qwertz
```

## connect to wi-fi
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

##  launch install script

https://wiki.archlinux.org/title/Archinstall

run
```
archinstall
```