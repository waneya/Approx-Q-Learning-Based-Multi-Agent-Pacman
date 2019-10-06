# AI Method 1 - Approximate Q-Learning

Your notes about this part of the project, including acknowledgement, comments, strengths and limitations, etc.

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

[Back to top](#table-of-contents)

### Application  
We implemented [number] features for our offensive, and [number] features for our defensive agent. Each feature was normalised between [0,1] and was scaled by the learnt weight vector. Thus, each Q(s,a) was estimated by a linear sum of each feature and weight. 

## Reward Shaping
We recognised early on that the reward would primarily occur late in the game, sometimes only at the terminal state. To expedite the learning process we modified the reward function. For our offensive agent, the reward was `(1 - (foodLeft/self.startFood)) +  self.getScore(gameState)`
[Back to top](#table-of-contents)

### Trade-offs  
#### *Advantages*  


#### *Disadvantages*

[Back to top](#table-of-contents)

### Future improvements  

[Back to top](#table-of-contents)



[Previous Page](/2_0_design_choices) | [Next Page](/2_2_approach)