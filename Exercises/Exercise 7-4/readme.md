### Exercise 7-4
Asks to use Num, Caps, and Scroll locks to create a "Knight Rider LED Pattern" on the keyboard's indicators.
#### Work
The decided upon pattern was a simple blink all twice, then bounce a single LED between them 5 times.
Functions were created for each needed state (all on, all off, each on indivisually)

* *Ducky was plugged into my personal laptop on campus at 5:14p EST to arm a payload.*
* *Ducky was plugged into my personal laptop on campus at 5:14p EST to test a payload.*

```DuckyScript
REM Title: Exercise 7-4 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Send a series of lock key presses to animate a "Knight Rider LED Pattern" on the LED indicators

ATTACKMODE HID STORAGE

FUNCTION ALL_LOCK_OFF()
	IF $_NUMLOCK_ON THEN
		NUMLOCK
	END_IF
	IF $_CAPSLOCK_ON THEN
		CAPSLOCK
	END_IF
	IF $_SCROLLLOCK_ON THEN
		SCROLLLOCK
	END_IF
END_FUNCTION

FUNCTION ALL_LOCK_ON()
	IF ( $_NUMLOCK_ON == FALSE ) THEN
		NUMLOCK
	END_IF
	IF ( $_CAPSLOCK_ON == FALSE ) THEN
		CAPSLOCK
	END_IF
	IF ( $_SCROLLLOCK_ON == FALSE ) THEN
		SCROLLLOCK
	END_IF
END_FUNCTION

FUNCTION ONLY_LOCK_NUM()
	IF ( $_NUMLOCK_ON == FALSE ) THEN
		NUMLOCK
	END_IF
	IF $_CAPSLOCK_ON THEN
		CAPSLOCK
	END_IF
	IF $_SCROLLLOCK_ON THEN
		SCROLLLOCK
	END_IF
END_FUNCTION

FUNCTION ONLY_LOCK_CAP()
	IF $_NUMLOCK_ON THEN
		NUMLOCK
	END_IF
	IF ( $_CAPSLOCK_ON == FALSE ) THEN
		CAPSLOCK
	END_IF
	IF $_SCROLLLOCK_ON THEN
		SCROLLLOCK
	END_IF
END_FUNCTION

FUNCTION ONLY_LOCK_SCROLL()
	IF $_NUMLOCK_ON THEN
		NUMLOCK
	END_IF
	IF $_CAPSLOCK_ON THEN
		CAPSLOCK
	END_IF
	IF ( $_SCROLLLOCK_ON == FALSE ) THEN
		SCROLLLOCK
	END_IF
END_FUNCTION

VAR $index = 0
VAR $DELAY_VAL = 100
WHILE TRUE
    $index = 0
    WHILE ( $index <= 2 )
        ALL_LOCK_ON()
		DELAY $DELAY_VAL
        ALL_LOCK_OFF()
		DELAY $DELAY_VAL
        $index = ( $index + 1 )
    END_WHILE

    $index = 0
    WHILE ( $index <= 5 )
        ONLY_LOCK_NUM()
		DELAY $DELAY_VAL
        ONLY_LOCK_CAP()
		DELAY $DELAY_VAL
        ONLY_LOCK_SCROLL()
		DELAY $DELAY_VAL
        ONLY_LOCK_CAP()
		DELAY $DELAY_VAL
        ONLY_LOCK_NUM()
		DELAY $DELAY_VAL
        $index = ( $index + 1 )
    END_WHILE
END_WHILE
```
* *Ducky was plugged into my personal laptop on campus at 5:28p EST to test the payload.*
* *Ducky was plugged into my personal laptop on campus at 5:31p EST to test the payload.*
* *Ducky was plugged into my personal laptop on campus at 5:32p EST to test the payload.*
* Ducky was plugged into my personal laptop on campus at 5:55p EST to test the payload.*

Script woks as intended