# Input devices

## Touchpad

The internal touchpad can work both in i2c and ps2 mode. In i2c mode it seems a little buggy (sometimes it stops working).

To disable the i2c mode it is enough to blacklist the i2c_hid module.

This has the additional advantage of enabling the feature that the keyboard backlight turns on when the touchpad is being used.

## Installation

Copy all the files in the `modprobe.d` directory in `/etc/modprobe.d`.
