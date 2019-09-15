# Design Choices

1. Heuristic Search Algorithms (using general or pacman specific heuristic functions) 
2. Classsical Planning (PDDL and calling a classical planner, see subsection below) 
3. Policy iteration or Value Iteration (Model-Based MDP)
4. Monte Carlo Tree Search or UCT (Model-Free MDP)
5. Reinforcement Learning – classical, approximate or deep Q-learning (Model-Free MDP) 
6. Goal Recognition techniques (to infer intentions of opponents)
7. Game Theoretic Methods

## General Comments

_General comments about the project goes here_

## Comments per topic

## Offense

| Consideration | Function                   |
| ------------- | -------------------------- |
| Eating food   | getFood(self, gameState)   |
| Find capsules | getCapsules(self, gameState)|

## Defense

| Consideration | Function                                  |
| ------------- | ----------------------------------------- |
| Defending food| getFoodYouAreDefending(self, gameSate)    |

## General

| Consideration | Function                                  |
| ------------- | ----------------------------------------- |
| Find opponents| getOpponents(self, gameState)             |
| Find team     | getTeam(self, gameState)                  |
| Overall score | getScore(self, gameState)                 |
| Distance b/w objects | getMazeDistance(self, pos1, pos2)  |
| Get belief on opponents | displayDistributionsOverPositions |



[Back Home](/home) | [Next Home](/2_1_approach)