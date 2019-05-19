
### Make a bootable USB
1. Google it and follow instructions.

### Boot from USB
1. Insert USB with Arch Linux ISO
1. Connect physical Ethernet cable
1. Press power button
1. Hold Options key when gray screen appears
1. Select Arch Linux ISO

### Block size and Disk Sizes 
1. lsblk
1. cfdisk

### Check internet connection
1. ping -3 google.com
1. ip link

### Update pacman databases
1. pacman -Syy
2. pacman -S reflector

### Shorten mirrorlist 
3. reflector -c "United States" -f 12 -l 10 -n 12 --save /etc/pacman.d/mirrorlist

#### BIOS Boot Mode 
[Arch Linux Bios](https://www.youtube.com/watch?v=GKdPSGb9f5s)
1. cfdisk /dev/sdX
1. mkfs.ext4 /dev/sdX1

#### UEIF Boot Mode
Note: Use either Option 1 or 2.
1. Option 1 worked on non-Apple hardware.
1. Option 2 worked on Apple hardware.

##### UEFI Option 1 
######  Partitions 
[Arch Linux UEFI 2](https://www.youtube.com/watch?v=dOXYZ8hkdmc)
1. cfdisk /dev/sdX
1. /dev/sdX1 efi 60MB
1. /dev/sdX2 swap 8GB
1. /dev/sdX3 / 500GB
1. /dev/sdX4 /home remaining
1. mkfs.fat -F32 /dev/sdX1
1. mkfs.ext4 /dev/sdX3
1. mkfs.ext4 /dev/sdX4
1. mkswap /dev/sdX2

###### Make mount points
1. mount /dev/sdX3 /mnt
1. mkdir /mnt/boot
1. mount /dev/sdX1 /mnt/boot
1. mount /dev/sdX4 /home
1. swapon /dev/sdX2

##### UEFI Option 2
###### Partitions 
[Arch Linux UEFI 2](https://www.youtube.com/watch?v=DfC5hgdtbWY)
*Note:*  Don't use Grub
1. pacman -Sy vim font
1. setfont
1. ls /sys/firmware/efi  => any output means you have UEFI.
1. cat /proc/partitions

1. gdisk /sdX
   1. First partition
      1. o = clear
      1. y => proceed
      1. Command (? or help) n => new
      1. first sector : enter
      1. second sector : +500mb
      1. Hex code or GUID: EF00

   1. Second partition
      1. Command (? or help) n => new
      1. first sector : enter
      1. second sector: enter
      1. Hex code or GUID: enter

2. Command (? or help): write => write

###### File systmes
1. gdisk -l /dev/sdX
1. mkfs.vfat /dev/sdX1
1. mkfs.ext4 /dev/sdX2

###### Make mount points
1. mount /dev/sdX2 /mnt
1. mkdir /mnt/boot
1. mount /dev/sdX1 /mnt/boot

### Install Packages
1. packstrap /mnt base base-devel

### Post packstrap
#### BIOS or UEFI Option 1
1. pacman -S grub
1. grub-install /dev/sdX
1. grub-mkconfig -o /boot/grub/grub.cfg
1. genfstab -U -p /mnt > /mnt/etc/fstab

#### Ueif Option 2
1. arch-chroot /mnt
1. pacman -S --noconfirm vim
1. bootctl install
1. vim /boot/loader/entries/arch.conf
```
title ArchLinux
linux /vimlinuz-linux
initrd /initramfs-linux.img
options root=PARTUUID=YOUR-UUID-GOES-HERE rw
```
1. :r !blkid to read the YOUR-UUID.  => It is the Linux file system
1. :wq => write quit
1. reboot

### Set local time and password
1. arch-chroot /mnt
1. vi /etc/locale.gen
1. locale-gen
1. ln -sf /usr/share/zoneinfo/America/Chicago /etc/localtime
1. hwclock --systohc --utc
1. echo LANG=en_US.UTF-8 > /etc/locale.conf 

### Name your computer
1. echo Fubar > /etc/hostname
2. vi /etc/hosts
```
   127.0.0.1 localhost.localdomain localhost
   ::1       localhost.localdomain localhost
   127.0.1.1 localhost.localdomain Fubar
```

### Enable DHCP 
1. systemctl enable dhcpcd

### Enable Network Manager 
1. pacman -S --noconfirm networkmanager
1. systemctl enable NetworkManager 

### Set root password
1. passwd

### Reboot
1. exit
1. umount -R /mnt
1. reboot

### Add user 
1. useradd -m -g users -G wheel -s /bin/bash traap
1. passwd traap
