# Touchpad Gestures

Only the basic 1 and 2-finger gestures worked.
I wanted to see if I could get 3 and 4-finger gestures working.

The simple solution is to install
[libinput-gestures](https://github.com/bulletmark/libinput-gestures)
and configure it.

## Analysis

### Do I need a special driver to get this to work?

- Inspect hardware.
```shell
sudo su
libinput list-devices
grep -e "libinput" /var/log/Xorg.0.log
lsmod | grep -i hid
lsmod | grep -i elan
mhwd -lh -d | less
```
- According to `/var/log/Xorg.0.log` I have a `ELAN0501:00 04F3:3019 Touchpad`
and it is `Applying InputClass "libinput touchpad catchall"`.
- Finding online: It's an Elantech touchpad and the driver is called
`i2c`.
- `lsmod` shows an `i2c_hid` driver, so I guess the right driver is installed...

### Is libinput receiving 3 and 4-finger events already?

- Try some commands to see what you can see:
```shell
sudo libinput debug-gui
sudo libinput debug-gui --enable-tapping --set-click-method=clickfinger
sudo libinput debug-events
sudo libinput debug-events --enable-tapping --set-click-method=clickfinger
```
- Yes.

## Solution

Install and configure
[libinput-gestures](https://github.com/bulletmark/libinput-gestures)

- Run `sudo gpasswd -a $USER input` and then logout and back in.
- Install `libinput-gestures` via Pacman or Pamac.
- Run `libinput-gestures-setup autostart`
- Run `libinput-gestures-setup start`

## Configuration

- Run `cp /etc/libinput-gestures.conf ~/.config/`
- Edit `~/.config/libinput-gestures.conf` using the documentation in that file.
- Run `libinput-gestures-setup restart`

### Files

- [home/.config/libinput-gestures.conf](../../files/home/.config/libinput-gestures.conf)
