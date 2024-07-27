### Exercise 10-1
Asks for a payload to hold shift while CAPSLOCK is on, effectively taking away capital letters when Caps Lock is on.
#### Work
```DuckyScript
REM Title: Exercise 10-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Hold shift whenever Caps Lock is on.

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligatory enumeration delay:
DELAY 2000

WHILE TRUE
	IF $_CAPSLOCK_ON THEN
		INJECT_MOD
		HOLD SHIFT
	ELSE
		INJECT_MOD
		RELEASE SHIFT
	END_IF
END_WHILE
```
Script works as intended as can be easily observed with the On-Screen Keyboard.