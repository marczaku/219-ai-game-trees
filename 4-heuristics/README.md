# 6 Iterative Deepening MiniMax

Problem: Many games are insanely complex:

- Tic-Tac-Toe: 19,683
- Poker Hands: 2,598,960
- Rubik's Cube: 10^18
- Checkers: 10^21
- Chess: 10^45

This results in us not being able to calculate all possible moves. Actually, if you were able to turn the whole earth (all 10^50 atoms) into a computer, you might be able to store all possible chess combinations.

=> We need to be able to work with a limited set of possible moves being calculated.

This is called **Iterative Deepening MiniMax** Algorithm.

- Choose a depth to begin your calculations with.
- Run algorithm only until chosen depth.
- (does this remind you of another algorithm?)
- Increase the depth and re-run, if the result is not good enough, yet and there is more time available

```
function minimax(node, depth, maximizingPlayer) is        // CHANGE
    if depth = 0 or node is a terminal node then           // CHANGE
        return the heuristic value of node                 // CHANGE
    if maximizingPlayer then
        value := −∞
        for each child of node do
            value := max(value, minimax(child, depth − 1, FALSE))  // CHANGE
        return value
    else (* minimizing player *)
        value := +∞
        for each child of node do
            value := min(value, minimax(child, depth − 1, TRUE))    // CHANGE
        return value
    end if
end function
```

```
(* Initial call *)
minimax(origin, depth, TRUE)          // CHANGE
```


# 7 Heuristic Functions

Problem:

If we calculate a game like chess with a depth of a few nodes only, we don't know yet who's going to win. We need to evaluate non-terminal leaves by some heuristic. Let's observe this issue by the example of chess:

<img src="https://www.houseofstaunton.com/media/catalog/product/cache/35ece35ec071d185e0970020aa695e66/g/r/grand-eb-6_7.jpg">

## 7.1 Counting Figures

First of all, you could just count the number of pieces on the board. Having more pieces on the board than the opponent is better, right?

## 7.2 Ranking Figures

Then, you can give values to different pieces. This will make sure that we don't think that sacrificing a Queen for two Pawns is a good idea:

|piece|score|
|-----|-----|
|pawn|1|
|knight|3|
|bishop|3|
|rook|5|
|queen|9|
|king|+Infinity|

## 7.3 Other heuristics

Modern algorithms go many steps further and evaluate positions, e.g. by:
- what pieces are *bound* (needed to defend other pieces)
- what pieces are *threatened* (could be taken by an opposing piece)
- how freely movable are pieces (are they locked in or can they roam the whole board)

## 7.4 Conclusion

You will need to find a smart heuristic evaluation of states and the better your heuristic, the better your A.I. will do.
