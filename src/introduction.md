# Introduction

## What is SuperChessEngine?
<img src = "https://user-images.githubusercontent.com/62668186/159037002-b996e609-3888-44b9-b70d-8e2c82b99228.jpg" width="300px" height="350px" />

SuperChessEngine is a chess engine inspired by AlphaZero developed by Google, which was able to defeat the famous Stockfish engine with only 4 hours of training.

It has better evaluation function for a given chess position by removing hard-coded values in the Static Evaluator in the current chess engine. It also tries to reduce the number of unnecessary positions being searched by using intuition based move
ordering.

[Github code Repository](https://github.com/superchessengine/sce)

## Why SuperChessEngine ?

SuperChessEngine replaces two major components of existing chess engines.
1. sorting of moves using machine learning.
2. static board evaluation using machine learning.

## Aim

SuperChessEngine aims to:

1. reduce search time in calculating the next move.
2. improve the static evaluator by using deep learning.
3. build and train a deep neural network that scores a given position.
4. build and train a deep neural network that gives probable good moves in a given position without looking ahead.

## Structure

Following diagram depicts simple structure of SuperChessEngine:

![EngineStructure](https://user-images.githubusercontent.com/62668186/159009943-f3e57e83-b61a-42ba-9c50-8e501f4826aa.png)



## Features

- SuperChessEngine is a UCI compliant chess engine, which on given a position evaluates it on certain depth or for a given time and then returns all the evaluated moves with their respective score.
- Being UCI compliant enables it to be used by any chess GUI program as a chess engine. 
- SuperChessEngine is also uploaded as a chess [bot](https://lichess.org/@/SuperChessEngineV1) on [Lichess](https://lichess.org/).

![working](https://user-images.githubusercontent.com/62668186/159010136-520cb265-9760-4749-830f-bab81ec1712f.png)

