**Experiments with Enhancing Features For Offensive Agents (It is misplaced now. Moreover, This in just for information and should not be considered part of Wiki Now unless all team members agree):**

The idea is to make sure as soon as the opponent's defender approaches Offensive Pacman, Pacman run away without caring for anything else. Following two features were tried for this. Enhancement is to add forward knowledge. Two favorable features are given below. All information below is experimentally derived by looking at variables carefully and optimizing. To incorporate forward knowledge, we should add advanced algorithms (as already planned).

1. The first feature that was added to offensive agent was to find the distance from one of the opponents (it is visible when opponent is within 5 maze distance to the agent). This feature addition ensured that the offensive agent tries to stay away from defender as soon as it spots the defender. It worked but does not produce very effective results. The logic was calculating distance from current position of opponent, to all successors positions of agent. Whichever successor maximize the distance from the opponent, offensive agent will move to that state. This often resulted the Pacman to move to those successor states where few further actions are available to move onwards (sometimes only one which is the backward action). As a result Pacman becomes vulnerable and get caught.

2. To enhance the above feature, we added another feature to get the number of legal action at each successors position. Pacman will move to that successor where most legal actions are available to be further taken. This improved the result. But is not very effective at intersections. Often Pacman moves to dead end because it does not have forward knowledge of available actions beyond current successor and gets caught.


# UoM COMP90054 Contest Project

This Wiki can be used as external documentation to the project.
- [1. Home and Introduction](/home)
- [2. Design Choices (Offense/Defense)](/2_0_design_choices)
    - [2.1 Approach Foo](/2_1_approach)
    - [2.2 Approach FoO](/2_2_approach)
    - [2.3 Approach FOo](/2_3_approach)
- [3. Approach Evolution and Experiments](/3_approach_evolution)
- [4. Conclusions and Reflections](/4_conclusions_and_reflections)

[Next Page ](/2_0_design_choices)

You can structure your wiki pages in many different sections and styles. The above is just one example based on submissions that got a good grade in previous years :)

# Youtube presentation

![Sample Video](https://www.youtube.com/embed/enMumwvLAug)

<figure class="video_container">
  <iframe src="https://www.youtube.com/embed/enMumwvLAug" frameborder="0" allowfullscreen="true"> </iframe>
</figure>

## Team Members

* Waneya Iqbal        - iqbalw@student.unimelb.edu.au     - 919750
* Maxim Mattvey       - mattveym@student.unimelb.edu.au   - 694125
* Matthew O'Halloran  - mohalloran@student.unimelb.edu.au - 702322