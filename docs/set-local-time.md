[Back to Table of Contents](../README.md)
***

#### Set Local Time
* arch-chroot /mnt
* vi /etc/locale.gen
* locale-gen
* ln -sf /usr/share/zoneinfo/America/Chicago/etc/localtime
* hwclock --systohc --utc
* echo LANG=en_US.UTF-8 > /etc/locale.conf 

---
__Note:__ 
* Besides `arch-chroot /mnt`, the steps abobe can always be used to change your
  local time zone.
