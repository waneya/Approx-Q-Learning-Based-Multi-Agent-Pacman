## Game Theory

- Check lines ~1440+

Dominant strategy of fleeing enemy if enemy is within 2 steps

Other dominated / dominant strategies and game theory tables

As this is a game with 2 agents on each team, and we defined offensive and defensive agents, a reasonable questions arises of how to set the agents' behaviour, e.g. should we have:
*  1 defensive & 1 offensive
* 2 defensive
* 2 offensive

First we will consider the beginning of a game from a game theory perspective, whereby our decision consists of 1 move at the beginning, of whether to take one of the three actions above. Then, the case of our score being >0 and <0 will be considered, i.e. if we are winning or losing, respectively, at a given point in time. The motivation for doing this is to consider whether it would be attractive to consider switching strategies within a game as scores differ.

# Score = 0; start of game initialisation

| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | tie, tie | tie/loss, tie/win| tie/loss, tie/win|
| **1O & 1D** | tie/win, tie/loss | ?, ?| win/loss, win/loss| 
|**2O**| tie/win, tie/loss| win/loss, win/loss| ?, ? | 

# Score > 0; time not considered

Please note, our team's possible actions are represented by the first column, and payoff as the first item in each cell in  the inner cells.

| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | win, loss| ?, ?| ?, ?|
| **1O & 1D** | win, loss | ?, ?| ?, ?| 
|**2O**| win, loss | ?, ?| ?, ? | 

# Score < 0; time not considered

Please note, our team's possible actions are represented by the first column, and payoff as the first item in each cell in  the inner cells.

| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | loss, win | loss, win| loss, win |
| **1O & 1D** | ?, ? | ?, ?| ?, ?| 
|**2O**| ?, ? | ?, ?| ?, ? | 

