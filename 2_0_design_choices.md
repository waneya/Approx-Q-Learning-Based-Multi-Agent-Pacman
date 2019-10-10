# Design Choices

## Considerations

***Scoring & winning***

To score, an agent must return food pellets back to home territory without dying. To win, the team must retain a score of >0 by time 0. These factors influence implementation decisions in the direction of maximising the probability of winning against opposing teams, and has various implications that are discussed in further sections of this wiki.

***Computation time***
At initialisation of the game, each team has 15secs to perform 'registry' computations, and then each turn thereafter allows for 1sec of computation. After 3 warnings of exceeding 1sec, or a single move >3sec, a team is disqualified. This places quite a hard margin on computation time, as each agent has 300 moves, i.e. 600 moves per team, and so there is not much leniency for over-computation. Therefore, calculations and techniques utilised must consider this as a limiting constraint, and be efficient in the method of calculation as well as scalable to be able to generalise to all states.

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
3. Goal recognition techniques (to infer intentions of opponents)
4. Game theoretic methods

## General Comments

_General comments about the project goes here_

## Comments per topic

## Files utilised (in addition to files provided by UC Berkeley)

***myTeam.py:*** the main file that implements agent set-up for the game, i.e., defines how they will behave and play the game. It also includes the approximate q-learning methodology for when the agents are training.

***usefulFunctions.py:*** contains helper methods and heuristic functions that are either made use of in *myTeam.py* or *featureExtraction.py*. 

***featureExtraction.py:*** contains the majority of functions that are utilised to generate features within *myTeam.py*.


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
| Get actions | getLegalActions |
| Get successor states | generateSuccessor |
| Noisy distance to each agent | getAgentDistances |

[Back Home](/home) | [Next Home](/2_1_approach)