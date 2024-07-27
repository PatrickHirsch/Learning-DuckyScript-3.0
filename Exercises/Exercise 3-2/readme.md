### Exercise 3-2
Script should toggle between `ATTACKMODE STORAGE` and `ATTACKMODE HID` on button push.
#### Work
First draft code:
```DuckyScript
REM Title: Exercise 3-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Toggle between HID and STORAGE on button press

REM Set attackmode as a STORAGE device to start
ATTACKMODE STORAGE

REM Obligitory enumeration delay:
DELAY 2000

BUTTON_DEF
	REM if HID, make STORAGE.  else if STORAGE, make HID
	IF($_CURRENT_ATTACKMODE == 1) THEN
		ATTACKMODE STORAGE
	ELSE IF($_CURRENT_ATTACKMODE == 2)
		ATTACKMODE HID
	END_IF
END_BUTTON

REM Try typing a . every second to see if it can
WHILE TRUE
	STRING .
	DELAY 1000
END_WHILE
```

* *Ducky was plugged into my personal laptop on campus at 7:48p EST to test the payload.*

The Ducky would mount as storage, then, on button press change to HID and begin typing periods, though would not mount as storage again on button press.  I figure this has to do with the syntax of the ELSE IF, so I changed thing around there

```DuckyScript
REM Title: Exercise 3-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Toggle between HID and STORAGE on button press

REM Set attackmode as a STORAGE device to start
ATTACKMODE STORAGE

REM Obligitory enumeration delay:
DELAY 2000

BUTTON_DEF
	REM if HID, make STORAGE.  else make HID
	IF ( $_CURRENT_ATTACKMODE == 1 ) THEN
		ATTACKMODE STORAGE
	ELSE IF ( $_CURRENT_ATTACKMODE == 2 ) THEN
		ATTACKMODE HID
	END_IF
END_BUTTON

REM Try typing a . every second to see if it can
WHILE TRUE
	STRING .
	DELAY 1000
END_WHILE
```

* * *Ducky was plugged into my personal laptop on campus at 8:02p EST to arm the payload onto it.*
*  *Ducky was plugged into my personal laptop on campus at 8:03p EST to test the payload.*
* * *Ducky was plugged into my personal laptop on campus at 8:05p EST to arm the payload onto it.*
*  *Ducky was plugged into my personal laptop on campus at 8:06p EST to test the payload.*

***These changes again did not work, will look at later.***

<span style="color:yellow">- Revisiting on 2024-07-15, found the issue is resolved when removing the infinite while-loop meant to debug/confirm.  Unsure how the button function injects into the running code, but suspect the issue lies somewhere in there.</span>
```DuckyScript
REM Title: Exercise 3-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Toggle between HID and STORAGE on button press

BUTTON_DEF
    IF ($_CURRENT_ATTACKMODE == 1) THEN
        ATTACKMODE STORAGE
    ELSE IF ($_CURRENT_ATTACKMODE == 2)
        ATTACKMODE HID
    ELSE
        ATTACKMODE HID STORAGE
    END_IF
END_BUTTON
```
