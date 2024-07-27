## Chapter 20 Exercises:
### Exercise 9-1
Asks for script to open terminal, create 20 files on current user's desktop with random contents and names, close terminal

#### Work
```DuckyScript
REM Title: Exercise 9-1 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: In Windows, Create 20 randomly named files of randomness on the Desktop

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Open PowerShell
FUNCTION openTerminal()
	GUI r
	DELAY 100
	STRING powershell
	ENTER
	DELAY 100
END_FUNCTION

REM Index used for all loops.  Referenced in fileContents() & fileName()
VAR $INDEX = 0

REM Type a random number of random letters between 100-150, upper and lowercase
FUNCTION fileContents()
	$_RANDOM_MIN = 100
	$_RANDOM_MAX = 150
	$INDEX = $_RANDOM_INT
	WHILE ( $INDEX > 0 )
		RANDOM_LETTER
		$INDEX = ( $INDEX - 1 )
	END_WHILE
END_FUNCTION

REM Type a random number of random letters between 10-20, upper and lowercase
FUNCTION fileName()
	$_RANDOM_MIN = 10
	$_RANDOM_MAX = 20
	$INDEX = $_RANDOM_INT
	WHILE ( $INDEX > 0 )
		RANDOM_LETTER
		$INDEX = ( $INDEX - 1 )
	END_WHILE
END_FUNCTION

REM Types and issues a PowerShell command to echo a string (via fileContents()) into a file (via fileName()) on the current user's Desktop
REM .duck extention used for easy cleanup.
FUNCTION createFile()
	STRING echo "
	fileContents()
	STRING " >> ~\Desktop\
	fileName()
	STRING .duck
	ENTER
END_FUNCTION

REM Obligatory enumeration delay:
DELAY 2000

openTerminal()

REM While loop to run createFile() function 20 times to create 20 files as defined there-in
VAR $NUM_OF_FILES = 20
WHILE ( $NUM_OF_FILES > 0 )
	createFile()
    $NUM_OF_FILES = ( $NUM_OF_FILES - 1 )
	DELAY 100
END_WHILE
```

Could not use `RANDOM_CHAR` as PowerShell does not allow the use of `&` in strings without special escaping.