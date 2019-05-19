[Back to Table of Contents](../README.md)
***

#### Post packstrap UEFI Option __2__
* arch-chroot /mnt
* pacman -S --noconfirm vim
* bootctl install
* vim /boot/loader/entries/arch.conf
  * Make the edits below
    ```
    title ArchLinux
    linux /vimlinuz-linux
    initrd /initramfs-linux.img
    options root=PARTUUID=YOUR-UUID-GOES-HERE rw
    ```
  * :r !blkid to read the YOUR-UUID.  => It is the Linux file system
  * :wq => write quit

---
__Note:__ 
* A lot of videos instruct you to use **nano**.  I only use **Vim**.
* *bootctrl* solved all my problems.
