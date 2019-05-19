[Back to Table of Contents](README.md)
***

#### Update pacman databases
1. pacman -Syy

#### Shorten mirrorlist 
1. pacman -S reflector
1. reflector -c "United States" -f 12 -l 10 -n 12 --save /etc/pacman.d/mirrorlist
