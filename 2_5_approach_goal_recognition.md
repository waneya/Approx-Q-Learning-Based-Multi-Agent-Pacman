
# Inferring if enemy pacman is heading towards capsule

# Recognising non-visible enemy pacman is eating food

Because of agents being visible within only 5 manhattan distance, it is difficult to accurately distinguish where an agent is located outside of that range. Although a noisy distance is provided, this distance only provides a range of possible positions from an agent inquiring the noisy distance of others - and so, does not indicate which direction the un-seen agent(s) are. 

Being able to accurately understand where an agent is, is useful to agents when they are in their home territory (defending) and in enemy territory (eating food). Through this game, we have found an alternative method to identify accurate positions of only enemy agents when they are eating food. This is useful to agents that are attempting to defend home territory since the enemy pacman may have entered the home territory from an unseen position of the border. Whenever an enemy agent eats a food, we are able to recognise their exact position through the mapping of the food-grid. This can allow defensive agents to find an unseen enemy pacman eating food - something that is valued greatly as maps get larger and the possibility of an enemy agent entering home territory unseen is greater.

Challenges experienced:
*  Even though an exact position can be obtained of enemy pacmen upon eating food, it is difficult to understand which direction they are headed afterwards. If after an enemy pacman has eaten a food, we can attempt to goal infer that they will either continue to eat food nearby, or head home with some probability to guarantee their haul. As they eat more food, we can attempt to attribute greater probability that they will head home and vice-versa. Thus, a defensive agent can attempt to gradually move towards an enemy pacman with the intentions of intercepting them, depending on which direction they expect them to be heading in.

