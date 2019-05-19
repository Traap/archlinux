[Back to Table of Contents](../README.md)
***

#### Post packstrap applicable to BIOS or UEFI Option __1__

* pacman --noconfirm -s grub
* grub-install /dev/sd__x__
* grub-mkconfig  /boot/grub/gurb.cfg
* genfstab -U -p /mnt /mnt/etc/fstab
* reboot
