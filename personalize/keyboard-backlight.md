[Back to Personalizing Arch Linux](../03-personalize-arch-linux.md)
***

#### Keyboard backlight
* [Arch Linux
  Backlight](https://wiki.archlinux.org/index.php/Backlight#Backlight_utilities)
  ArchLinux wiki article about Backlight.

* [macbook-lighter aur](https://aur.archlinux.org/packages/macbook-lighter/)
  ArchLinux user repository package.

* [macbook-lighter](https://github.com/harttle/macbook-lighter) GitHub
  repository with source code and examples.

#### Installation and Setup
```bash
yay --noconfirm -S macbook-lighter
```

##### Keyboard
```bash
macbook-lighter-kbd --inc 60
```

##### Screen
```bash
macbook-lighter-screen --inc 60
```

##### Ambient lighting
```bash
systemctl start macbook-lighter
macbook-lighter-ambient
```

---
__Note:__
*  AUR macbook-lighter just works.
