[Back to Personalizing Arch Linux](../03-personalize-arch-linux.md)
***

#### WiFi 
Steps taken to configure my WiFi module.

##### Step 1
```bash
mkdir -p ~/Downloads
cd ~/Downloads
wget http://bues.ch/b43/fwcutter/b43-fwcutter-018.tar.bz2
http://bues.ch/b43/fwcutter/b43-fwcutter-018.tar.bz2.asc
wget http://bues.ch/b43/fwcutter/b43-fwcutter-018.tar.bz2.asc
gpg --verify b43-fwcutter-018.tar.bz2.asc 
tar xjf b43-fwcutter-018.tar.bz2
cd b43-fwcutter-018
make
sudo make install
```
##### Step 2
```bash
cd ~/Downloads
export FIRMWARE_INSTALL_DIR="/lib/firmware"
wget http://www.lwfinger.com/b43-firmware/broadcom-wl-5.100.138.tar.bz2
tar xjf broadcom-wl-5.100.138.tar.bz2
sudo b43-fwcutter -w "$FIRMWARE_INSTALL_DIR" broadcom-wl-5.100.138/linux/wl_apsta.o
```

---
__Note:__
*
