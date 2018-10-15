# Disable Bluetooth Autostart

Bluetooth was turned back on every time I logged in.

## Solution

- Run
```
gsettings set org.blueman.plugins.powermanager auto-power-on false
```

[found on forum.manjaro.org](https://forum.manjaro.org/t/solved-bluetooth-turned-off-on-startup/40465/32)
