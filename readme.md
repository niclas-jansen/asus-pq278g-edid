# EDID files for Asus PQ278g
linux fails to set correct display mode when using Asus PQ278g with an AMD graphics card
adding custom edid files and loading them via kernel parameters fixes this.

## Modelines
EDID files have been created with https://github.com/akatrevorjay/edid-generator
modelines used:

60hz = `Modeline 241.5 2560 2608 2640 2720 1440 1443 1448 1481 -Hsync +Vsync`
120hz = `Modeline 497.75 2560 2608 2640 2720 1440 1443 1481 1525 -Hsync +Vsync`

## Set Kernel Parameters
https://wiki.archlinux.org/title/kernel_mode_setting
https://wiki.archlinux.org/title/kernel_parameters

copy edid binary to `/usr/lib/firmware/edid`


#### Systemd
`/boot/loader/entries/`

### changes
```conf
drm.edid_firmware=DP-1:edid/2560x1440@60_custom.bin drm_kms_helper.edid_firmware=DP-1:edid/2560x1440@60_custom.bin video=DP-1:2560x1440@60
```
