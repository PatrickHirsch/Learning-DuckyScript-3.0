### Exercise 4-1
This script should open https://www.example.com and full screen the browser.  Looking ahead at Exercise 4-2 this will be adapted to use constants later.
#### Work
First draft code:
```DuckyScript
REM Title: Exercise 4-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, open example.com and fullscreen the browser

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligitory enumeration delay:
DELAY 2000

REM Open 'Run' and wait for it to finish opening
GUI r
DELAY 100

REM Open https://www.example.com
STRING https://www.example.com
ENTER
DELAY 100

REM Fullscreen the browser
ALT SPACE
STRING x
```
* *Ducky was plugged into my personal laptop off-campus at 5:47p EST to arm the payload onto it.*
* *Ducky was plugged into my personal laptop off-campus at 5:48p EST to test the payload.*
* *Ducky was plugged into my personal laptop off-campus at 5:48p EST to test the payload.*

The script seemed to run too fast for the `x` to be picked up by the dialog box, revised with a delay.
Second draft code:
```DuckyScript
REM Title: Exercise 4-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, open example.com and fullscreen the browser

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligitory enumeration delay:
DELAY 2000

REM Open 'Run' and wait for it to finish opening
GUI r
DELAY 100

REM Open https://www.example.com
STRING https://www.example.com
ENTER
DELAY 100

REM Fullscreen the browser
ALT SPACE
DELAY 100
STRING x
```
* *Ducky was plugged into my personal laptop off-campus at 5:54p EST to test the payload.*
* * *Ducky was plugged into my personal laptop off-campus at 5:54p EST to test the payload.*
Script works as intended.