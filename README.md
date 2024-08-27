# AIGobbletGame

**Chosen Programming language:**

![image](https://github.com/user-attachments/assets/1d5891a6-6bc5-4580-a7e0-4155a3fa2542)



**Chosen Framework:**

Java Swing

**User manual and features:**

To use the application, simply open the provided exe file:

![image](https://github.com/user-attachments/assets/96cc977c-f5a2-45d9-9760-bbca887a8eb2)



Then when faced with the interface, choose an option from the many options provided and then press the play icon

![image](https://github.com/user-attachments/assets/e8559f08-da22-4cec-9417-8e5918f3fd17)



CPU represents the computer or the ai we are playing against, where there are 3 difficulties varying from easy (easily beaten) to medium (a fair challenge) to hard (almost impossible to beat)

Where the player option represents human player where us -humans- take control and try to beat an ai or another human player

Let's take Human vs Human for an example to illustrate some game features!

![image](https://github.com/user-attachments/assets/819486e0-656c-4eae-b570-ac41d686f1f3)


After we press the play icon, the pieces we use appear, whereby default the white always starts playing first as in chess.

In order to select a piece, click on it with the mouse, and it should appear on the top right corner indicating that it has been chosen and revealing the piece underneath it:

![image](https://github.com/user-attachments/assets/0025a7f9-703a-4f8d-83d4-56f224ed375b)



And in order to play it, simply click anywhere on the board.

After that, the status in the right bottom corner changes indicating that it's black's turn to play.

![image](https://github.com/user-attachments/assets/a43fb9f6-7b8f-49b9-b067-29668088288c)



All the game rules were considered when the application was made and any attempt to violate it, causes a notification message to appear the bottom left of the GUI and rejects the move,

For example, if we tried to cover a larger piece that ours this is what we would be shown:

![image](https://github.com/user-attachments/assets/1c42a05a-8841-47f8-8948-15c22873ea3a)


Now let's also see what happens when a player wins by achieving 4 connected pieces:

![image](https://github.com/user-attachments/assets/0e3c11d9-1bef-46c8-b98a-730c97a06f98)



The notifier and status bar shows that someone won (white in this case) and all GUI interactions inside the boards are rejected unless the player starts a new game which clears the board and pieces.

The next feature we have is the AI (or CPU) player, before we show gameplay, we will discuss how it was made.

The first step was to make a board tree, the board tree represents all possible moves branching from our current move, and all the moves branching from these moves and so on until it reaches a certain depth.

This was our initial step, but for means of optimizing and eliminating unnecessary options, we used a game heuristic covered in our lectures called"Tapered search", this heuristic in short, sorts board nodes in the tree according to their evaluation (we will discuss the evaluation further on), and then board nodes are given ranks based on their indexing after sorting, where the higher rank nodes are given higher branching, which means more children can result out of this node because, while lower rank nodes are given lower branching, and all according to this function:

![image](https://github.com/user-attachments/assets/fbb59dd4-3cf6-44a9-a024-51333faa12af)



And this concludes our tree, the next step is to know what move we should pick according to the tree, this is done by evaluating every node.

Evaluating nodes takes into account all pieces on board and off board and which turn it is and gives a score which represents how well the player is doing.

Then when all pieces are evaluated, we decide which move to pick by pruning the tree using alpha-beta pruning, which gives us which move we should take in order to achieve victory.

**Difficulty and iterative deepening:**

The last part to cover is difficulty, and what makes the easy CPU easy, or the hard CPU hard, the answer would be: depth.

We used iterative deepening in our algorithm, which in short, decides how much time should a tree spend generating children, and depending on the level of difficulty, we allow the tree to generate more depths, which in turn, gives a further insight into the game which allows CPU to take better decisions.

And now at last, when we try to play against ai, it's the same procedure for human, but instead of a second player making a move, the move is automatically taken by the AI.

Here's an example of a match of a player (White) against a hard AI (Black)

![image](https://github.com/user-attachments/assets/861ed0c9-6af1-40e4-9289-45f961fd8414)

