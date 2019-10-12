# Features #

### Offensive features

* deadEndWithActiveGhostNearbyFeature: Avoid entry to dead Tunnels (with no exit) , when enemy is nearby to prevent ending up in dead ends. A demo is given in Heuristic Search Algorithms
* {1-3} stepsFromEnemyAgent1
* {1-3} stepsFromEnemyAgent2
* isSuccessorCloserToChoosenPoint
* closenessToOptimizedFood: optimized food is the food which is not near to enemy (applicable if enemy is visible)
* ActionsAvailableActiveGhostNearbyFeature: When enemy is nearby, this feature will cause offensive agent to prefer
paths with more future actions available, this ensures smooth movement of pacman without causing him to enter in traps. 
* foodEaten
* capsuleEatenWithEnemyNearBy: Pacman will try to eat capsule when enemy is nearby otherwise tries to avoid it as much as possible.

### Defensive features

* becomesPacman
* isSuccessorCloserToChosenPoint
* {1-3} stepsFromEnemyAgent1
* {1-3} stepsFromEnemyAgent2

### Hybrid (reflexive) features

*

***Please note that, for clarity, the agents in the demos will be referenced by their respective colour - i.e. red & orange for the RED team, blue & teal for the BLUE team. Our agents may switch from either team throughout each video, but will be identified under the respective demo.***

***feature name***
*  problem feature is intended to address:
*  Effectiveness of feature in addressing that problem:

## Offensive agent - fleeing from enemy ghost, (and pacman!)

Our agent is the blue offensive agent. Our first attempt at attempting to stop our offensive agent from dying to enemy agents was to add a feature of maze distance to attempt to maximise it from an encountered enemy. 

# Demo

![1_-_offensive_agent_is_ghost__running_from_enemy_pacman](uploads/1462f1ad37b0b188024a0901a88c6272/1_-_offensive_agent_is_ghost__running_from_enemy_pacman.gif)

A pitfall of the first feature is demonstrated here. Our Red offensive while maximizing the distance enters in dead end and get caught by enemy agents. 

![2_-_offensive_agent_staying_in_dead_end](uploads/3ade853f2b9a113095f31b273ac19f4a/2_-_offensive_agent_staying_in_dead_end.gif)



3- Possible solution of 1 by adding future available actions as a feature. This did not worked as expected. We found it difficult to favour paths closer to food or paths with more action.  Resultantly pacman remained confused as to go where. This confusion is clearly eveident in attached replay from 1100-1000 [3_replay-Problem](uploads/91cb0bffcb7f3812888045b7d05c7379/3_replay-Problem)


![4_-_offensive_agent_repeatedly_failing_to_re-enter_in_aims_of_closest_food](uploads/1fc4b3b072d59730c30404a1fd70ea0b/4_-_offensive_agent_repeatedly_failing_to_re-enter_in_aims_of_closest_food.gif)

4- To solve the confusion above , we added one condition. Consider the future distances only when enemy is nearby. After all pacman should (in most cases) avoid dead ends (with or without food) when enemy is nearby. Solving 3 by calculating future value only when opponent is in proximity.
The replay below from between 1200 and 950 it can be clearly seen that pacman is no more confused and it also avoids dead end when enemy is nearby. We only considered a depth of 7 with this feature at that time.[4_replay](uploads/164dc8bc3345304bd907ec1e40a75c6f/4_replay) 


5. After that we added new future to check ratio of available food/nonavaiable food to n-depth. The idea is to favour paths where more food is availble compared to lower food. However,  It became a challenge to adjust weight b/w feature minimumDistanceToFood and this feature (they are both related to Food and indirectly to food distances). This proved to be a bad feature as pacman keeps roaming randomly and moving back and forth.  At the same time we also added a feature to chasing scared ghost feature to Offensive agent. (However, Later on we found experimentally that this feature is causing offensive agent to forget its actual work of collecting food and focus on eating enemies in home territory. Hence we removed it) 

6. To solve problem as specified  in 4 in which opponent is not moving away from food nearest to our agent, added a new feature to measure distance of opponent agent (if visible) to nearest Food, and direct to agent to start moving towards some other random food.

![8_-_offensive_agent_held__hostage_](uploads/4df8370837b6dee5b20d0def584d44ad/8_-_offensive_agent_held__hostage_.gif)

8. We are red_Look at blue how it is stuck. Our agent avoid such behavior by killing it self as there is no way out


# Normalisation