In descending order. (So start reading from bottom)

 (On 12th October)
Problem: Pacman will return home after eating one-third food. In the problem below against staff team super and top, our team lost because Pacman collected enough food but it does not focus on returning home when few time is left and hence we lost.

[Cheeky-Pacmen_vs_staff_team_super_RANDOM1522_This_gives_us_the_hint_that_when_less_than_200_time_is_left_we_must_go_back.replay](uploads/2366f79908f4fc80ae96eb7a93b148b0/Cheeky-Pacmen_vs_staff_team_super_RANDOM1522_This_gives_us_the_hint_that_when_less_than_200_time_is_left_we_must_go_back.replay)

[Cheeky-Pacmen_vs_staff_team_top_RANDOM1522_This_gives_us_hint_that_when_small_time_is_left_go_back_home.replay](uploads/358ee05c1abb31112b0bc01ff9407dfc/Cheeky-Pacmen_vs_staff_team_top_RANDOM1522_This_gives_us_hint_that_when_small_time_is_left_go_back_home.replay)

Solution: WE have added a condition that when less than 200 unit of time is left, pacman will focus on returning home, in any case. After adding this condition we won against all staff-teams on 12th october at 8am session.
![image](uploads/632378307ac162f354ba5ff8d8bdf704/image.png)

And consistently won against at least 3 staff teams (losing with either top or super at different times) through out the day.


Problem: (during 11th October) We have added a feature in which agent self kill itself when it is stuck between and enemy ghost agent and wall. The enemy is not killing us and the offensive pacman remains at halt. We have found out that the feature was not working correctly and agent is killing itself randomly. The prooblem is shown is the replay below at around time 600-500.
[Cheeky-Pacmen_vs_staff_team_super_RANDOM4214.replay](uploads/83034c46a0d216eacd086f4e97bd995e/Cheeky-Pacmen_vs_staff_team_super_RANDOM4214.replay).

Solution: The bug was debugged and agent performed well after wards. 


Problem: On 8th October tournamnet we found out that our offensive agent is continuously exceeding the time limit to make a move and crushing.

[Cheeky-Pacmen_vs_staff_team_medium_contest16Capture.log](uploads/52f1eebb933d3e63e4b05121f3a859c3/Cheeky-Pacmen_vs_staff_team_medium_contest16Capture.log)


Solution: We figured out that getting number of actions available to a depth of n with n>8 is causing this problem. This is an important feature to find out dead ends and avoid pacman falling into it when being chased by enemy agent. We have rewritten an efficient algorithm to find out this depth using IDS. With the new version we can work on n>50 and time limit still not exceed.

Problem: On 7th October we found out that our agent is entering into the dead ends and getting killed. See the replay below
between 1000-800 against staff super team (our agent is red) entering dead end.[Cheeky-Pacmen_vs_staff_team_super_RANDOM1292.replay](uploads/0a9d003bd5831487c091254d22582513/Cheeky-Pacmen_vs_staff_team_super_RANDOM1292.replay)

Solution: We have added a feature to check number of available actions for a successor node and avoid successors where few actions are available (we defined no limit for few. More action is preferred always)


# Evolution of the approach

You can include screenshots of precompetition results and animated gifs, to showcase the evolution of your agents.

Evolution| Percentile |Date|Position|No. teams|Points	|Win	|Tie	|Lost	|TOTAL	|FAILED|	Score balance|
|--------|---|---|---|---|---|---|---|---|---|---|---|
|4|0.425|11/10/2019|17|40|136|44|4|30|78|0|-34|
|3|0.18|09/10/2019|6|33|139|43|10|11|64|0|225|
|2|0.83|08/10/2019|24|29|42|14|0|42|56|39|-66|
|1|0.54|07/10/2019|13|23|66|21|3|22|46|0|-19|

## Evolution 1 | Competition results: Position - X/X | Percentile - X%
----

Description

### Evolution 1 Demo

Demo description

#### Strategy summary

| Pros | Cons |
|-----------------|:-------------|
| First body part | Second cell  |
| Second line     | foo          |

## Evolution 2 | Competition results: Position - X/X | Percentile - X%
----

Description

### Evolution 2 Demo

Demo description

#### Strategy summary

| Pros | Cons |
|-----------------|:-------------|
| First body part | Second cell  |
| Second line     | foo          |

## Evolution 3 | Competition results: Position - X/X | Percentile - X%
----

Description

### Evolution 3 Demo

Demo description

#### Strategy summary

| Pros | Cons |
|-----------------|:-------------|
| First body part | Second cell  |
| Second line     | foo          |

## Evolution 4 | Competition results: Position - X/X | Percentile - X%
----

Description

### Evolution 4 Demo

Demo description

#### Strategy summary

| Pros | Cons |
|-----------------|:-------------|
| First body part | Second cell  |
| Second line     | foo          |

[Previous Page](/3_approach_evolution)| [Next Page](/4_conclusion)