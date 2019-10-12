# Approach 2: Heuristic search algorithms

There are certain features utilised within the approximate Q-learning approach that require costly search calculations to achieve a true value representation. And so, heuristic functions must be used to approximate values. However this must be done carefully as ill-defined (i.e. inadmissible) heuristics could lead to sub-optimal and adverse agent actions taken, as features would be estimated improperly.

### Motivation  

### The heuristics utilised or explored

***Maze distance:*** 

***Manhattan distance:***

***Noisy distance:***

The problem: when should an agent return home after eating food? A heuristic to minimise chance of getting eaten but also maximise score over the entire game

The mechanism: sqrt(height*width) map < maze distance to food 

Second mechanism: If there is a lot of food nearby (i.e. connected by 1 square), go back home after eating half of total food


### Trade-offs  
#### *Benefits*  


#### *Challenges*


### Future improvements  



[Previous Page](/2_1_approach) | [Next Page](/2_3_approach)