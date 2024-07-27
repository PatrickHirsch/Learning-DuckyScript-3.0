### Exercise 2-3
This exercise asks the script from 2-1 to be modified to toggle the LED Red/Green between each char.  No indication is given to slow the typing.
#### Work
While not an elegant approach, with the tools avalible it seems easiest to just throw `LED_R`s and `LED_G`s between `STRING`s

First draft code
```DuckyScript
REM Title: Exercise 2-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>

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
STRING H
LED_G
STRING e
LED_R
STRING l
LED_G
STRING l
LED_R
STRING o
LED_G
STRING ,
LED_R
STRING  
LED_G
STRING W
LED_R
STRING o
LED_G
STRING r
LED_R
STRING l
LED_G
STRING d
LED_R
STRING !

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

* *Ducky was plugged into my personal laptop on campus at 5:41p EST to test the payload.*

This appears to have work, though as expected, it was too fast to observe.  Delays were added to a revision:
```DuckyScript
REM Title: Exercise 2-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>

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
STRING H
LED_G
DELAY 100
STRING e
LED_R
DELAY 100
STRING l
LED_G
DELAY 100
STRING l
LED_R
DELAY 100
STRING o
LED_G
DELAY 100
STRING ,
LED_R
DELAY 100
STRING  
LED_G
DELAY 100
STRING W
LED_R
DELAY 100
STRING o
LED_G
DELAY 100
STRING r
LED_R
DELAY 100
STRING l
LED_G
DELAY 100
STRING d
LED_R
DELAY 100
STRING !

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

* *Ducky was plugged into my personal laptop on campus at 5:43p EST to test a revised payload.*
* * *Ducky was plugged into my personal laptop on campus at 5:44p EST to test a revised payload.*

This works as expected.