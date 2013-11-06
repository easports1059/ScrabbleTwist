ScrabbleTwist
=============

A mix between Scrabble and Boggle.

Written in Java 7.

Uses [Oracle's dictionary](http://docs.oracle.com/javase/tutorial/collections/interfaces/examples/dictionary.txt) for word checking.

#Report
##Goals
#####Create method of interacting with letters and getting how many of them there are and how much they are worth.
######Method:
- Separate dictionaries for the count of the letters and the letter point values.

######Problems:
- 

<br>

#####Select letters randomly and place them in a "hand" for the player
###### Method:
- ArrayList for letters in hand.

######Problems:
- Letters not properly biased by their number of occurences when drawing directly from dictionary.
	- __Solution:__ Placed letters, in appropriate numbers, in a new list, which was then randomly picked from.

<br>

#####Accept user input of words and immediately check if they are made of the available letters.
######Method:

######Problems:
- At first we thought we would have to stop the user exactly at 30s, which was much more of a challenge, but actually we didn't.

<br>

#####Get Oracle's dictionary in some usable form to check the inputted words against.
######Method:
- Auto-download dictionary.txt file from Oracle.
- Iterate through file with a scanner, checking each line if it is the same as the word given..

######Problems:
- 

<br>

##Functions
####getDictionary()
_Prepares Oracle's dictionary for being used._

1. Tests if the dictionary is already in the same directory as the program (from previous runs).
2. If not, it downloads the dictionary and writes it to dictionary.txt in the program's directory. [(Source)](http://stackoverflow.com/a/921408)
	- Uses BufferedInputStream and FileOutputStream to download.
_Input_ None
_Output_ None

####inputSession()
_Opens and manages user input session._

1. Creates ArrayList for user input to continuously be added to.
2. Continuous loop of user input and input testing for 30 seconds. [(Source)](http://stackoverflow.com/a/2550814)
_Input_ None
_Output_ int

####correctLetter()
_Checks if inputted word used the letters available and hadn't been inputted before_

####countScore()
_Takes userInput list and calculates the player's score._

1. Iterates through words in userInput list, and then the individual characters of each word, and counts up the scores.
_Input_ List < String >
_Output_ int

####findInDictionary()
_Searches Oracle's dictionary for the word provided._

1. Create dictionary scanner. If fails, then it fetches the dictionary from the web.
2. Scans the file, looking for the given word, and returns true if found. Otherwise, returns false.
_Input_ String
_Output_ boolean


##Global Variables