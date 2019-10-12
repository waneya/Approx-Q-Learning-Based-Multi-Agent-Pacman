# Design Choices

## Considerations

***Scoring & winning***

To score, an agent must return food pellets back to home territory without dying. To win, the team must retain a score of >0 by time 0. These factors influence implementation decisions in the direction of maximising the probability of winning against opposing teams, and has various implications that are discussed in further sections of this wiki.

***Computation time***
At initialisation of the game, each team has 15secs to perform 'registry' computations, and then each turn thereafter allows for 1sec of computation. After 3 warnings of exceeding 1sec, or a single move >3sec, a team is disqualified. This places quite a hard margin on computation time, as each agent has 300 moves, i.e. 600 moves per team, and so there is little leniency for over-computation. Therefore, calculations and techniques utilised must consider this as a limiting constraint, and be efficient in the method of calculation as well as scalable to be able to generalise to all states.

***The need to generalise***

*(1) Randomly generated maps* : because the maps are randomly generated, it cannot be expected that our agents will be playing on the same map or same set of maps. Thus, assuming an infinitely possible number of maps that can act as the battlefield for our agents, this must be considered when making design choices. Therefore, abstract methods must be utilised to abstract away from an individual map to be able to perform well on a variety and additionally, unseen maps.

*(2) Variety of opposing agents* : with similar reasoning to the randomly generated maps, there are a number of opposing agents which we do not know about or may not encounter until the final competition. Therefore, it is important to also generalise to the types of opposing agents that may be encountered, as this will maximise the overall chance of success. 

***Multi-agent problem***

*(1) A sub-class '2-agent' problem* : in this format of competition, there are only 2 agents per team. This influences the design choices made throughout our implementation as we must think about how these 2 agents should be utilised, and if they should engage in cooperative dynamic behaviour. E.g. they can attempt to communicate and share common knowledge or intentions after learning new information from the map or enemy agents.

*(2) Offensive agents* : to be able to win and not tie at the best outcome, there must be some form of aggressive behaviour to eat food pellets in enemy territory. Deciding how this should be done, and if it should be a purely aggressive agent is the basis behind an offensive agent.

*(3) Defensive agents* : to be able to maintain a positive score, or to avoid losing all pellets, defensive behaviour is necessary to either eliminate or stall enemy agents from cashing in food pellets. 

*(4) Hybrid (reflexive) agents* : as the agents are not restricted to a purely defensive nor offensive behaviour pattern, there is a design choice consideration of whether to attempt to implement this. 

## Techniques

1. Approximate Q-learning (reinforcement learning; model-Free MDP) 
2. Heuristic search algorithms (using general or pacman specific heuristic functions) 
3. Game theoretic methods
4. Goal recognition techniques (to infer intentions of opponents)


## Files implemented and utilised (in addition to files provided by UC Berkeley)

***myTeam.py:*** the main file that implements agent set-up for the game, i.e., defines how they will behave and play the game. It also includes the approximate q-learning methodology for when the agents are training.

***usefulFunctions.py:*** contains helper methods and heuristic functions that are either made use of in *myTeam.py* or *featureExtraction.py*. 

***featureExtraction.py:*** contains the majority of functions that are utilised to generate features within *myTeam.py*.


## Offense

1. Detection of a chase by an agent. Method used is isAgentChasingAhent(self, chasingAgentIndex, chasedAgentIndex). This method determines if an agent is being chased by another by considering the distances in three consecutive game states. If an enemy ghost is chasing, the offensive agent will try to approach a capsule if available. If no capsule is available the agent will try to return home while eating the food on the way.

The attched replay clearly demonstrates this technique:
[replay-0](uploads/bcab2c8cd615255eaea034f5e7450f2d/replay-0)

2. One of the biggest challenge for the offensive agent is to break through the border and enter the enemy teritory especially when the number of entry points are few and most of them are blocked by walls. The approach is using random points at home border. If our agent fails to enter the enemy teritory from a point because it is protected by enemy agent, it changes its path randomly and try to enter enemy teritory from a different point. After failing to enter from the center it tries to enter from top at time 975 and broken into enemy teritory successfully. At around 820 another feature is demonstrated and  our agent also avoids dead end [instead of going down in the column to food) it prefers to go up to avoid trapping in the dead end ( the method is detecting dead tunnels (path with no exit) [method: isSuccessorTunnel( successorPosition, gameState) that uses IDF to detect dead tunnels (with or without Food,) and the logic is: if enemy is nearby it will avoid dead tunnel  even if it has food), if the enemy is not nearby it may try 2 go to tunnel and collect food, if there is no food it will never go to that path. This is demonstrated at 820, going down leads to dead tunnel) 

[replay-0](uploads/9aede4c576242d0caa997bec838c983e/replay-0)

3. Related to second feature described above at 820 that detects dead tunnels, there is another methods that calculates the number of actions available at each successor to a depth of 50 states. When an enemy is nearby or chasing the agent will only take path that has most action available. At 555 in the replay, the agent can easily move up to eat many food. Instead it contunues to move right so that it can avoid successors with fewer available actions. Effectively it saves the agent from entering dead ends when enemy is nearby. If enemy is not nearby (more than a distance of 6 maze distance), it can go inside and collect. The method name is evaluateOffensiveAgentSuccessor(self, gameState, parent, grandParent,
                                      n, status_till_N_successors, visitedNodes, gamma = 1)

[replay-0](uploads/afdc74ae6a0c5f3507ad457115d479c1/replay-0)

[Back Home](/home) | [Next Home](/2_1_approach)