# Wayneman : Acer E5-575G

System log for my Acer E5-575G laptop with **Manjaro** Linux, XFCE Edition

## Contents

A detailed system-specific installation log is shown in this file.

The [`files/` directory](files/README.md) contains any system file
modifications done by me after installation (to solve issues).

The [`issues/` directory](issues/README.md) contains details about various
issues that I've solved.

## Hardware

| | |
|-|-|
|Manufacturer|Acer|
|Brand|Aspire|
|Model Number|E5-575G|
|CPU|Intel Skylake i5|
|RAM|8GB|
|HDD|256GB SSD|

## Pre-install ~ _October 12th, 2018 EST_

- Started with **Windows 10 Pro (1803) 64-bit** already installed on
`/dev/sda4`, a _~237GB_ partition.
- Used Windows to shrink the partition to _~137GB_.
- _(The BIOS should have also been updated at this point, but the author forgot
until after Manjaro had been installed!)_
- Downloaded [an official ISO](https://osdn.net/dl/manjaro/manjaro-xfce-17.1.12-stable-x86_64.iso)
via [manjaro.org/get-manjaro](https://manjaro.org/get-manjaro/).
- Created a bootable 8GB Flash Drive using ImageWriter.

### Pre-install BIOS Changes
- Following the [UEFI modification guide for Acer Aspire E5-575 on 
wiki.archlinux.org](https://wiki.archlinux.org/index.php/Acer_Aspire_E5-575).
- Plug in the bootable USB flash drive.
- Reboot.
- Enter the BIOS by hitting `F2` during boot/POST.
- A system supervisor password must be set to change any UEFI settings here.
_The password can be removed later (after a subsequent reboot) when all changes
have been safely committed._
- Use the UEFI Secure File settings to add a trusted EFI boot file from the 
flash drive. _(The BIOS will open a rudimentary file browser to let you find
an EFI file on the flash drive. The choice of which file should be obvious, 
I believe the file names all end in .efi.)_ Later this same step will have
to be done for a new EFI file on the SSD, for the new OS.
- Enable the BIOS setting that lets you choose the boot volume by hitting F12.
- Save changes and exit.

## Install Manjaro XFCE 17.1.12

- Hit F12 during POST to get to the BIOS menu that lets you choose the bootable
Flash USB drive as the startup drive.
- Boot into the GUI installer.
- Choose non-free drivers.
- Start installer after booting into the live ISO.

### Partitioning

- Choose manual partitioning.
- Starting with _~100GB_ free on the main SSD `/dev/sda`
- Created `ext4` partition `/dev/sda6` with 84GB mounted at `/`.
- Created `linux-swap` parition `/dev/sda7` with 16GB with `swap` flag.
- Set the `boot` and `esp` flags on the pre-existing `fat32` EFI system
partition (Installer would not continue without this.)

### Completing Installation

- During the final reboot after installation completed, the system froze
at the very last command. I forget what it said, but it might have had
something to do with a watchdog timer.
- So, the system had to be hard-reset by holding down the power button.

## Post-install BIOS Changes

- Enter the BIOS by hitting `F2` during boot/POST.
- Enter the system supervisor password.
- Use the UEFI Secure File settings to add a trusted EFI boot file from the 
SSD drive. Call it Manjaro.
- _Optionally_, before exiting at this time I believe you can re-order the 
boot order so that Manaro is first on the list, above the Windows Boot Manager.
Otherwise, you have to hit `F12` to get into Manjaro at every boot. If the BIOS
doesn't let you do it right now, it definitely will after a reboot.
- Save changes and exit.

## First start

- I forget exactly what I did here. Probably just installed all the updates and
started looking for issues to solve...
