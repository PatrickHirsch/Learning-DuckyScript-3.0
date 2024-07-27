### Exercise 2-2
This exercise asks the previous script to be modified to pause between "Hello," and "World" and await a button push.
#### Work
A simple `WAIT_FOR_BUTTON_PRESS` should suffice here:

```DuckyScript
REM Title: Exercise 2-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, opens notepad, types "Hello," waits for button push, types " World!", and blinks LED for 5 seconds

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
STRING Hello,
WAIT_FOR_BUTTON_PRESS
STRING  World!

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

* *Ducky was plugged into my personal laptop on campus at 5:20p EST to test the payload.*

This proves successful.