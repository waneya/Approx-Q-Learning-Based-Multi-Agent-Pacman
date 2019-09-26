**Experiments with Enhancing Features For Offensive Agents (This in just for information and should not be considered part of Wiki Now unless all team members agree):**

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

List here the full name, email, and student number for each member of the team:

* Full Name - Student email - UoM Student number
* Waneya Iqbal - iqbalw@student.unimelb.edu.au - 919750
* Maxim Mattvey - mattveym@student.unimelb.edu.au - 694125
* Matthew O'Halloran mohalloran@student.unimelb.edu.au - 702322

## Useful links - Wiki features

This wiki uses the [Markdown](http://daringfireball.net/projects/markdown/) syntax. 

1. The [MarkDown Demo tutorial](https://about.gitlab.com/handbook/product/technical-writing/markdown-guide/) shows how various elements are rendered.
2. This 5min video shows how to use markdown for creating [issues](https://www.youtube.com/watch?v=Ix416lAYRSg).
3. The [GitLab documentation](https://docs.gitlab.com/ee/user/project/wiki/) has more information about using a wiki.
4. This video shows how can you use [boards and issues](https://www.youtube.com/watch?v=CiolDtBIOA0) to integrate agile methodologies for working in your team.

The wiki itself is actually a git repository, which means you can clone it, edit it locally/offline, add images or any other file type, and push it back to us. It will be live immediately.

Go ahead and try:

```
$ git clone https://gitlab.eng.unimelb.edu.au/nlipovetzky/comp90054-pacman.wiki.git
```

Wiki pages are normal files, with the .md extension. You can edit them locally, as well as creating new ones.

## Syntax highlighting



Here's an example of some Python code:

```python

def wiki_rocks(text):
    formatter = lambda t: "funky"+t
    return formatter(text)
```


You can check out the source of this page to see how that's done. Just clone the wiki and get inspired to start your own project wiki.


Have fun!