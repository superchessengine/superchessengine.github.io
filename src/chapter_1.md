# Chapter 1

## Alphabeta pruning

Only having minimax algorithm was not enough. So we have pruned the nodes which are guaranteed to give worse score then current best move using Alpha-beta pruning. Hence, the unwanted branches of the search tree was eliminated.

This way, we limited the search time to the more promising subtree and performed the deeper search in the same time.

## Move Ordering

Alpha-beta algorithm was performing well, but there were cases when the best move used to occur at the deepest node. That's where we thought nodes should be ordered such best nodes are checked first. 

Using intution based move ordering, SuperChessEngine tries to reduce the unnecessary positions being searched. 