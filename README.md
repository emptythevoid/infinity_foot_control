# infinity_foot_control
Files to make the Infinity Foot Control function as mouse buttons

The Infinity Foot Control (idVendor 05f3, idProduct 00ff) is a three-button foot pedal designed for transcription control.  When used on a Linux system, xinput does not recognize it as an input device, and it has an unusual button mapping.

These two files work together to make the device appear in xinput and make it default to left/middle/right clicking, although they can be modified to whatever you need (use evtest on a keyboard or mouse to get the keycodes you need to map to the pedals).

To emulate a mouse, add this to the end of the .rules line: ENV{ID_INPUT_MOUSE}="1"

To emulate a keyboard, add this to the end of the .rules line instead: ENV{ID_INPUT_KEYBOARD}="1"

Key codes do NOT have a leading zero. So if evtest or xev says the keycode is 42, just put 42. Do NOT put in 042, as this will have unexpected results.

The files need to go in these directories:

/etc/udev/rules.d/10-vec-usb-footpedal.rules

/etc/udev/hwdb.d/60-usb-footpedal.hwdb

After the files are created, run

sudo systemd-hwdb update

and then unplug/replug the device in. 


I've included specific layouts for various games.
