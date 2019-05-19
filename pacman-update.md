[Back to Table of Contents](README.md)
***
#### Update pacman databases
* pacman -Syu

Update all packages.

#### Shorten mirrorlist 
* pacman -S reflector
* reflector -c "United States" -f 12 -l 10 -n 12 --save /etc/pacman.d/mirrorlist

The mirror list is very long.  I shortened the list to the United States.  My
collegues from France should replace "United States" with "France".  I do
recommend 
```bash
cat /etc/pacman.d/mirrorlist
``` 
to learn what reflector did to your system.
