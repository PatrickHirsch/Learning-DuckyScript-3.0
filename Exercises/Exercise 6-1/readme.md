### Exercise 6-1
This exercise asks for the modification of the script written in Exercise 5-2 so that there exists a variable that lets the user decide weather or not to delay between lines.
#### Work
The use of the `DO_DELAY()` function should make this simple, simply wrapping everything but the `ENTER`s in an `IF` as no other functions of it are necessary.  It is considered that it may be useful to track line numbers for other reasons if the script were expanded, although for now it's just extra computations.
```DuckyScript
REM Title: Exercise 6-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Simple payload that will never give you up, let you down, nor desert you, thogh it may make you wait.

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Boolen value to, if set to true, cause a growing delay between typing each line 
VAR $DO_DELAY = TRUE

REM Set delay after the first line, after the second line will be twice the value, after the third three times, and so on.  Irrelivant if $DO_DELAY is set to FALSE or 0
VAR $INITIAL_DELAY = 100

REM Obligatory enumeration delay:
DELAY 2000

REM Use Run to open Notepad
GUI r
DELAY 100
STRING notepad
ENTER
DELAY 100

REM Handles line breaks, does delay, and increments line counter
VAR $LINE_NUM = 1
VAR $DELAY_TIME = 0
FUNCTION LINEBREAK()
	ENTER
    IF $DO_DELAY THEN
        $DELAY_TIME = ( $INITIAL_DELAY * $LINE_NUM)
	    DELAY $DELAY_TIME
	    $LINE_NUM = ( $LINE_NUM + 1 )
    END_IF
END_FUNCTION

REM Begin reciting the lyrics
STRING We're no strangers to love
LINEBREAK()
STRING You know the rules and so do I
LINEBREAK()
STRING A full commitment's what I'm thinking of
LINEBREAK()
STRING You wouldn't get this from any other guy
LINEBREAK()
STRING  
LINEBREAK()
STRING I just wanna tell you how I'm feeling
LINEBREAK()
STRING Gotta make you understand
LINEBREAK()
STRING  
LINEBREAK()
STRING Never gonna give you up
LINEBREAK()
STRING Never gonna let you down
LINEBREAK()
STRING Never gonna run around and desert you
LINEBREAK()
STRING Never gonna make you cry
LINEBREAK()
STRING Never gonna say goodbye
LINEBREAK()
STRING Never gonna tell a lie and hurt you
LINEBREAK()
STRING  
LINEBREAK()
STRING We've known each other for so long
LINEBREAK()
STRING Your heart's been aching, but
LINEBREAK()
STRING You're too shy to say it
LINEBREAK()
STRING Inside, we both know what's been going on
LINEBREAK()
STRING We know the game and we're gonna play it
LINEBREAK()
STRING  
LINEBREAK()
STRING And if you ask me how I'm feeling
LINEBREAK()
STRING Don't tell me you're too blind to see

REM !!! --Rest of song ommitted for brevity.-- !!!
```
* *Ducky was plugged into my personal laptop on campus at 1:39p EST to arm the payload onto it.*
* *Ducky was plugged into my personal laptop on campus at 1:41p EST to test the payload*
* *Ducky was plugged into my personal laptop on campus at 1:42p EST to test the payload*
* *Ducky was plugged into my personal laptop on campus at 1:45p EST to test the payload*
* *Ducky was plugged into my personal laptop on campus at 1:46p EST to test the payload*