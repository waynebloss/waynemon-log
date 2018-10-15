# Touchpad Gestures for Window Snapping

I wanted to use 3 or 4-finger swipe right/left to snap window to 50% screen
width, like Windows.

## Analysis

- The XFCE Window Manager keyboard settings already allow you to do this with
the keyboard and using my findings from
[Issue 02 - Super Key Shortcuts](02_Super_Key_Shortcuts.md), I had assigned
`Super+Right/Left` to do that.
- So, I added the following to `~/.config/libinput-gestures.conf`
```
# Snap Left
# gesture swipe left 4 xdotool keyup Super+Left

# Snap Right
# gesture swipe right 4 xdotool keyup Super+Right
```
- This worked, but for some reason it causes the Whisker menu to activate, a
problem that we solved in
[Issue 01 - Touchpad Gestures](01_Touchpad-Gestures.md).
- The way `libinput-gestures` sends keys must be bypassing `xfce-superkey`.
Maybe there's a way to involve `xfce-superkey` here?
- Another solution that I found
[uses wmctrl](https://unix.stackexchange.com/questions/53150/how-do-i-resize-the-active-window-to-50-with-wmctrl)
to do it without involving the window manager.

## Solution

None applied yet. Maybe just use the `wmctrl` solution mentioned above.
