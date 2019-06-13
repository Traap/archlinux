[Back to Personalizing Arch Linux](../03-personalize-arch-linux.md)
***

#### Update community packages
* `yay -Syu`

#### Install rbenv and ruby-build
* `yay -Sy rbenv`
* `yay -Sy ruby-build`

#### Install ruby with rbenv
* `rbenv install 2.6.2`

#### Mody your path
* Use rbenv init for the latest instructions.
```bash
rbenv init
# Load rbenv automatically by appending
# the following to ~/.bash_profile
eval "$(rbenv init -)"
```

---
__Note:__ 
* I chose to run *yay* commands 1 at a time.
* `rbenv install -l | less` to view everything rbenv can install.
