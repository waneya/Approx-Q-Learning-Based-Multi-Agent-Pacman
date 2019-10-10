# Design Choices

## Considerations

***The need to generalise***

*(1) Randomly generated maps* : because the maps are randomly generated, it cannot be expected that our agents will be playing on the same map or same set of maps. Thus, assuming an infinitely possible number of maps that can act as the battlefield for our agents, this must be considered when making design choices. Therefore, abstract methods must be utilised to abstract away from an individual map to be able to perform well on a variety and additionally, unseen maps.

*(2) Variety of opposing agents* : with similar reasoning to the randomly generated maps, there are a number of opposing agents which we do not know about or may not encounter until the final competition. Therefore, it is important to also generalise to the types of opposing agents that may be encountered, as this will maximise the overall chance of success. 

***Multi-agent problem***

*(1) A sub-class '2-agent' problem* : in this format of competition, there are only 2 agents per team. This influences the design choices made throughout our implementation as we must think about how these 2 agents should be utilised, and if they should engage in cooperative dynamic behaviour. E.g. they can attempt to communicate and share common knowledge or intentions after learning new information from the map or enemy agents.

*(2) Offensive agents* : 

*(3) Defensive agents* :

*(4) Hybrid (reflexive agents)* :


- Design an offensive and defensive agent or generalise to a multi-agent problem?
- https://towardsdatascience.com/modern-game-theory-and-multi-agent-reinforcement-learning-systems-e8c936d6de42
- Reinforcement learning
- https://github.com/deepmind/trfl/blob/master/docs/index.md 
- Deep Q-Learning
- https://towardsdatascience.com/qrash-course-deep-q-networks-from-the-ground-up-1bbda41d3677
- https://towardsdatascience.com/how-to-teach-an-ai-to-play-games-deep-reinforcement-learning-28f9b920440a

## Techniques

1. Reinforcement Learning – classical, approximate or deep Q-learning (Model-Free MDP) 
2. Heuristic Search Algorithms (using general or pacman specific heuristic functions) 
3. Goal Recognition techniques (to infer intentions of opponents)
4. Game Theoretic Methods

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