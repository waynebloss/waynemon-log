# Chrome Keyring Prompt

Every time I opened Chrome, it would prompt me to unlock the Gnome keyring.
It was annoying.

## Analysis

The answer is pretty much laid out [here](https://classicforum.manjaro.org/index.php?PHPSESSID=tr6l9rmv6s0a1u4gln4mf5ue65&topic=32700.msg267279#msg267279).

## Solution

- Modify `~/.xinitrc` to
[start the Gnome Keyring Daemon at login](https://wiki.archlinux.org/index.php/GNOME/Keyring#xinitrc_method)
```
eval $(/usr/bin/gnome-keyring-daemon --start --components=pkcs11,secrets,ssh)
export SSH_AUTH_SOCK

get_session() { ...
```
- Modify `/etc/pam.d/login` to
[unlock the Keyring at login](https://wiki.archlinux.org/index.php/GNOME/Keyring#PAM_method)
```
auth       ...
auth       optional     pam_gnome_keyring.so
session    ...
session    optional     pam_gnome_keyring.so auto_start
```
- Reboot.
