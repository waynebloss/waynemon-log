# Remote Desktop to Windows

I want to remote desktop to windows.

## Analysis

- Found many mentions of `rdesktop` (because it's old).
- It's official Arch package.
- Tried `rdesktop` and got an error 
[CredSSP required by server](https://blog.syskit.com/credssp-required-by-server-solutions)
where I then found mention of `FreeRDP`.
- It's also an official Arch package.
- Tried `FreeRDP`. It's great.

## Solution

Use FreeRDP.

- You can make a launcher to go right to your machine with the command:
```
xfreerdp -f -v <machine-name>
```
- There are lots of other options shown in
[the FreeRDP User Manual](https://github.com/awakecoding/FreeRDP-Manuals/blob/master/User/FreeRDP-User-Manual.pdf?raw=true)
found via the
[FreeRDP Manuals Page](https://github.com/awakecoding/FreeRDP-Manuals/blob/master/Configuration/FreeRDP-Configuration-Manual.markdown).
