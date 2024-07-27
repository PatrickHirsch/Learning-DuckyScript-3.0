### Exercise 5-2
This exercise asked for the previous code to be revised in manners largely already  covered.  Instead, I opted to try using a function for the delays and their timings.
#### Work:
First draft code:
```DuckyScript
REM Title: Exercise 5-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Simple payload that will never give you up, let you down, nor desert you, thogh it may make you wait.

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Set delay after the first line, after the second line will be twice the value, after the third three times, and so on.
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
FUNCTION DO_DELAY()
	ENTER
    $DELAY_TIME = ( $INITIAL_DELAY * $LINE_NUM)
	DELAY $DELAY_TIME
	$LINE_NUM = ( $LINE_NUM + 1 )
END_FUNCTION

REM Begin reciting the lyrics
STRING We're no strangers to love
DO_DELAY()
STRING You know the rules and so do I
DO_DELAY()
STRING A full commitment's what I'm thinking of
DO_DELAY()
STRING You wouldn't get this from any other guy
DO_DELAY()
STRING  
DO_DELAY()
STRING I just wanna tell you how I'm feeling
DO_DELAY()
STRING Gotta make you understand
DO_DELAY()
STRING  
DO_DELAY()
STRING Never gonna give you up
DO_DELAY()
STRING Never gonna let you down
DO_DELAY()
STRING Never gonna run around and desert you
DO_DELAY()
STRING Never gonna make you cry
DO_DELAY()
STRING Never gonna say goodbye
DO_DELAY()
STRING Never gonna tell a lie and hurt you
DO_DELAY()
STRING  
DO_DELAY()
STRING We've known each other for so long
DO_DELAY()
STRING Your heart's been aching, but
DO_DELAY()
STRING You're too shy to say it
DO_DELAY()
STRING Inside, we both know what's been going on
DO_DELAY()
STRING We know the game and we're gonna play it
DO_DELAY()
STRING  
DO_DELAY()
STRING And if you ask me how I'm feeling
DO_DELAY()
STRING Don't tell me you're too blind to see
DO_DELAY()
STRING  
DO_DELAY()
STRING Never gonna give you up
DO_DELAY()
STRING Never gonna let you down
DO_DELAY()
STRING Never gonna run around and desert you
DO_DELAY()
STRING Never gonna make you cry
DO_DELAY()
STRING Never gonna say goodbye
DO_DELAY()
STRING Never gonna tell a lie and hurt you
DO_DELAY()
STRING  
DO_DELAY()
STRING Never gonna give you up
DO_DELAY()
STRING Never gonna let you down
DO_DELAY()
STRING Never gonna run around and desert you
DO_DELAY()
STRING Never gonna make you cry
DO_DELAY()
STRING Never gonna say goodbye
DO_DELAY()
STRING Never gonna tell a lie and hurt you
DO_DELAY()
STRING  
DO_DELAY()
STRING (Ooh, give you up)
DO_DELAY()
STRING (Ooh, give you up)
DO_DELAY()
STRING Never gonna give, never gonna give
DO_DELAY()
STRING (Give you up)
DO_DELAY()
STRING Never gonna give, never gonna give
DO_DELAY()
STRING (Give you up)
DO_DELAY()
STRING  
DO_DELAY()
STRING We've known each other for so long
DO_DELAY()
STRING Your heart's been aching, but
DO_DELAY()
STRING You're too shy to say it
DO_DELAY()
STRING Inside, we both know what's been going on
DO_DELAY()
STRING We know the game and we're gonna play it
DO_DELAY()
STRING  
DO_DELAY()
STRING I just wanna tell you how I'm feeling
DO_DELAY()
STRING Gotta make you understand
DO_DELAY()
STRING  
DO_DELAY()
STRING Never gonna give you up
DO_DELAY()
STRING Never gonna let you down
DO_DELAY()
STRING Never gonna run around and desert you
DO_DELAY()
STRING Never gonna make you cry
DO_DELAY()
STRING Never gonna say goodbye
DO_DELAY()
STRING Never gonna tell a lie and hurt you
DO_DELAY()
STRING  
DO_DELAY()
STRING Never gonna give you up
DO_DELAY()
STRING Never gonna let you down
DO_DELAY()
STRING Never gonna run around and desert you
DO_DELAY()
STRING Never gonna make you cry
DO_DELAY()
STRING Never gonna say goodbye
DO_DELAY()
STRING Never gonna tell a lie and hurt you
DO_DELAY()
STRING  
DO_DELAY()
STRING Never gonna give you up
DO_DELAY()
STRING Never gonna let you down
DO_DELAY()
STRING Never gonna run around and desert you
DO_DELAY()
STRING Never gonna make you cry
DO_DELAY()
STRING Never gonna say goodbye
DO_DELAY()
STRING Never gonna tell a lie and hurt you
ENTER
```
This worked as intended.
This code could be condensed with functions for repeated parts of the song.