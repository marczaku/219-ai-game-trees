# 10 Expectiminimax

Variation of Minimax that can handle chances.

```
function expectiminimax(node, depth)
    if node is a terminal node or depth = 0
        return the heuristic value of node
    if the adversary is to play at node
        // Return value of minimum-valued child node
        let α := +∞
        foreach child of node
            α := min(α, expectiminimax(child, depth-1))
    else if we are to play at node
        // Return value of maximum-valued child node
        let α := -∞
        foreach child of node
            α := max(α, expectiminimax(child, depth-1))
    else if random event at node
        // Return weighted average of all child nodes' values
        let α := 0
        foreach child of node
            α := α + (Probability[child] × expectiminimax(child, depth-1))
    return α
```

# 11 Monte Carlo Tree Search

This algorithm has been used by AlphaGo to beat World Class Go Players!

It works with a exploitation-exploration-tradeoff, which means that it balances playing through random moves until the very end of a game and then signaling the win/loss back to its parent nodes, which then update its UCB (Upper Confidence Bounds, how confident are we in the value of this move?) as well as its Score (do we usually win or lose from here?)

The stages are:
- selection (picking the most promising move)
- expansion (if no more nodes can be selected after selection criteria, it expands all possible states from the leaf node)
- simulation (after expansion, we pick a random or a heuristically chosen child node to evaluate the result from here)
- back-propagation (also known as update phase)
