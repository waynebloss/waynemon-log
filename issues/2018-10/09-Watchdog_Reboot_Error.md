# Watchdog Reboot Error

During restarts I would see an error message, something like this:
```
Error: watchdog: watchdog0: watchdog did not stop!
```

## Analysis

- A [watchdog timer](https://en.wikipedia.org/wiki/Watchdog_timer) is a hardware
timer that watches a resource (such as a CPU) to make sure that it's responsive.
If the resource is frozen, the watchdog can reboot. An OS software component is
responsible for "kicking the watchdog" every so often, to let it know things
are alive.
- They're important for servers and embedded systems, for automatic recovery.
- However, they're not very important for personal desktop/laptop systems.
- In this case, according to one report, the message was mistakenly categorized
as an error and that the watchdog shutdown is part of normal business.
- There were also quite a few reports of users seeing high resource usage by
the watchdog software components.
- So, let's find a way to disable it or at least get rid of the error.

## Solutions

I honestly can't remember the exact solution I used! Most likely setting the
time correctly using `timeset` had fixed it by getting rid of the error
(see last point below).

- Bookmarked: [same problem with list of things they tried.](https://serverfault.com/questions/911697/watchdog-watchdog0-watchdog-did-not-stop)
- Bookmarked: [4 Ways to disable NMI Watchdog](https://www.pcsuggest.com/disable-nmi-watchdog-linux/#4_Permanently_disable_NMI_watchdog_through_boot_parameter).
However, the solution it points to was undone by me at some point since my
current `/etc/default/grub` file does not contain `nmi_watchdog=0` and I seem
to remember that not working anyway.
- Maybe setting the time correctly using the `timeset` package did the trick?
I can see that in my history immediately before the last time I updated
`/etc/default/grub`...
- Looking at my historey, I also ran `sudo wdctrl`...
