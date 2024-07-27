### Exercise 11-2
Asks for Exercise 7-1 to be modified to stop if the button is ever pressed.
#### Work
Simply add within the `BUTTON_DEF` a `STOP_PAYLOAD` command.  This will stop the payload's execution without remunerating as a storage device in Arming Mode
```DuckyScript
REM Title: Exercise 11-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Forever type the lyrics to the Song That Never Ends Song until button press, then stop

REM Set attackmode as an HID device;
ATTACKMODE HID MAN_HirschP2 PROD_DUCKY SERIAL_123456789012

BUTTON_DEF
	STOP_PAYLOAD
END_BUTTON

REM Obligatory enumeration delay:
DELAY 2000

REM Use Run to open Notepad
GUI r
DELAY 100
STRING notepad
ENTER
DELAY 100

WHILE TRUE
	STRINGLN This is the song that doesn't end.
	STRINGLN Yes, it goes on and on, my friend.
	STRINGLN Some people started singing it, not knowing what it was.
	STRINGLN And, they'll continue singing it forever, just because...
END_WHILE
```
This works as intended, stops typing on button press but can be seen via  [Nirsoft USBDeview](https://www.nirsoft.net/utils/usb_devices_view.html) to still be connected as the same HID device.