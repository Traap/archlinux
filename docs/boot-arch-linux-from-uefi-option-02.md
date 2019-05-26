[Back to Table of Contents](../README.md)
***

#### Boot Arch Linux from UEFI Option 2
Watch [Arch Linux UEFI 2](https://www.youtube.com/watch?v=DfC5hgdtbWY).  Below
are commands I used when I _successfully_ booted into Arch Linux for the first
time on my hardware.

#### Make your fonts bigger and update Vim.
* `pacman --noconfirm -Sy vim terminus-font`
* `setfont terminux-font`

#### Confirm your system uses UEFI.
* `ls /sys/firmware/efi`  => any output means you have UEFI.
* `dmesg | grep sd` to display kernel ring buffer information about sd devices.
* `lsblk` to list block devices.
* `cat /proc/partitions` to see your partitions

#### Partitions 
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

#### File systems 
* gdisk -l /dev/sdX
* mkfs.vfat /dev/sdX1
* mkfs.ext4 /dev/sdX2

#### Make mount points
* mount /dev/sdX2 /mnt
* mkdir /mnt/boot
* mount /dev/sdX1 /mnt/boot

---
__Notes:__
* Don't use GRUB when you confirm you have a UEFI sytem.
* pacman was used to install vim and font to make text on
  YouTube video easer to read.
* `cfdisk` can replace `gdisk`. As I recall, `cdisk` did not have capabilities
  it now when this video was done.`
