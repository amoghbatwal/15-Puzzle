# CSCI-B 551 Elements of Artficial Intelligence

### 15-Puzzle

### Problem statement
The goal of the puzzle is to ﬁnd the shortest sequence of moves that restores the canonical conﬁguration given an initial board conﬁguration. You can run the program like this:
./solve_luddy.py [input-board-filename] [variant]
where input-board-filename is a text ﬁle containing a board conﬁguration in a format

### Implementation
We have employed the code using A* search algorithm with heuristic. There are lot of heuristics available to solve puzzle problems of this sort like Manhattan distance, number of misplaced tiles from goal, etc. The state space consists of all the explored states of the board during the heuristic search. The successor function consists of all the valid moves which are possible from the current board state as per the board variant. The edge weights are all one since no move is weighted in the process. The goal state is the board position consisting of numbers 1-15(from first position) in order and 0 in the last position. We have used Manhattan distance due to its efficiency and ease to code. We have also implemented Misplaced tiles heuristic in the same code. The function on line 105 needs to be replaced with the function name- ‘calculate_misplaced_tiles’ to change the heuristic. There is very minute difference in output between the two methods. Misplaced tile heuristic is admissible because it is clear that any tile that is out of place must be moved at least once, whereas Manhattan distance is admissible because all any move can do is move one tile one step closer to the goal. Thus, neither of these overestimates the true solution cost. Also, permutation inversion is implemented to check whether the board is solvable in the first place.

### Search Algorithm working
Manhattan distance calculates the City-block distance/Manhattan distance of each tile from its position in the current board position to its ideal position in the standard board. The cost function (known as f(s)) adds 1 each time (known as path cost) it explored one state corresponding to a chosen state to the Manhattan distance (known as h(s)). The minimum cost function is chosen and explored further until a solution state is reached.
