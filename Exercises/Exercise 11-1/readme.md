### Exercise 11-1
Asks for any previous payload to be modified to "self destruct" after execution.
#### Work
Yesterday's Jet Pack Adventure script has a definitive end rather than any loops or logic.  By appending a `HIDE_PAYLOAD` at the end, it should only play the game after being plugged in once, 
```DuckyScript
REM Title: Exercise 11-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: Crash very quickly in Jet Pack Adventure, earn about 14 coins.  Self-destruct script after

REM Set attackmode as an HID device; not storage this time.
ATTACKMODE HID

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

REM "Self-destruct" and appear as a flash drive
HIDE_PAYLOAD
ATTACKMODE STORAGE
```
This works the same as before on the first game, quickly crashing the JetPack, before mounting as a mass storage device with no `payload.bin` present.  As expected, when plugged in on the second playthrough it simply mounts as a storage device and displays the Red LED, default behavior for when there is no `payload.bin` present.