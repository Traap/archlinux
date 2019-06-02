[Back to Installing Arch Linux from Bootable USB](../01-install-arch-linux.md)
***

#### Pacstrap Arch Linux
* `pacstrap /mnt base base-devel` 

#### Update System Clock
* `timedatectl set-ntp true`

#### FSTAB
* `genfstab -U /mnt >> /mnt/etc/fstab`

---
__Note:__ 
* Arch Linux is running from your USB drive.  You are now using packstrap
  to bootstrap Arch Linux packages onto your newly create file system.  
