[Back to Table of Contents](../README.md)
***
#### Update pacman databases
* `pacman --noconfirm -Syu`

#### Shorten mirrorlist
* `pacman --noconfirm -S reflector`
* `reflector -c "United States" -f 12 -l 10 -n 12 --save /etc/pacman.d/mirrorlist`

---
__Notes:__
* I use `--noconfim` to avoid answering questions.  I don't care if things
  fail.  I will start over.

* The mirror list is very long.  I shortened the list to the United States.  My
  collegues from France should replace "United States" with "France".  I do
  recommend `cat /etc/pacman.d/mirrorlist` to learn what reflector did to your
  system.
