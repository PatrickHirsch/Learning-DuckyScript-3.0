### Exercise 11-3
Asks for Exercise 5-2 to be modified to include an incresingly higher level of jitter with each line of the lyrics.
#### Work
Will make it randomly increase between 100-500 ms each line break by modifying the `DO_DELAY()` function.
```DuckyScriot
REM Title: Exercise 5-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Simple payload that will never give you up, let you down, nor desert you, thogh it may make you wait.

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Set delay after the first line, after the second line will be twice the value, after the third three times, and so on.
VAR $INITIAL_DELAY = 100

REM Obligatory enumeration delay:
DELAY 2000

REM Use Run to open Notepad
GUI r
DELAY 100
STRING notepad
ENTER
DELAY 100

REM Handles line breaks, does delay, and increments line counter
VAR $LINE_NUM = 1
VAR $DELAY_TIME = 0
$_RANDOM_MIN = 100
$_RANDOM_MAX = 500
$_JITTER_ENABLED = TRUE
FUNCTION DO_DELAY()
	ENTER
    $DELAY_TIME = ( $INITIAL_DELAY * $LINE_NUM)
	DELAY $DELAY_TIME
	$LINE_NUM = ( $LINE_NUM + 1 )
	$_JITTER_MAX = ($_JITTER_MAX + $_RANDOM_INT)
END_FUNCTION

REM Begin reciting the lyrics
STRING We're no strangers to love
DO_DELAY()
STRING You know the rules and so do I
DO_DELAY()
STRING A full commitment's what I'm thinking of
DO_DELAY()
STRING You wouldn't get this from any other guy
DO_DELAY()
STRING  
DO_DELAY()
STRING I just wanna tell you how I'm feeling
DO_DELAY()
STRING Gotta make you understand
DO_DELAY()
REM ...

REM Rest of script ommitted for space.
```
This works as intended, though with these values Jitter gets painfully slow by the third line.