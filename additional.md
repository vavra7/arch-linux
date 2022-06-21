# ADDITIONAL
## VIRTUALBOX
https://wiki.archlinux.org/title/VirtualBox
1) install
```
sudo pacman -S virtualbox virtualbox-guest-utils
```
2) choose `virtualbox-host-modules-arch` option
3) launch and disable *preferences -> Input -> Auto Capture Keyboard* (Causes freezing on Wayland)
4) reboot host before running virtual machine

### activate Windows in VirtualBox from OEM
https://superuser.com/questions/1402949/oem-license-activation-for-windows-10-home-virtualbox-guest-on-ubuntu-host
1) find activation key
```
sudo strings /sys/firmware/acpi/tables/MSDM
```
2) activate windows
