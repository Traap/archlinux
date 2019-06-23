[Back to Installing Arch Linux from Bootable USB](../01-install-arch-linux.md)
***

#### Boot Arch Linux from UEFI Option 3
Watch [Arch Linus Virutalbox UEFI](https://www.youtube.com/watch?v=SVFgHPXBVug).  Below
are commands I used when I _successfully_ booted into Arch Linux for the first
time on my VirtualBox 

#### Install grup and efibootmgr.
* `pacman --noconfirm -S grub efibootmgr`

#### Grub install is Virtualbox Specific.
* `grub-install --target=x86_64-efi --efi-directory=boot --bootloader-id=arch_grub'
* `grub-mkconfig -o /boot/grub/grub.cfg`
* `mkinitcpio -p linux`


---
__Notes:__
* [Ubuntu pastebin](https://paste.ubuntu.com/9017251/)
