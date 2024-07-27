### Exercise 10-3
Asks for a payload to open the Windows Calculator and move it randomly about the screen, not dissimilar to a PowerShell obfuscation technique shown earlier in the chapter.
#### Work
```DuckyScript
REM Title: Exercise 10-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Open the Windows Calculator and move it about randomly

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligatory enumeration delay:
DELAY 2000

VAR $BASE_DELAY = 1000

REM Open calc
GUI r
DELAY $BASE_DELAY
STRINGLN calc
DELAY $BASE_DELAY

REM Access "move" option
ALT SPACE
DELAY $BASE_DELAY
STRING m

REM Jiggle it a bit
WHILE TRUE
	$_RANDOM_MAX = 1
	IF $_RANDOM_INT THEN
	REM Vertical Movement-----
		IF $_RANDOM_INT THEN
			HOLD UP
			$_RANDOM_MAX = 500
			DELAY $_RANDOM_INT
			RELEASE UP
		ELSE
			HOLD DOWN
			$_RANDOM_MAX = 500
			DELAY $_RANDOM_INT
			RELEASE DOWN
		END_IF
	ELSE
	REM Horizontal Movement---
		IF $_RANDOM_INT THEN
			HOLD LEFT
			$_RANDOM_MAX = 500
			DELAY $_RANDOM_INT
			RELEASE LEFT
		ELSE
			HOLD RIGHT
			$_RANDOM_MAX = 500
			DELAY $_RANDOM_INT
			RELEASE RIGHT
		END_IF
	END_IF
END_WHILE
```
This was unsuccessful on my Windows 10 machine, but did prove successful on my Windows 7 machine after the Drivers installed.  I believe the Windows 10 calculator just takes too long to open.