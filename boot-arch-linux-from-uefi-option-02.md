[Back to Table of Contents](README.md)
***

#### Boot Arch Linux from UEFI Option 2

##### pacman steps 
[Arch Linux UEFI 2](https://www.youtube.com/watch?v=DfC5hgdtbWY)
__Note:__  Don't use GRUB and confirm you have UEFI.

* pacman -Sy vim font
* setfont
* ls /sys/firmware/efi  => any output means you have UEFI.
* cat /proc/partitions

##### Partitions 
__Note:__ `cfdisk` can replace `gdisk`. As I recall, `cdisk` did not have
capabilities it now when this video was done.

* gdisk /sdX
  * First partition
    * o = clear
    * y => proceed
    * Command (? or help) n => new
    * first sector : enter
    * second sector : +500mb
    * Hex code or GUID: EF00

  * Second partition
    * Command (? or help) n => new
    * first sector : enter
    * second sector: enter
    * Hex code or GUID: enter

  * Command (? or help): write => write

##### File systems 
* gdisk -l /dev/sdX
* mkfs.vfat /dev/sdX1
* mkfs.ext4 /dev/sdX2

##### Make mount points
* mount /dev/sdX2 /mnt
* mkdir /mnt/boot
* mount /dev/sdX1 /mnt/boot
