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

### freezing on startup with 11th and higher generation Intel CPU
- https://wiki.archlinux.org/title/VirtualBox#Freeze_during_virtual_machine_startup_with_11th_generation_Intel_CPU
- https://wiki.archlinux.org/title/Kernel_parameters

add kernel parameter `ibt=off` at the end of the line `linux /boot/vmlinuz-linux root=UUID=0a3407de-014b-458b-b5c1-848e92a327a3 rw quiet` in file `/boot/grub/grub.cfg`


### activate Windows in VirtualBox from OEM
https://superuser.com/questions/1402949/oem-license-activation-for-windows-10-home-virtualbox-guest-on-ubuntu-host
1) find activation key
```
sudo strings /sys/firmware/acpi/tables/MSDM
```
2) activate windows
