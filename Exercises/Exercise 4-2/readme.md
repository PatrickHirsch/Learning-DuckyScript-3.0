### Exercise 4-2
This script should revise the previous to use constants and comments.
#### Work
First draft code:
```DuckyScript
REM Title: Exercise 4-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, open defined webpage, fullscreen the browser, and type a message for the user.

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM ---== CONSTANTS DEFINED ==---
DEFINE WEB_ADDRESS https://www.example.com
DEFINE AUTHOR_NAME HirschP2
DEFINE DELAY_TIME 100

REM Obligitory enumeration delay:
DELAY 2000

REM Open 'Run' and wait for it to finish opening
GUI r
DELAY DELAY_TIME

REM Open specified webpage and fullscreen the browser
STRING WEB_ADDRESS
ENTER
DELAY DELAY_TIME
ALT SPACE
DELAY DELAY_TIME
STRING x

REM Open 'Run' and wait for it to finish opening
GUI r
DELAY DELAY_TIME

REM Open notepad and type a message to the user
STRING notepad
ENTER
ENTER
DELAY DELAY_TIME
STRING Dear User,
ENTER
STRING Please checkout my website, 
STRING WEB_ADDRESS
STRING  , which has been opened for your convinence.
ENTER
ENTER
STRING Sincerely,
ENTER
STRING AUTHOR_NAME
```
* * *Ducky was plugged into my personal laptop off-campus at 6:13p EST to test the payload.*
Payload works as intended.