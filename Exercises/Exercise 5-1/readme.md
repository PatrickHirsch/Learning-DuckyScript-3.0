### Exercise 5-1
This script should open a text editor and type the lyrics to Rick Astley's *"Never Gonna Give You Up"* with a delay of 100(n-1) milliseconds before typing each line number n
#### Work:
First draft code
```DuckyScript
REM Title: Exercise 5-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Simple payload that will never give you up, let you down, nor desert you, thogh it may make you wait.

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligitory enumeration delay:
DELAY 2000

REM Use Run to open Notepad
GUI r
DELAY 100
STRING notepad
ENTER
DELAY 100

REM Begin reciting the lyrics
VAR $DELAY_TIME = 100
STRING We're no strangers to love
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING You know the rules and so do I
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING A full commitment's what I'm thinking of
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING You wouldn't get this from any other guy
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING I just wanna tell you how I'm feeling
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Gotta make you understand
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna give you up
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna let you down
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna run around and desert you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna make you cry
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna say goodbye
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna tell a lie and hurt you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING We've known each other for so long
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Your heart's been aching, but
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING You're too shy to say it
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Inside, we both know what's been going on
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING We know the game and we're gonna play it
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING And if you ask me how I'm feeling
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Don't tell me you're too blind to see
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna give you up
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna let you down
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna run around and desert you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna make you cry
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna say goodbye
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna tell a lie and hurt you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna give you up
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna let you down
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna run around and desert you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna make you cry
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna say goodbye
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna tell a lie and hurt you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING (Ooh, give you up)
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING (Ooh, give you up)
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna give, never gonna give
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING (Give you up)
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna give, never gonna give
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING (Give you up)
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING We've known each other for so long
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Your heart's been aching, but
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING You're too shy to say it
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Inside, we both know what's been going on
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING We know the game and we're gonna play it
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING I just wanna tell you how I'm feeling
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Gotta make you understand
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna give you up
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna let you down
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna run around and desert you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna make you cry
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna say goodbye
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna tell a lie and hurt you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna give you up
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna let you down
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna run around and desert you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna make you cry
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna say goodbye
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna tell a lie and hurt you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING 
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna give you up
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna let you down
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna run around and desert you
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna make you cry
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
STRING Never gonna say goodbye
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
ENTER
DELAY $DELAY_TIME
$DELAY_TIME = $( $DELAY_TIME + 100 )
STRING Never gonna tell a lie and hurt you
ENTER
```

This worked as intended.