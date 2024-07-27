### Exercise 7-2
Asks for a script to open notepad and type the lyrics to [John Jacob Jingleheimer Schmidt](https://www.scoutsongs.com/lyrics/johnjacob.html) 4 times then blink LED Green indefinitely, if the button is ever pushed, stop and blink Red indefinitely.
#### Work
```DuckyScript
REM Title: Exercise 7-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Type the lyrics to John Jacob Jingleheimer Schmidt a specified number of times, or until button press.

REM ---== The $TIMES_TO_PRINT variable will define how many time the lyrics will be printed ==---
VAR $TIMES_TO_PRINT = 4

BUTTON_DEF
	WHILE TRUE
		LED_R
		DELAY 250
		LED_OFF
		DELAY 250
	END_WHILE
END_BUTTON

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligatory enumeration delay:
DELAY 2000

REM Use Run to open Notepad
GUI r
DELAY 100
STRING notepad
ENTER
DELAY 100

WHILE ( $TIMES_TO_PRINT > 0 )
	STRINGLN John Jacob Jingleheimer Schmidt,
	STRINGLN His name is my name too.
	STRINGLN Whenever we go out,
	STRINGLN The people always shout,
	STRINGLN There goes John Jacob Jingleheimer Schmidt.
	STRINGLN Dah dah dah dah, dah dah dah
	$TIMES_TO_PRINT = ( $TIMES_TO_PRINT - 1 )
END_WHILE

WHILE TRUE
	LED_G
	DELAY 250
	LED_OFF
	DELAY 250
END_WHILE
```

* *Ducky was plugged into my personal laptop on campus at 4:46p EST to test the payload*
* *Ducky was plugged into my personal laptop on campus at 4:46p EST to test the payload*
Script worked as intended.