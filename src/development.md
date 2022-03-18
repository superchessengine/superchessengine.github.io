# Development of SuperChessEngine

## Alphabeta pruning

Only having minimax algorithm was not enough. So we have pruned the nodes which are guaranteed to give worse score then current best move using Alpha-beta pruning. Hence, the unwanted branches of the search tree was eliminated.

This way, we limited the search time to the more promising subtree and performed the deeper search in the same time.

## Move Ordering

Alpha-beta algorithm was performing well, but there were cases when the best move used to occur at the deepest node. That's where we thought nodes should be ordered such best nodes are checked first. 

Using intution based move ordering, SuperChessEngine tries to reduce the unnecessary positions being searched. 

Below are some move ordering techniques which we have used:

- ### Killer Heuristic

	It considers moves that caused a beta-cutoff in a sibling node as killer moves and orders them high on the list. Killer moves work on the supposition that most of the moves do not change the situation on the board too much.

	In some cases, killer moves saves a lot amount of time while searching.

- ### Hash moves

	To implement this we first implemented transposition table. In this technique, the move returned from TT was ordered first in the list, infront of all the other moves.
	Hence this hash move is either a best move of a stored PV-node - a PV-move, or a good enough refutation move to cause a cutoff. 

- ### History Heuristic

	This technique is based on number of cutoffs caused by a given move irrespectively from the position in which the move has been made. On a cutoff we incremented a counter in a table, addressed by [piece][to]. Values retrieved from that table are used to order non-capturing moves. This heuristics performs usually better than domain-dependent heuristics.

- ### MVV-LVA Look up

	MVV-LVA stands for Most Valuable Victim - Least Valuable Aggressor. 
	In this, we sort the capture moves in a reasonable order. We first look up the potential victim of all attacked opponent pieces, in the order of the most valuable first. After the most valuable victim is found, the find-aggressor cycle loops over the potential aggressors that may capture the victim in inverse order, from pawn, knight, bishop, rook, queen to king. 

## Transposition Table(TT)

Transpoistion Table comes into role when a position recurs via a different sequence of moves. TT is a database that stores results of previously performed searches. This way we reduced the search space of a chess tree. We took a hash table storing information about positions previously searched, how deeply they were searched, and what we concluded about them. However at some point, it becomes important to clear TT data.

## Bot

After implementing all this, it becomes very important to know how well our engine works. So, nothing could have been better than playing a chess game against the engine which we just built and knowing it's strength. Hence, we deployed our SuperChessEngine bot on [Lichess](https://lichess.org/).

> Now anyone can play against our [bot](https://lichess.org/@/SuperChessEngineV1).
