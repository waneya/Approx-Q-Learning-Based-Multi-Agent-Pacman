# AI Method 2 - Heuristic search algorithms

There are certain features utilised within the approximate Q-learning approach that would require costly search calculations to achieve a true value representation. And so, heuristic functions must be used to approximate values. However this must be done carefully as ill-defined (i.e. unadmissible) heuristics in this pacman game could lead to sub-optimal and adverse agent actions taken, as features would be estimated improperly.

In the case of 

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


[Back to top](#table-of-contents)

### The heuristics utilised or explored

***Maze distance:*** 

***Manhattan distance:***

***Noisy distance:***

The problem: when should an agent return home after eating food? A heuristic to minimise chance of getting eaten but also maximise score over the entire game

The mechanism: sqrt(height*width) map < maze distance to food 

Second mechanism: If there is a lot of food nearby (i.e. connected by 1 square), go back home after eating half of total food

[Back to top](#table-of-contents)

### Trade-offs  
#### *Benefits*  


#### *Challenges*

[Back to top](#table-of-contents)

### Future improvements  

[Back to top](#table-of-contents)



[Previous Page](/2_1_approach) | [Next Page](/2_3_approach)