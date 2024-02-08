# infinity_foot_control
Files to make the Infinity Foot Control function as mouse buttons

The Infinity Foot Control (idVendor 05f3, idProduct 00ff) is a three-button foot pedal designed for transcription control.  When used on a Linux system, xinput does not recognize it as an input device, and it has an unusual button mapping.

These two files work together to make the device appear in xinput and make it default to left/middle/right clicking, although they can be modified to whatever you need (use evtest on a keyboard or mouse to get the keycodes you need to map to the pedals).

The files need to go in these directories:

/etc/udev/rules.d/10-vec-usb-footpedal.rules

/etc/udev/hwdb.d/60-usb-footpedal.hwdb

After the files are created, run

sudo systemd-hwdb update

and then unplug/replug the device in. 


I've included specific hwdb files for use with different games.
