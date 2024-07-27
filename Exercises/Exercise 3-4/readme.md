### Exercise 3-4
Script should should bypass keyboard setup on a Mac computer.
#### Work
First Draft Code:
```DuckyScript
REM Title: Exercise 3-4 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Enumerates 5 times as Never, Gonna, Give, You, & Up

ATTACKMODE HID STORAGE MAN_Rick PROD_Never SERIAL_111111111111
DELAY 2000

ATTACKMODE HID STORAGE MAN_Rick PROD_Gonna SERIAL_111111111111
DELAY 2000

ATTACKMODE HID STORAGE MAN_Rick PROD_Give SERIAL_111111111111
DELAY 2000

ATTACKMODE HID STORAGE MAN_Rick PROD_You SERIAL_111111111111
DELAY 2000

ATTACKMODE HID STORAGE MAN_Rick PROD_Up SERIAL_111111111111
DELAY 2000
```

*  *Ducky was plugged into my personal laptop on campus at 8:25p EST to arm the payload onto it.*
*  *Ducky was plugged into my personal laptop on campus at 8:25p EST to test the payload.*

Tried installing [USBView](https://learn.microsoft.com/en-us/windows-hardware/drivers/debugger/usbview#:~:text=versions%20of%20Windows.-,Where%20to%20get%20USBView,-To%20download%20and) for Windows to observe this, still could not. <span style="color:yellow"> - This is explored more and resolved in Chapter 20, see 2024-07-10's notes on 'Inspecting USB Devices</span>

*  *Ducky was plugged into my personal laptop on campus at 8:30p EST to arm the payload onto it.*
*  *Ducky was plugged into my personal laptop on campus at 8:30p EST to test the payload.*