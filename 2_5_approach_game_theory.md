## Game Theory

- Check lines ~1440+

Dominant strategy of fleeing enemy if enemy is within 2 steps

Other dominated / dominant strategies and game theory tables

As this is a game with 2 agents on each team, and we defined offensive and defensive agents, a reasonable questions arises of how to set the agents' behaviour, e.g. should we have:
*  1 defensive & 1 offensive
* 2 defensive
* 2 offensive

First we will consider the beginning of a game from a game theory perspective, whereby our decision consists of 1 move at the beginning, of whether to take one of the three actions above. Then, the case of our score being >0 and <0 will be considered, i.e. if we are winning or losing, respectively, at a given point in time. The motivation for doing this is to consider whether it would be attractive to consider switching strategies within a game as scores differ.

Please note, our team's possible actions are represented by the first column, and payoff as the first item in each cell in  the inner cells. And vice-versa for the opposing team in consideration. And note that '?' will represent the outcome of a loss/tie/win, for ease of visual representation.


# Score = 0; start of game initialisation

| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | tie, tie | tie/loss, tie/win| tie/loss, tie/win|
| **1O & 1D** | tie/win, tie/loss | ?, ?| ?, ?| 
|**2O**| tie/win, tie/loss| ?, ?| ?, ? | 

Assuming equal probabilities of each outcome occurring, which is not necessarily the case, but is nonetheless simplified for a form of comparison:

* E(payoff | loss) = 0
* E(payoff | tie) = 1
* E(payoff | win) = 3
* E(payoff | tie/loss) = 1/2(1+3) = 0.5
* E(payoff | tie/win) = 1/2(1+3) = 2
* E(payoff | loss/tie/win) = 1/3(0+1+3) = 4/3 = approx. 1.33

| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | 1, 1| 0.5, 2| 0.5, 2|
| **1O & 1D** | 2, 0.5 | 1.33, 1.33| 1.33, 1.33| 
|**2O**| 2, 0.5| 1.33, 1.33| 1.33, 1.33| 


# Score > 0; time not considered


| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | win, loss| ?, ?| ?, ?|
| **1O & 1D** | win, loss | ?, ?| ?, ?| 
|**2O**| win, loss | ?, ?| ?, ? | 

# Score < 0; time not considered

| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | loss, win | loss, win| loss, win |
| **1O & 1D** | ?, ? | ?, ?| ?, ?| 
|**2O**| ?, ? | ?, ?| ?, ? | 

