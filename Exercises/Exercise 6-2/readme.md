### Exercise 6-2
This exercise asks for the modification of the script written in Exercise 5-2 so that there exists a variable that lets the user decide weather or not to delay between lines.
#### Work
* Open run, then notepad for a place to run
* Type Prompt
* Reset `$_BUTTON_PUSH_RECEIVED`
* `DELAY 50000`
* If `$_BUTTON_PUSH_RECEIVED` do thing else other thing
```DuckyScript
REM Title: Exercise 6-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: ...

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Override default Button behavior
BUTTON_DEF
END_BUTTON

REM Obligatory enumeration delay:
DELAY 2000

REM Use Run to open Notepad
GUI r
DELAY 100
STRING notepad
ENTER
DELAY 100

REM Type Prompt
STRING Push Micro Button within the next 5 seconds
$_BUTTON_PUSH_RECEIVED = 0
VAR $timer = 0
WHILE($timer<6)
	DELAY 1000
	STRING .
	$timer = ( $timer + 1 )
END_WHILE
ENTER

$timer = 0
IF $_BUTTON_PUSH_RECEIVED THEN
	STRING Button has been pushed.
	ENTER
	WHILE ( $timer < 5000 )
		LED_G
		DELAY 250
		LED_OFF
		DELAY 250
		$timer=($timer+500)
	END_WHILE
ELSE
	STRING Button has NOT been pushed.
	ENTER
	WHILE ( $timer < 5000 )
		LED_R
		DELAY 250
		LED_OFF
		DELAY 250
		$timer=($timer+500)
	END_WHILE
END_IF
```