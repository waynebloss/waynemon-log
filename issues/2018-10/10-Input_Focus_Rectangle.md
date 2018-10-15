# Input Focus Rectangle

I wanted an obvious focus rectangle, for when I use the tab button to change
focus from one button/input/control to the next in a given application.

None of the themes that came with Manjaro XFCE satisfied this requirement.

## Analysis

- Should I try to find a custom theme or modify one?
- Whose job is it even to draw this rectangle?
- What do I search for?
- Let's ask on IRC.
- Turns out it's the job of the GTK theme to do this.
- Can't find a recommended theme anywhere that does this.
- Let's try to modify my favorite built-in theme, Adwaita-dark.

### IRC freenode##linux

  `them>me:` you should add an equivalent stanza to `~/.gtkrc-2.0` instead or
  the next time you update the theme's package it will get overwritten

  `them>me`: you would have had to put the copy in
  `~/.local/share/themes/Adwaita-dark/main.rc`

- Putting my modifications of `mainrc` from the theme into
`~/.local/share/themes/Adwaita-dark/main.rc` didn't work.
- I didn't try modifying `~/.gtkrc-2.0` because I don't know how to override
the `image { function = FOCUS, ... }` section in the temp solution below.

## References

https://developer.gnome.org/gtk2/stable/GtkWidget.html#GtkWidget--s-focus-line-pattern

## Temp solution

Changes to `/usr/share/themes/Adwaita-dark/gtk-2.0/main.rc`
These changes may be overwritten by an OS update according to IRC user.

LINE 18: _Change focus-line-pattern to `"\001\001"`._
```
  # GtkWidget::focus-line-pattern = "\2\1"
  GtkWidget::focus-line-pattern = "\001\001"
```

LINE 678: _Comment out image being used for focus._
```
    #########
    # Focus #
    #########

    #image {
    #  function = FOCUS
    #  file     = "assets/focus.png"
    #  border   = {1, 1, 1, 1}
    #  stretch  = TRUE
    #}
```
