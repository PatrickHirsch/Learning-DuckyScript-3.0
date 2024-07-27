### Exercise 7-3
Asks for a modification to the script from Exercise 6-2 that does not make sense.  It is referred to as a caps lock payload although caps lock is not involved in  that exercise.

Instead focusing on the sentence "indefinitely ensure the caps lock function is enabled" and writing a payload to make it so that caps lock is always enabled.
#### Work
Within an infinite loop, check if caps lock is not enabled and if not, sent a caps lock key press to enable it.
```DuckyScript
REM Title: Force Caps Lock
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: If capslock is ever disabled, Ducky turns it back on.  Use button to stop.

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligatory enumeration delay, probobly not nessisary in this case
DELAY 2000

WHILE TRUE
	IF ( $_CAPSLOCK_ON == FALSE ) THEN
		CAPSLOCK
	END_IF
END_WHILE
```
* *Ducky was plugged into my personal laptop on campus at 5:00p EST to test the payload*

SCRIPT WORKS AS INTENDED, ALTHOGH MICRO PUSH BUTTON DOES NOT DISABLE IT.