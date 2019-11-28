[Back to Personalizing Arch Linux](../03-personalize-arch-linux.md)
***

#### XDG Base Directory Specification 
I read [XDG Specificaiton](https://specifications.freedesktop.orgi/basedir-spec/basedir-spec-latest.html)
first, and then customized my environment.  I have listed the defaults for starters.

##### XGD exports
The following exports are added to $HOME/my_exports.
```bash
export $XDG_DATA_HOME=$HOME/.local/share
export $XDG_CONFIG_HOME=$HOME/.config
export $XDG_DATA_DIRS=/usr/local/share/:/usr/share/
export $XDG_CONFIG_DIRS=/etc/xdg
export $XDG_CACHE_HOME=$HOME/.cache
export $XDG_RUNTIME_DIR=path/to/xdg_runtime_dir
```

---
__Note:__
* My thought is to apply version control to config and data dirs.
