### Exercise 2-1
The payload should open notepad on the target system (Windows 10), type "Hello, World!" and then blink the LED Green for 5 seconds
#### Work
* `🪟`+`R` for Run
* Type 'notepad' then `ENTER`
* Wait for it to open.
* `STRING Hello, World!`
* Loop & use delays for timing?

First draft code
```DuckyScript
REM Title: Exercise 2-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, opens notepad, types "Hello, World!" and blinks LED for 5 seconds

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Disable LED so that I alone may control it
LED_OFF

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

REM Blinking - $timer records milliseconds passed by the delays, toggles LED with delays between them. 5000ms=5s
VAR $timer = 0
WHILE($timer<5000)
	LED_G
	DELAY 250
	LED_OFF
	DELAY 250
	$timer=($timer+500)
END_WHILE
```

* *Ducky was plugged into my personal laptop on campus at 5:02p EST to arm the payload onto it.*
* * *Ducky was plugged into my personal laptop on campus at 5:03p EST to test the payload.*
* * *Ducky was plugged into my personal laptop on campus at 5:06p EST to test the payload.*

The LED was observed to keep blinking well beyond 5 seconds... Eventually I stumbled into the solution to the issue being the need for spaces surrounding an `=` when changing a variable's value,

* * *Ducky was plugged into my personal laptop on campus at 5:14p EST to test a revised payload.*

This was successful:
```DuckyScript
REM Title: Exercise 2-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, opens notepad, types "Hello, World!" and blinks LED for 5 seconds

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Disable LED so that I alone may control it
LED_OFF

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

REM Blinking - $timer records milliseconds passed by the delays, toggles LED with delays between them. 5000ms=5s
VAR $timer = 0
WHILE($timer<5000)
	LED_G
	DELAY 250
	LED_OFF
	DELAY 250
	$timer = ($timer+500)
END_WHILE
```