### Exercise 9-2
Asks for script to open a text editor, guess a number, then guess that number for all eternity.
#### Work
```DuckyScript
REM Title: Exercise 9-2 from USB Rubber Ducky: Keystroke Injection Attacks with Advanced DuckyScript
REM Author: Patrick Hirsch <HirschP2@nku.edu>
REM Description: In Windows, Duck picks a number, then blindly guesses that number reporting correctness infinitely.

REM Set attackmode as an HID device; leave storage for easy re-arming
ATTACKMODE HID STORAGE

REM Variables
$_RANDOM_MIN = 0
$_RANDOM_MAX = 10
VAR $ducksNumber = 0
VAR $ducksGuess = 0
VAR $timer = 0

REM Open Notepad via Run
FUNCTION openNotepad()
	GUI r
	DELAY 100
	STRING notepad
	ENTER
	DELAY 100
END_FUNCTION

REM Timer printing . each second.
REM Durration specified in seconds via $timer variable
FUNCTION waitTime()
	WHILE ( $timer > 0 )
		STRING .
		DELAY 1000
		$timer = ( $timer - 1 )
	END_WHILE
	ENTER
END_FUNCTION

REM Pick a number for Ducky to guess, saved to $ducksNumber var.
REM Assumes Min and Max have remained unchanged.
FUNCTION pickNumber()
	VAR $ducksNumber = $_RANDOM_INT
END_FUNCTION

REM Guess the number Ducky chose, saved to $ducksGuess var.
REM Assumes Min and Max have remained unchanged.
FUNCTION guessNumber()
	VAR $ducksGuess = $_RANDOM_INT
END_FUNCTION

REM Check equality of $ducksGuess & $ducksNumber and print message accordingly.
FUNCTION checkAnswer()
	IF ( $ducksGuess == $ducksNumber ) THEN
		STRING I guessed correct
	ELSE
		STRING I guessed incorrect
	END_IF
	ENTER
END_FUNCTION

REM ============================================

REM Obligatory enumeration delay:
DELAY 2000

openNotepad()

WHILE TRUE
	pickNumber()
	STRINGLN I'm thinking of a random number between 1 and 10
	$timer = 3
	startTimer()
	guessNumber()
	checkAnswer()
	$timer = 5
	startTimer()
END_WHILE
```
Code works as intended