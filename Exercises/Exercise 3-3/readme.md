### Exercise 3-3
Script should should bypass keyboard setup on a Mac computer.
#### Work
I do not have a personal Mac to use, so cannot test it, but mimicking any Apple keyboard should do the trick, such their [Aluminum Mini Keyboard (ANSI)](http://www.linux-usb.org/usb.ids#:~:text=021d%20%20Aluminum%20Mini%20Keyboard%20(ANSI)).  
```DuckyScript
ATTACKMODE HID VID_05ac PID_021d
```