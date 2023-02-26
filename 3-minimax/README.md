# 5 Minimax Algorithm

Problem: What will the A.I. consider the best play / shortest path to victory in the case of Tic-Tac-Toe?

|X|O| |
|-|-|-|
|X|O| |
|X| | |

Isn't it much more likely, that these Plays will turn out like this?

|X|X|O|
|-|-|-|
|X|O| |
|X|O|X|

The Problem:
- A move that's good for us is bad for the opponent.
- And a move that's good for the opponent is bad for us.
- We need to assume that the opponent makes the best move possible

> The **maximin** value is the highest value that the player can be sure to get without knowing the actions of the other players

- Maximizing the own play, while assuming the Worst-Case Scenario

> The **minimax** value of a player is the smallest value that the other players can force the player to receive, without knowing the player's actions

- Minimizing the opponent's options while assuming their Best-Case Scenario

```
function minimax(node, maximizingPlayer) is
    if node is a terminal node then
        return WIN(1) or DRAW (0) or LOSE(-1) for node
    if maximizingPlayer then
        value := −∞
        for each child of node do
            value := max(value, minimax(child, FALSE))
        return value
    else (* minimizing player *)
        value := +∞
        for each child of node do
            value := min(value, minimax(child, TRUE))
        return value
    end if
end function
```

```
(* Initial call *)
minimax(origin, depth, TRUE)
```

Here's a picture of the algorithm's result assuming that each decision results in a final score for both players:

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/6/6f/Minimax.svg/800px-Minimax.svg.png">

## The Result
When you run above pseudo-code, you'll end up with a number telling you the best score you can achieve, but you won't get the actual best move. This can be fixed:

```
function minimax(node, maximizingPlayer) is
    if node is a terminal node then
        return WIN(1),node or DRAW (0),node or LOSE(-1),node for node
    if maximizingPlayer then
        value := −∞
        child := null
        for each child of node do
            newValue, newChild = minimax(child, FALSE)
            if newValue > value
              value := newValue
              child := newChild
            end if
        return value,child
    else (* minimizing player *)
        value := +∞
        child := null
        for each child of node do
            newValue, newChild = minimax(child, TRUE)
            if newValue <> value
              value := newValue
              child := newChild
            end if
        return value,child
    end if
end function
```

```
(* Initial call *)
score, node = minimax(origin, depth, TRUE)
```

- node is the best next move
- score is the score of that move

## The full Path
Maybe, you even want to see, how the whole game plays out. In that case, you can use a Stack to store all the moves:

```
function minimax(node, maximizingPlayer) is
    if node is a terminal node then
        return WIN(1),stack(node) or DRAW (0),stack(node) or LOSE(-1),stack(node) for node
    if maximizingPlayer then
        value := −∞
        node_stack := null
        for each child of node do
            newValue, new_node_stack = minimax(child, FALSE)
            if newValue > value
              value := newValue
              node_stack := new_node_stack
            end if
        end for
        return value,child
    else (* minimizing player *)
        value := +∞
        node_stack := null
        for each child of node do
            newValue, new_node_stack = minimax(child, TRUE)
            if newValue <> value
              value := newValue
              node_stack := new_node_stack
            end if
        end for
        return value,child
    end if
end function
```

```
(* Initial call *)
score, nodes = minimax(origin, depth, TRUE)
```