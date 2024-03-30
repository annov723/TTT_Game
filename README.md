
# **TTTGame** <img align="right" img src="https://github.com/annov723/TTTGame/blob/master/TicTacToeGame/icon.png" width=25% height=25%>

The project is based on the game of Tic Tac Toe, contains 2 game options - the classic one and 9 in 1 variation:
- user-friendly interface built with Java Swing
- HashMap to store players' nicknames and scores, all the data saved in a dat.txt file
- single and two-player modes with 3 difficulty levels.

It is my first java project fully written by me. I'm pretty proud despite *of course* it is not perfect ;)

## Main objectives:
- to create a game, using Java Swing graphics library
- to use file handling, all nicknames and scores are saved in a dat.txt file and updated everytime the user plays
- to broad my Java knowledge without starting from basics.


### *9 in 1 Tic-tac-toe variation*

The board is divided into 9 "big" squares, each of them divided into 9 "small" squares. In every "big" square there is a Tic-tac-toe game. The "small" square where the first player's mark is put defines in which "big" square the second player has to make their move and so on. When someone wins the "big" square it the big mark is put there and this square is out of the game. The goal of the game is to have the line with the "big" squares' marks. When during the game someone picks the "small" square which is connected with the already ended "big" square, the square for the next move is picked randomly. Of course there is still possible that the game ends in a draw.


## Description:
1. First window - the login window (Login class), where user can pick their in-game name and confirm their choice by clicking the button:
- if the chosen nick is used the first time in the game, it is added to the dat.txt and the starting number of points equals to 0
- if the chosen nick exists in the dat.txt file, points gained in the current session are added to the points collected by this player before
- implements ActionListener (to open the menu window when button is pressed)
- implements MouseListener (when the mouse enters the button its colors invert)
- Java Swing components: JFrame, JButton, JTextField, JLabel, ImageIcon to build the window
- there are some rules the nickname should fit in - cannot be longer than 20 characters and cannot contain ":" character (it is used in the dat.txt to separate the data)
- the user has to put in the correct nickname, otherwise they aren't allowed to open the menu.
2. Data class - opens dat.txt file if it already exists or creates a new one:
- using HashMap to store the nicknames and scores data
- when the game is closed correctly (by pressing the exit button) all the points collected are added to the dat.txt next to the player's nickname, separated with ":"
- dat.txt is being overwritten.
3. Menu class:
- implements ActionListener (to start the game, open ranking or exit when button is pressed)
- implements MouseListener (when the mouse enters the button its colors invert)
- Java Swing components: JFrame, JButton, JLabel arrays, ImageIcon arrays to build the window
- exit button -> calls data to file saving method and closes program
- ranking button -> opens ranking with nicknames and scores sorted in descending order, there is a back button to get back to the menu
### classic game button
-  user has to choose from 2 modes: single and two player
-  if the single mode is chosenuser picks the difficulty level (easy, medium, hard)
-  two player mode:
      * it is the simple Tic-tac-toe game where the marks are picked randomly, the same as who starts the game
      * points aren't counted
      * at the end the winner is announced or the information about the draw and the user can go back to the main menu by clicking the proper button
      * during the game it is possible to go back to the menu by clicking back button, when button is clicked the dialog box is shown to avoid the user that the progress in game will not be saved so they can rethink if they really want to go back to the menu
- single player mode:
   * it is the simple Tic-tac-toe game where the marks are picked randomly, the same as who starts the game
   * playing against the computer
   * points are counted - 10 for easy, 20 for medium and 50 for winning the hard level
   * at the end the winner is announced or the information about the draw and the user can go back to the main menu by clicking the proper button
   * during the game it is possible to go back to the menu by clicking back button, when button is clicked the dialog box is shown to avoid the user that the progress in game will not be saved so they can rethink if they really want to go back to the menu
   * in the easy level the computer's moves are chosen fully randomly
   * in the hard level the computer's moves are generated by: first checking if there is a possibility of winning for the computer, second how to stop the player from winning, third option is to try to build a line  by putting the mark next to the computer's another and the last option is to just picked randomly because there is no smart move in the round
   * in the medium level it is randomly chosen if the computer's moves should begenerated by easy level or hard level methods
### 9 in 1 game button
-  user has to choose from 2 modes: single and two player
-  if the single mode is chosen, user picks the difficulty level (easy, medium, hard)
-  two player mode:
    * it is the 9 in 1 Tic-tac-toe game variation where the marks are picked randomly, the same as who starts the game
    * points aren't counted
    * at the end the winner is announced or the information about the draw and the user can go back to the main menu by clicking the proper button
    * during the game it is possible to go back to the menu by clicking back button, when button is clicked the dialog box is shown to avoid the user that the progress in game will not be saved so they can rethink if they really want to go back to the menu
- single player mode:
   * it is the 9 in 1 Tic-tac-toe game variation where the marks are picked randomly, the same as who starts the game
   * playing against the computer
   * points are counted - 10 for easy, 20 for medium and 50 for winning the hard level, what is more for winning every "big" square the point are added too (2 in easy, 5 in medium and 8 in hard level)
   * score counter is changed constantly during the game
   * at the end the winner is announced or the information about the draw and the user can go back to the main menu by clicking the proper button
   * during the game it is possible to go back to the menu by clicking back button, when button is clicked the dialog box is shown to avoid the user that the progress in game will not be saved so they can rethink if they really want to go back to the menu
   * in the easy level the computer's moves are chosen fully randomly, based on the situation in the exact "big" square the the move has to be done
   * in the hard level the computer's moves are generated by: first checking if there is a possibility of winning for the computer, second how to stop the player from winning, third option is to try to build a line  by putting the mark next to the computer's another and the last option is to just picked randomly because there is no smart move in the round, based on the situation in the exact "big" square the the move has to be done
   * in the medium level it is randomly chosen if the computer's moves should begenerated by easy level or hard level methods, based on the situation in the exact "big" square the the move has to be done
   * during the game the "big" square there the move should take place has different background than the other ones
   * after every move the requirements are checked to make sure that any "big" square or the whole game is not won.

## Solutions I am proud of:
- adding the buttons' colors invertion when mouse enters them
- personalized buttons which aren't focusable and don't have any weird, old-fashioned borders
- clearly made, user-friendly interface with self-designed appearance
- refreshing system to have the ranking frame up-to-date after every game
- the idea how to code the 9 in 1 game and it's correct implementation
- making pretty good hard level method
- begin() function that picked who starts the game and with which mark
- using a lot of code from classic game to build the 9 in 1 option, so it wasn't so time consuming to finish the 9 in 1 game.

## Things to work on:
- of course, the game is not perfect starting from the appearance design, ending of its functionality, but the project is working well, it is finished and abled to be used
- the difficulty levels in 9 in 1 single player mode -> the computer should focus not only on the exact "big" square it is currently at but should think about the whole game board
- develop the appearance of the app
- maybe add some animations like confetti when the winner is announced
- animated game logo in the menu (can pop up when the menu is opening
- allow users to pick the color of their X and O?
- I'm sure the code can be optimalized somehow but for now my algorithmic and Java knowledge is to small to propose any suggestions
- make an online version to play with people from all over the world :)
