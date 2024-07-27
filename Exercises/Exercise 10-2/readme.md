### Exercise 10-2
Asks for a payload to "play a video game poorly"
#### Work
Opting for Club Penguin's Jet Pack Adventure, I took note of how to crash into a tree.  Simply fly up for about 1 second, to the left for 5 seconds, then up and right for 8, about then you can descend into a tree top.
```DuckyScript
REM Title: Exercise 10-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Crash very quickly in Jet Pack Adventure, earn about 14 coins

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Obligatory enumeration delay:
DELAY 2000

HOLD UP
DELAY 1000
RELEASE UP

HOLD RIGHT
DELAY 5000
RELEASE RIGHT

HOLD UP
DELAY 1000
HOLD RIGHT
DELAY 3500
RELEASE RIGHT
DELAY 500
RELEASE UP
```

Some variance exists in the game's knock-back mechanics upon collisions, but consistently the Duck crashes the Penguin into a couple trees before hitting an anvil and destroying the jetpack ending the game with about 14 coins.  On occasion, the Duck may pilot the Penguin further, though this misses the coin worth 10 and yields a total of only 8 coins. 

Playing a keyboard-based game could be a fun yet simple lab exercise for a younger audience.