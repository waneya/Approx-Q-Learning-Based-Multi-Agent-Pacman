## Game Theory

As this is a game with 2 agents on each team, and we defined offensive and defensive agents, a reasonable questions arises of how to set the agents' behaviour, e.g. should we have:
*  1 defensive & 1 offensive
* 2 defensive
* 2 offensive

First we will consider the beginning of a game from a game theory perspective, whereby our decision consists of 1 move at the beginning, of whether to take one of the three actions above. Then, the case of our score being >0 and <0 will be considered, i.e. if we are winning or losing, respectively, at a given point in time. The motivation for doing this is to consider whether it would be attractive to consider switching strategies within a game as scores differ.

Please note, our team's possible actions are represented by the first column, and payoff as the first item in each cell in  the inner cells. And vice-versa for the opposing team in consideration. And note that '?' will represent the outcome of a loss/tie/win, for ease of visual representation.


# Score = 0; at any given point in time in the game

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

Under the set of assumptions made, this shows that a pure 2D strategy is dominated, and therefore when score = 0, agents should either be set to 1O & 1D, or 2O to maximise expected future payoffs.

# Score > 0; at any given point in time in the game


| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | win, loss| ?, ?| ?, ?|
| **1O & 1D** | win, loss | ?, ?| ?, ?| 
|**2O**| win, loss | ?, ?| ?, ? | 

**Estimated expected numerical payoffs of the above table:**

| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | 3, 0| 1.33, 1.33| 1.33, 1.33|
| **1O & 1D** | 3, 0| 1.33, 1.33| 1.33, 1.33| 
|**2O**| 3, 0| 1.33, 1.33| 1.33, 1.33 | 

By observing this table, it can be seen that having 2 defensive agents when score = 0 is a dominated strategy. So it is then beneficial to either have 1O & 1D or 2O in order to maximise expected payoff. This relies on the fact that the outcomes are assumed to be of equal probability, however this is not always the case, and is a limitation of this approach.

# Score < 0; at any given point in time in the game

| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | loss, win | loss, win| loss, win |
| **1O & 1D** | ?, ? | ?, ?| ?, ?| 
|**2O**| ?, ? | ?, ?| ?, ? | 

**Estimated expected numerical payoffs of the above table:**

| | **2D** | **1O & 1D**| **2O**|
| ---- | ----| ---- | --- |
| **2D** | 0, 3|0, 3| 0, 3|
| **1O & 1D** | 1.33, 1.33| 1.33, 1.33| 1.33, 1.33| 
|**2O**| 1.33, 1.33| 1.33, 1.33| 1.33, 1.33 |

This forms the inverse of the previous Score > 0, where now our team is losing. It is therefore a dominated strategy to have 2 purely defensive agents once we are losing in score at any given point in time.  This is because the expected payoff of maintaining this strategy is 0 in all action cases of the opposing team. Implementation-wise, what this means, is that if our agents observe that we are losing in score, to maximise payoff, it is advantageous for then to either have 1O & 1D or 2O agent behaviours set. Intuitively this makes sense since there is no possible way to get a better outcome if the agents remain on a defensive position once our team is already losing.

Challenges:
*  Although it is simple enough, for example, to understand that having 2D is dominated once we are losing, it is a difficult question to then ask which strategy should be taken in cases where 1O & 1D or 2O seem to have the same expected payoff. 
*  We did attempt to test the combinations of agent offensiveness/defensiveness manually through empirical observation of results and replays, however it would be preferable given more time to have a systematic approach for learning and generalisation.
*  It is difficult to map agent behaviours as purely offensive or defensive, because for example, an agent that is offensive that is making its way to the enemy territory could stumble upon an offensive enemy agent who is in close range - and then a decision question arises of whether to perhaps maximise payoffs by attempting to eat them then return to attempting to eat food, or to just ignore them and prioritise food. This can be observed conversely by defensive agents, e.g. eating close-by food to the border.
*  Another approximate method for utilising this type of game theory is to consider time and its impact on the payoffs. E.g. when time is almost up, and we are losing, it may be more beneficial to attempt to forego all defense, and set the agents to 2O. This applies inversely to setting to 2D if we are winning by a large margin when the game is almost finished in time.

Possible improvements:
*  To extend this game theory model and to make it robust, it would be beneficial to find a way to calculate the probable likelihood of each outcome (loss, tie, win) when there are multiple possibilities in a given situation (e.g. tie/win). This would allow for a more accurate measure of expected payoff, although this game of pacman has many turns and such probabilities will differ in each of the very high number of possible states - so this must be approached carefully.
* Empirically testing or utilising Q-learning may work well to be able to implicitly calculate these probabilities, however a wide range of samples and opposing team agents should be tested to ensure good generalisation.
* A parameter upon which these game theory tables could be adjusted to is the range of score, e.g. if score = 10, it is less probable that the score will reach 0 than if the score = 100.
* Another possible dimension to consider as an extension, is that depending on how much food of the opposing enemy has, or our team has, it is rational to then increase or decrease the expected payoff for each strategy taken. For example, if the enemy only has 3 food left in their territory, then it may be more attractive to then set 2O agents on our team, since we would only need to eat 1 pellet to win. However, this is only a constraint example, because we may also have only 3 food pellets left!


