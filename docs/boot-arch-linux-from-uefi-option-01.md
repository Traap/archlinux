[Back to Table of Contents](../README.md)
***

#### Boot Arch Linux from UEFI Option 1
Watch [Arch Linux UEFI 2](https://www.youtube.com/watch?v=dOXYZ8hkdmc).  Below
are commands I used when attempting this options.

####  Partitions 
* cfdisk /dev/sdX
  * /dev/sdX1 efi 60MB
  * /dev/sdX2 swap 8GB
  * /dev/sdX3 / 500GB
  * /dev/sdX4 /home remaining
* make file systems
  * mkfs.fat -F32 /dev/sdX1
  * mkfs.ext4 /dev/sdX3
  * mkfs.ext4 /dev/sdX4
  * mkswap /dev/sdX2

#### Make mount points
* mount /dev/sdX3 /mnt
* mkdir /mnt/boot
* mount /dev/sdX1 /mnt/boot
* mount /dev/sdX4 /home
* swapon /dev/sdX2
