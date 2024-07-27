### Exercise 3-1
Script should type "Hello, World!" into a text editor, then on button press re enumerate as a flash drive.
#### Work
Copy previous code, revise to mount as only HID, then wait for button press and change to `ATTACKMODE STORAGE`

First draft code:
```DuckyScript
REM Title: Exercise 3-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, opens notepad, types "Hello, World!" then mounts as storage on button press

REM Set attackmode as an HID device
ATTACKMODE HID

REM Disable button until after typing
DISABLE_BUTTON

REM Obligitory enumeration delay:
DELAY 2000

REM Open 'Run' and wait for it to finish opening
GUI r
DELAY 100

REM Open notepad and wait for it to finish opening
STRING notepad
ENTER
DELAY 100

REM Hello, World!
STRING Hello, World!

REM Change to ATTACKMODE STORAGE following button press
WAIT_FOR_BUTTON_PRESS
ATTACKMODE STORAGE

REM Try typing ya stupid duck.  Betcha can't!
WHILE TRUE
	STRING "Curse me kilts!" -Scrooge McDuck
END_WHILE
```

* *Ducky was plugged into my personal laptop on campus at 7:32p EST to arm the payload onto it.*
* *Ducky was plugged into my personal laptop on campus at 7:33p EST to test the payload.*
* *Ducky was plugged into my personal laptop on campus at 7:33p EST to test the payload.*
* *Ducky was plugged into my personal laptop on campus at 7:35p EST to test the payload.*
* *Ducky was plugged into my personal laptop on campus at 7:38p EST to test the payload.*

Works as expected.