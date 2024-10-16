
This Java code implements a graphical Tic-Tac-Toe game using the Swing framework from the Java AWT (Abstract Window Toolkit). Here's a detailed explanation:

Class Structure
TicTacToe Class: Represents the Tic-Tac-Toe game. It contains fields, constructor, and methods for setting up the game and handling game logic.
Attributes (Fields)
Board Dimensions:

boardWidth = 600: The width of the game window.
boardHeight = 650: The height of the game window (50px extra for the text panel).
Swing Components:

JFrame frame: The main window frame of the game.
JLabel textLabel: Displays the status of the game (e.g., player's turn, winner).
JPanel textPanel: A panel that holds the textLabel at the top.
JPanel boardPanel: Holds the Tic-Tac-Toe board, which is made up of buttons arranged in a 3x3 grid.
Game Logic Components:

JButton[][] board: A 2D array of buttons representing the Tic-Tac-Toe board's 3 rows and 3 columns.
String playerX = "X", String playerO = "O": Strings representing player X and player O.
String currentPlayer: Keeps track of whose turn it is, starting with player X.
boolean gameOver = false: A flag to indicate if the game is over.
int turns = 0: A counter to track the number of turns taken.
Constructor (TicTacToe)
Frame Setup:

The JFrame window is created and set to a fixed size (600x650). The layout is BorderLayout, and the frame is set to close on clicking the 'X' button (JFrame.EXIT_ON_CLOSE).
Text Label:

The textLabel displays "Tic-Tac-Toe" at the top of the window in large, bold white text on a dark gray background.
Board Panel:

A GridLayout with 3 rows and 3 columns is used to organize the 9 buttons (JButton) in a 3x3 grid. Each button has a default font size of 120 to fit the large "X" or "O" marks.
Button Setup:

The buttons are initialized with an empty label and are assigned an ActionListener to handle clicks. When clicked:
The button displays the current player's symbol ("X" or "O").
The number of turns increments.
The method checkWinner() is called to see if there is a winner or if the game should continue.
Game Logic
ActionListener for Button Clicks
Each button is set to respond to clicks using addActionListener. When a player clicks an empty tile:
The tile displays the current player's symbol (currentPlayer).
After each click, the program checks for a winner using the checkWinner() method.
If no winner is found, it switches the currentPlayer to the other player.
checkWinner() Method
This method checks for winning conditions after every move:

Horizontal Check: It checks each row to see if all three buttons have the same text (X or O).
Vertical Check: It checks each column for the same condition.
Diagonal and Anti-Diagonal Check: It checks both the main diagonal and anti-diagonal for matching symbols.
If any of these conditions are met, the setWinner() method is called to mark the winning tiles in green and declare the winner.
If there is no winner after 9 turns, the game ends in a tie, and the setTie() method highlights the board in orange.

setWinner(JButton tile):
Changes the tile’s text color to green and the background color to gray.
Updates the textLabel to display the winning player.
setTie(JButton tile):
Changes the tile’s text color to orange and the background color to gray.
Updates the textLabel to display "Tie!".
Overall Flow:
Game Start: The game window appears with a blank board and "Tic-Tac-Toe" at the top.
Gameplay:
Players take turns clicking empty tiles. "X" and "O" alternate between turns.
After each move, the game checks for a winner or a tie.
Game Over:
If there is a winner, the game highlights the winning combination and displays a winning message.
If the game ends in a tie, all tiles are highlighted, and the label shows "Tie!".
This implementation creates an interactive Tic-Tac-Toe game with a simple, elegant design and clean game logic.
