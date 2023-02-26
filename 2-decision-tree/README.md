# 4 Decision Trees

In this course, we're not planning to do a deep-dive into AIs, though, but instead we want to look at one kind of problem and the solution to it.

## 4.1 Restrictions
- Zero-Sum
- Perfect Knowledge
- Deterministic

e.g. Chess, Tic-Tac-Toe, NIM, Checkers

## 4.2 Approach

Let's imagine the following state of a Tic-Tac-Toe Game:

|O|O|X|
|-|-|-|
| |X| |
|O|X| |

What's the next bext move?

We could start by looking at all three possible moves and then look at the state:

Option 1:
|O|O|X|
|-|-|-|
|X|X| |
|O|X| |

Option 2:
|O|O|X|
|-|-|-|
| |X|X|
|O|X| |

Option 3:
|O|O|X|
|-|-|-|
| |X| |
|O|X|X|

- What's the best move?
- How did you come up with that?
- But what about this state?

|-|-|-|
|-|-|-|
|-|X|O|
|-|-|-|

We need to start looking further down the possible moves:

<img src="https://www.ocf.berkeley.edu/~yosenl/extras/alphabeta/alphabeta.jpg">


The possible moves in a Game form a Tree. The leaves of the tree are terminal Game States in which either player has won.

We can use Pathfinding in this Tree! Start-Node: Current State. Target-Node: Any Node in which the player has won.

- This will yield us the shortest route to Victory
- Works perfectly in Single-Player Games
