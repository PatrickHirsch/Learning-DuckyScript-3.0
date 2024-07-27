### Exercise 1-1
Choosing to work on Windows, the instructions say the script must open the terminal, run a command to show a listing of files and directories, pause for 5 seconds, close the terminal.
#### Work:
Without trying anything, the approach seems obvious: 
* `🪟`+`R` for Run
* Open cmd or PowerShell
* Run either `dir` or `ls`
* `DELAY 5000`
* Run either `exit` or `CTRL`+`C`

First draft code
```DuckyScript
REM Title: Exercise 1-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, opens PS terminal, runs ls, closes terminal after 5 seconds

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligitory enumeration delay:
DELAY 2000

REM Open 'Run' and wait for it to finish opening
GUI r
DELAY 100

REM Open PowerShell pre-loaded with commands to do listing and wait 5 seconds
STRING powershell "ls;sleep 5"
```

* *Ducky was plugged into my personal laptop on campus at 6:31p EST to arm the payload onto it.*
* *Ducky was plugged into my personal laptop on campus at 6:32p EST to test the payload.*

Testing revealed a failure to issue an `ENTER` after entering the command into Run.  This was revised and tested again.
Second draft code
```DuckyScript
REM Title: Exercise 1-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, opens PS terminal, runs ls, closes terminal after 5 seconds

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligitory enumeration delay:
DELAY 2000

REM Open 'Run' and wait for it to finish opening
GUI r
DELAY 100

REM Open PowerShell pre-loaded with commands to do listing and wait 5 seconds
STRING powershell "ls;sleep 5"
ENTER
```
* *Ducky was plugged into my personal laptop on campus at 6:36p EST to arm the revised payload onto it.*
* *Ducky was plugged into my personal laptop on campus at 6:37p EST to test the revised payload.*
This proved successful.

It is worth noting, as a form of optimization, rather than using a `DELAY 5000` to achieve the "Wait 5 seconds" requirement, a PowerShell `sleep 5` command was used and I relied on PowerShell's default behavior of closing when it finishes its Run-given instructions.  This, I believe, ensures the "attack" will be successful at hiding its tracks by assuring the window is closed, even if it is moved out of focus or device unplugged.