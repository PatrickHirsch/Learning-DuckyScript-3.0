### Exercise 1-2
This exercise wants me to revise the previous script to minimize the terminal window after 5 seconds rather than closing it.
#### Work: 
Considering this, the optimization of the `sleep` over the `DELAY` cannot be utilized, and PowerShell must be made to stay open after `ls` if the command is to be passed to it from Run.

It gives the hint for Windows and Linux to use `ALT`+`SPACE`.  Trying it, I observe it's the equivalent of clicking a program's icon on the title bar with `n` as the hotkey to minimize the window.  I will assume at first there's no need for a delay between theys actions and revise if needed.

The steps would seem to be:
* Revise what's entered into Run to `powershell -NoExit ls` to run just the one command and not close
* `DELAY 5000`
* `ALT`+`SPACE`
* `n`

First draft code:
```DuckyScript
REM Title: Exercise 1-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, opens PS terminal, runs ls, minimize terminal after 5 seconds

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligitory enumeration delay:
DELAY 2000

REM Open 'Run' and wait for it to finish opening
GUI r
DELAY 100

REM Open PowerShell pre-loaded with commands to do listing and wait 5 seconds
STRING powershell -NoExit ls
ENTER

REM Wait 5 seconds, minimize terminal window
DELAY 5000
ALT SPACE
n
```

* *Ducky was plugged into my personal laptop on campus at 7:01p EST to arm the payload onto it.*
* *Ducky was plugged into my personal laptop on campus at 7:02p EST to test the payload.*
* *Ducky was plugged into my personal laptop on campus at 7:02p EST to test/observe the payload once again.*

This proved to be successful on my computer, though a slower one may require a delay before the `n` keystroke.