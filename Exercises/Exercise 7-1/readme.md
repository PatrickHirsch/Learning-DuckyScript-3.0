### Exercise 7-1
This exercise asks for a payload that opens a text editor and forever types the lyrics to the self-referential [Song That Never Ends Song](https://www.boyscouttrail.com/content/song/song_that_never_ends-2159.asp).
#### Work
```DuckyScript
REM Title: Exercise 7-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Forever type the lyrics to the Song That Never Ends Song

REM Set attackmode as an HID device; will leverage default button behavior to end loop and re-arm
ATTACKMODE HID

REM Obligatory enumeration delay:
DELAY 2000

REM Use Run to open Notepad
GUI r
DELAY 100
STRING notepad
ENTER
DELAY 100

WHILE TRUE
	STRINGLN This is the song that doesn't end.
	STRINGLN Yes, it goes on and on, my friend.
	STRINGLN Some people started singing it, not knowing what it was.
	STRINGLN And, they'll continue singing it forever, just because...
END_WHILE
```
* *Ducky was plugged into my personal laptop on campus at 4:36p EST to test the payload*
Script worked as intended.