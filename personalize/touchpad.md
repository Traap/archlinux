[Back to Personalizing Arch Linux](../03-personalize-arch-linux.md)
***


#### Touchpad
* vim 30-touch.conf
* Enter the following text.
  ```
  Section "InputClass"
    Identifier "bcm5974"
    Driver "libinput"
    MatchIsTouchpad "on"
    Option "Tapping" "on"
    Option "TappingButtonMap" "lmr"
    Option "Scrolling" "on"
  EndSection
  ```
* save and quit
* `sudo mv -v 30-touch.conf /etc/X11/xorg.conf.d/.`

---
__Notes:__ 
* I used [LARBS](../personalize/larbs.md) to initially setup
  [i3](https://wiki.archlinux.org/index.php/I3) -- a dynamically tiling window
  manager.  This process installed X11 components so my Touchpad only works
  after _StartX_ is run.
* Scrolling and clicking are fuctioning.
* - [ ] Clicking and draging does not work. 
