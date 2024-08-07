### Exercise 8-1
Wants to execute a different payload given number of times button is pushed.
#### Work
Should be able to re-work logic for Caps Lock counter for this.
```DuckyScript
REM Title: Exercise 8-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Once plugged in, wait for red light, then push micro button X times before pushing caps lock to issue payload X.

ATTACKMODE HID STORAGE
$_BUTTON_TIMEOUT = 100

BUTTON_DEF
    REM Override default button action.
END_BUTTON

FUNCTION openNotepad()
	GUI r
	DELAY 100
	STRING notepad
	ENTER
	DELAY 100
END_FUNCTION

REM Declare variable $NUMBER_OF_DOTS to reference in function 
VAR $NUMBER_OF_DOTS = 0
FUNCTION printEllipsisOfLength()
	WHILE ( $NUMBER_OF_DOTS > 0)
		STRING .
		$NUMBER_OF_DOTS = ( $NUMBER_OF_DOTS - 1 )
	END_WHILE
END_FUNCTION

FUNCTION capsOn()
	IF $_CAPSLOCK_ON THEN
		RETURN TRUE
	ELSE
		CAPSLOCK
		RETURN FALSE
	END_IF
END_FUNCTION

FUNCTION countButtons()
	VAR $BUTTCOUNT = 0
	$_BUTTON_PUSH_RECEIVED = 0
    capsOn()
    LED_R
	WHILE ( $_CAPSLOCK_ON )
		IF $_BUTTON_PUSH_RECEIVED THEN
			LED_OFF
            $BUTTCOUNT = ( $BUTTCOUNT + 1 )
			$_BUTTON_PUSH_RECEIVED = 0
            DELAY 100
            LED_R
		END_IF
	END_WHILE
    LED_G
    REM Unsure why, $BUTTCOUNT always equates to twice expected.
	RETURN ( $BUTTCOUNT / 2 )
END_FUNCTION

FUNCTION PAYLOAD_1()
    openNotepad()
    STRING One
END_FUNCTION

FUNCTION PAYLOAD_2()
    openNotepad()
    STRING Two
END_FUNCTION

FUNCTION PAYLOAD_3()
    openNotepad()
    STRING Three
END_FUNCTION

FUNCTION PAYLOAD_4()
    openNotepad()
    STRING Four
END_FUNCTION

FUNCTION PAYLOAD_5()
    openNotepad()
    STRING Five and up
END_FUNCTION

DELAY 2000

$NUMBER_OF_DOTS = countButtons()

IF ( $NUMBER_OF_DOTS == 1 ) THEN
    PAYLOAD_1()
ELSE IF ( $NUMBER_OF_DOTS == 2 ) THEN
    PAYLOAD_2()
ELSE IF ( $NUMBER_OF_DOTS == 3 ) THEN
    PAYLOAD_3()
ELSE IF ( $NUMBER_OF_DOTS == 4 ) THEN
    PAYLOAD_4()
ELSE
    PAYLOAD_5()
END_IF
```