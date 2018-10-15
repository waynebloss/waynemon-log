# White Cursor (like Windows)

I didn't like any of the cursors that came with XFCE (as seen in the Mouse
settings). The black cursor looked the sharpest, but I'd rather have a white
cursor like Windows.

## Analysis

### How to add custom cursors?

- [XFCE Themes docs](https://wiki.xfce.org/howto/install_new_themes#cursors_44_and_46)
say to put them in `~/.icons/<theme_name>/cursors/`.
- [Top of the same page](https://wiki.xfce.org/howto/install_new_themes)
lists where to get them.
- Found a set of 
[white cursors from Windows 8.1](https://www.xfce-look.org/p/1084938/)
on [https://www.xfce-look.org](https://www.xfce-look.org).

## Solution

- Download the
[Win-8.1-NS-S-(KDE).R2.tar.bz2 file](https://www.xfce-look.org/p/1084938/startdownload?file_id=1515308043&file_name=Win-8.1-NS-S-(KDE).R2.tar.bz2&file_type=application/x-bzip2&file_size=54718&url=https%3A%2F%2Fdl.opendesktop.org%2Fapi%2Ffiles%2Fdownload%2Fid%2F1515308043%2Fs%2F5474cb14cc0e67bb6d7e0036b42daa70%2Ft%2F1539572000%2Fu%2F%2FWin-8.1-NS-S-(KDE).R2.tar.bz2)
from xfce-look.org.
- Extract the folder and copy all files from 
`Win-8.1-NS-S-(KDE)/Win-8.1-NS/cursors/` into `~/.icons/win81/cursors`.
- Open the system `Mouse and Touchpad` settings.
- Choose the `Theme` tab.
- Select the `win81` theme.
