### Exercise 7-5
Asks for a script to open a text editor and continuously type smiles (`-)`)  and on button push toggle with frownies (`-(`)
#### Work
```DuckyScript
REM Title Exercise 7-5 from USB Rubber Ducky Keystroke Injection Attacks with Advanced DuckyScript
REM Author Patrick Hirsch HirschP2@nku.edu
REM Description Repeatedly print emoticons, toggling between -) & -( on button press, for eternity

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Override default Button behavior
BUTTON_DEF
END_BUTTON

REM Obligatory enumeration delay
DELAY 2000

REM Use Run to open Notepad
GUI r
DELAY 100
STRING notepad
ENTER
DELAY 100

WHILE TRUE
	STRING -
	IF ( $_BUTTON_PUSH_RECEIVED % 2 ) THEN
		STRINGLN )
	ELSE
		STRINGLN (
	END_IF
END_WHILE
```

Starts with frowns, changs to smiles on firs button press, doesn't toggle.  I had believed `$_BUTTON_PUSH_RECEIVED` counted number of pushes, thus the mod 2 of it would toggle between 01, truefalse.  Will instead toggle a variable on button press.
```DuckyScript
REM Title Exercise 7-5 from USB Rubber Ducky Keystroke Injection Attacks with Advanced DuckyScript
REM Author Patrick Hirsch HirschP2@nku.edu
REM Description Repeatedly print emoticons, toggling between -) & -( on button press, for eternity

REM Set attackmode as an HID device; can't really re-arm with all those faces
ATTACKMODE HID STORAGE

REM Obligatory enumeration delay
DELAY 2000

REM Boolean variable to determine whether to print -) or -(
VAR $HAPPY = TRUE

REM Override default Button behavior to toggle $HAPPY
BUTTON_DEF
	IF $HAPPY
		$HAPPY = FALSE
	ELSE
		$HAPPY = TRUE
	END_IF
END_BUTTON

REM Use Run to open Notepad
GUI r
DELAY 100
STRING notepad
ENTER
DELAY 100

REM Infinite loop to forever print emoticons
WHILE TRUE
	REM Print eyes & nose each iteration
	STRING -
	
	REM Print mouth with proper concavity given $HAPPY mode
	IF $HAPPY THEN
		STRINGLN )
	ELSE
		STRINGLN (
	END_IF
END_WHILE
```

This works as intended.