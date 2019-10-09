# AI Method 1 - Approximate Q-Learning

# Table of Contents
- [Governing Strategy Tree](#governing-strategy-tree)
  * [Motivation](#motivation)
  * [Application](#application)
  * [Trade-offs](#trade-offs)     
     - [Advantages](#advantages)
     - [Disadvantages](#disadvantages)
  * [Future improvements](#future-improvements)

## Governing Strategy Tree  

### Motivation  
In order to eliminate the need for a large Q-Table, and scale our solution, we implemented an approximate Q-Function. Weights were derived using reinforcement Q-Learning. Doing so enabled us to reasonably estimate Q(s,a) for states we had not seen before. 

Our initial thoughts were to use a neural network to approximate the Q-Value (deep Q networks), however we deemed that the time frame of the project bounded our ability to fully implement this methodology. As an alternative, we opted for the aforementioned approach. 

[Back to top](#table-of-contents)

### Application  
We implemented [number] features for our offensive, and [number] features for our defensive agent. Each feature was normalised between [0,1] and was scaled by the learnt weight vector. Thus, each Q(s,a) was estimated by a linear sum of each feature and weight. 

#### Reward Shaping
We recognised early on that the reward would primarily occur late in the game, sometimes only at the terminal state. To expedite the learning process we modified the reward function. For our offensive agent, the reward was:
`(1 - (foodLeft/self.startFood)) +  self.getScore(gameState)`

Whereas for the defensive, it was:
`agentsEaten`.

We believed these heuristics best represented the future reward as the score is primarily a function of the number of food eaten (then retrieved). 

#### Weight Vector Initialisation
Instead of initialising with a zero weight vector, we used judgement to create initialised values that we believed represented each features importance. This allowed the reinforcement learning to reach optimisation significantly faster. 

#### Training
``` python
# Hyperparameters
self.gamma = 0.99     
self.alpha = 0.15

# Epsilon greedy parameters
self.epsilonStart = 1.0 
self.epsilonMin = 0.01  
self.epsilonStep = (self.epsilonStart-self.epsilonMin)/self.trainEps
```
[Back to top](#table-of-contents)

### Trade-offs  
#### *Benefits*  
- Reduce size of state space to [Features x Actions]
- Apply heuristics (features) that we believed would lead to a successful agent
- Faster convergence than a Deep-Q learning approach

#### *Challenges*
- With this approach, we have to define features based on our understanding of the problem domain. This introduces a risk that we do not specify appropriate features and information about the state space is lost to the learning agent
- Due to the sparsity of rewards, we had to introduce a heuristics for rewards. Although close to `getScore`, our approximation is not an exact representation of the actual reward. As a result, a learning agent may learn sub-optimal moves. The trade-off is deemed appropriate given the significant time step between each action and reward.

[Back to top](#table-of-contents)

### Future improvements  
A possible future implementation would combine the learning process amongst both agents. Currently, each agent acts (and learns) independently towards their specific objective - capture food or eat enemies. An improved solution would generalise the approach to a multi-agent solution in order for them to work as a team.

[Back to top](#table-of-contents)



[Previous Page](/2_0_design_choices) | [Next Page](/2_2_approach)