# 8 Transposition Table

Problem: When using Iterative Deepening, we will encounter the same states very often. Not only because we start searching from the root again, but also because many combinations of moves can bring the board to the same state.

Solution: Caching

## 8.1 What do we cache?
- A Hash-Key that represents the current State of the Game
- The depth with which the information has been analyzed
- The score of the node

## 8.2 What do we use the information for?

The Hash-Key is used to identify and recognize the State. It is needed in order to recognize the state when it is encountered and see that it has been analyzed already.

The depth is used to recognize, how accurately the state has been analyzed before. It is used to determine, whether this is a node that's worth to analyze in more detail now.

The score is the important value that's being cached.

## 8.3 Cache-Size

Caching every possible state will very quickly fill the RAM, so it needs to be determined, what states are more worth caching that others.

States with a very high or very low score and large depth ar ideal:
- they save a lot of computing power (depth)
- they provide a very meaningful value

# 9 Alpha-Beta-Pruning

Idea: If we find out that for two choices A and B, the Opponent has each two choices AA, AB and BA, BB.

Then, if we find out that AA and AB give the opponent -3 and +3 points respectively.

Then, if BA gives the opponent +4 points already, then there is no point in calculating what score BB would yield in.

The opponent is expected to maximize his play and therefore end up with +3 points if we chose A or **at least** +4 points if we choose B.

We can therefore skip the calculation of BB.

=> This is called Alpha-Beta-Pruning.

Technique:
- fully evaluate first branch
- keep track of the minimax and the maximin.
- skip whatever second choices not worth evaluating

```
function alphabeta(node, depth, α, β, maximizingPlayer) is
    if depth = 0 or node is a terminal node then
        return the heuristic value of node
    if maximizingPlayer then
        value := −∞
        for each child of node do
            value := max(value, alphabeta(child, depth − 1, α, β, FALSE))
            if value ≥ β then
                break (* β cutoff *)
            α := max(α, value)
        return value
    else
        value := +∞
        for each child of node do
            value := min(value, alphabeta(child, depth − 1, α, β, TRUE))
            if value ≤ α then
                break (* α cutoff *)
            β := min(β, value)
        return value
    end if
end function
```

```
(* Initial call *)
alphabeta(origin, depth, −∞, +∞, TRUE)
```

<img src="https://media.geeksforgeeks.org/wp-content/uploads/MIN_MAX1.jpg">

