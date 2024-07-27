### Exercise 1-3
This exercise wants me to revise the initial script from Exercise 1-1 to copy the terminal contents to a newly opened notepad after 5 seconds rather than closing it.

#### Work
After much searching for a way to "select all" in PowerShell I eventually stumbled across the info that the same menu reveled by `ALT`+`SPACE` has the option.  The script from Exercise 1-2 is revised following the `ALT SPACE` line.

First draft code:
```DuckyScript
REM Title: Exercise 1-3 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: For Windows 10, opens PS terminal, runs ls, copies terminal output to notepad after 5 seconds

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

REM Wait 5 seconds, select all text in terminal window and copy
DELAY 5000
ALT SPACE
STRING e
STRING s
CTRL c

REM Open Run, then notepad
GUI r
DELAY 100
STRING notepad
ENTER

REM Paste once Notepad opens
DELAY 100
CTRL v
```

* *Ducky was plugged into my personal laptop on campus at 7:25p EST to arm the payload onto it.*
* *Ducky was plugged into my personal laptop on campus at 7:26p EST to test the payload.*

This was successful. 