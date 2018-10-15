# Super Key Shortcuts

Creating global application shortcuts using the Super key resulted in the XFCE
Whisker menu being activated whenever the shortcut was used.

## Analysis

- [Whisker menu activates on key PRESS instead of RELEASE. You can use something
like xcape or ksuperkey to re-bind Super to something else and then use Super
for other global shortcuts.](https://unix.stackexchange.com/questions/237139/how-to-bind-the-super-key-to-whiskermenu-without-breaking-superother-combinatio/447801#447801)
- Looking at the [xcape repo](https://github.com/alols/xcape) and elsewhere, I
couldn't find any Manjaro/XFCE guides/instructions/recommendations, etc.
- Then I found a 
[recommendation](https://forum.xfce.org/viewtopic.php?pid=49024#p49024) for
[xfce-superkey](https://github.com/JixunMoe/xfce-superkey), so I decided to go
with that.
- However, `xfce-superkey` was not found in pacman (via pamac), not even in AUR.
- So, we must install from github.
- Requirements show `build-essential` package, but there is none for Arch.
- [Found a recommendation](https://forum.manjaro.org/t/manjaro-packages-equivalent-in-ubuntu/49118/2)
to search for each package, omitting the `-devel` suffix when searching for
package names that have it.
- I think most of the packages where already installed.

## Solution

Install and configure
[xfce-superkey](https://github.com/JixunMoe/xfce-superkey).

_"xfce-superkey allows you to open the whisker menu launcher in XFCE using the
Super key (also known as "Meta" or "the Windows key"). If you hold down the
Super key it will still act as a modifier key, allowing you to use [Super] for
other keyboard shortcuts."_

- Use pacman/pamac to install dependencies. Omit the `-devel` from any package
names that have it.
- Build the software:
```shell
git clone https://github.com/JixunMoe/xfce-superkey.git
cd xfce-superkey
make
```
- Install it:
```
sudo make install
```
- Run it:
```
xfce-superkey
```

## Configuration

- Open `Session and Startup` system settings.
- Choose the `Application Autostart` tab.
- Add a command: `xfce-superkey`
