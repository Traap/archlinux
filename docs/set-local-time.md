[Back to Your New Arch Linux System](../02-your-new-arch-linux-system.md)
***

#### Set Local Time
* `arch-chroot /mnt`
* `vi /etc/locale.gen`
* `locale-gen`
* `ln -sf /usr/share/zoneinfo/America/Chicago /etc/localtime`
* `hwclock --systohc --utc`
* `echo LANG=en_US.UTF-8 > /etc/locale.conf`

#### Sync Time with Network Time
* `sudo pacman --noconfirm -S ntp`
* `sudo systemctl enable ntpd`

---
__Note:__ 
* Besides `arch-chroot /mnt`, the steps abobe can always be used to change your
  local time zone.
