### Make a bootable USB
1. Google it and follow instructions.

### Boot from USB
1. Insert USB with Arch Linux ISO
1. Connect physical ethernet cable
1. Press power buton
1. Hold Options key when gray screen appears
1. Select Arch Linux ISO

### Block size and Cfdisk 
1. lsblk
1. cfdisk

### Check internet connection
1. ping -3 google.com

### Make file systems
1. /dev/sda1 efi 60MB
1. /dev/sda2 swap 8GB
1. /dev/sda3 / 500GB
1. /dev/sda4 /home remaining
1. mkfs.fat -F32 /dev/sda1
1. mkfs.ext4 /dev/sda3
1. mkfs.ext4 /dev/sda4
1. mkswap /dev/sda2


### Make mount points
1. mount /dev/sda3 /mnt
1. mkdir /mnt/boot
1. mount /dev/sda1 /mnt/boot
1. mount /dev/sda4 /home
1. swapon /dev/sda2

### Install Packages
1. vi /etc/pacman.d/mirrorlist
1. packstrap /mnt base base-devel
1. genfstab -U /mnt > mnt/etc/fstab

### Set local time and password
1. arch-chroot /mnt
1. passwd
1. ln -sf /usr/share/zoneinfo/America/Chicago /etc/localtime
1. hwclock --systohc
1. locale-gen
1. /etc/locale.conf 
   LANG=en_US.UTF-8
1. /etc/hostname
   Gucci 
2. /etc/hosts
   127.0.0.1 localhost
   ::1       localhost
   127.0.1.1 Gucci.localdomain Gucci
