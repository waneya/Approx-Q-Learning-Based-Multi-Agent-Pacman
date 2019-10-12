Experimental evolution, along with associated replays are illustrated below. We continuously monitored our agent and improved it from replays available from tournaments or staff_teams. It was then re-trained to account for the updated feature representation. The evolutionary process and the tournament results after this phase are presented below.

# Evolution of the approach

#|Percentile|Date|Pos|No. teams|Points|Win|Tie|Lost|TOTAL|FAILED|Score balance|
|--------|---|---|---|---|---|---|---|---|---|---|---|
|1|54%|07/10/2019|13|23|66|21|3|22|46|0|-19|
|2|83%|08/10/2019|24|29|42|14|0|42|56|39|-66|
|3|18%|09/10/2019|6|33|139|43|10|11|64|0|225|
|4|42%|11/10/2019|17|40|136|44|4|30|78|0|-34|
|5|9%|12/10/2019|4|47|203|64|11|17|92|0|447|


## Evolution 1 | Competition results: Position - 13/23 | Percentile - 54%
----

On 7th October we found out that our agent was entering into the dead ends and getting killed.

To solve this we have added a feature to check number of available actions of a successor node, and avoid entering a position that limited the number of actions available.

### Evolution 1 Demo
[ev1.gif.sb-a6948946-igj0LZ](uploads/9598b15c54c5919126f6b4696f2ecea9/ev1.gif.sb-a6948946-igj0LZ)
between 1000-800 against staff super team (our agent is red) entering dead end.[Cheeky-Pacmen_vs_staff_team_super_RANDOM1292.replay](uploads/0a9d003bd5831487c091254d22582513/Cheeky-Pacmen_vs_staff_team_super_RANDOM1292.replay)

#### Strategy summary

| Pros | Cons |
|-----------------|:-------------|
| First body part | Second cell  |
| Second line     | foo          |

## Evolution 2 | Competition results: Position - 24/29 | Percentile - 83%
----

We found out that our offensive agent was continuously exceeding the time limit to make a move and crashing.

We figured out that getting number of actions available to a depth of n with n>8 was causing this problem. This was an important feature to find dead ends and avoid them when being chased by enemy agent. To improve this, we wrote an efficient algorithm to find out this depth using IDS. With the new version we can work on n>50 and not exceed the time limit.

### Evolution 2 Demo

[Cheeky-Pacmen_vs_staff_team_medium_contest16Capture.log](uploads/52f1eebb933d3e63e4b05121f3a859c3/Cheeky-Pacmen_vs_staff_team_medium_contest16Capture.log)

#### Strategy summary

| Pros | Cons |
|-----------------|:-------------|
| First body part | Second cell  |
| Second line     | foo          |

## Evolution 3 | Competition results: Position - 6/33 | Percentile - 18%
----

We focused on optimising the entry point of the agent. We also focused on eliminating any back and forth repetitions. The solution to both problems was randomness.( will explain more later..............)

### Evolution 3 Demo

Demo description

#### Strategy summary

| Pros | Cons |
|-----------------|:-------------|
| First body part | Second cell  |
| Second line     | foo          |

## Evolution 4 | Competition results: Position - 17/40 | Percentile - 42%
----

During 11th October We have added a feature in which agent would kill itself when stuck between and enemy ghost agent and wall. Superior agents would trap our agent and remove any ability to play the game. We found out that the feature was not working correctly and agent is killing itself randomly. The problem is shown is 

Solution: The bug was debugged and agent performed well after wards.

### Evolution 4 Demo

the replay below at around time 600-500.
[Cheeky-Pacmen_vs_staff_team_super_RANDOM4214.replay](uploads/83034c46a0d216eacd086f4e97bd995e/Cheeky-Pacmen_vs_staff_team_super_RANDOM4214.replay).

#### Strategy summary

| Pros | Cons |
|-----------------|:-------------|
| First body part | Second cell  |
| Second line     | foo          |

## Evolution 5 | Competition results: Position - 4/47 | Percentile - 9%
----

On 12th October the agent would return home after eating one-third food. In the problem below against staff team super and top, our team lost because the agent collected enough food but did not focus on returning home when the time was running out.

We have added a condition that when less than 200 unit of time is left, pacman will focus on returning home, in any case. After adding this condition we won against all staff-teams on 12th october at 8am session.

### Evolution 5 Demo

[Cheeky-Pacmen_vs_staff_team_super_RANDOM1522_This_gives_us_the_hint_that_when_less_than_200_time_is_left_we_must_go_back.replay](uploads/2366f79908f4fc80ae96eb7a93b148b0/Cheeky-Pacmen_vs_staff_team_super_RANDOM1522_This_gives_us_the_hint_that_when_less_than_200_time_is_left_we_must_go_back.replay)

[Cheeky-Pacmen_vs_staff_team_top_RANDOM1522_This_gives_us_hint_that_when_small_time_is_left_go_back_home.replay](uploads/358ee05c1abb31112b0bc01ff9407dfc/Cheeky-Pacmen_vs_staff_team_top_RANDOM1522_This_gives_us_hint_that_when_small_time_is_left_go_back_home.replay)

![image](uploads/632378307ac162f354ba5ff8d8bdf704/image.png)

#### Strategy summary

| Pros | Cons |
|-----------------|:-------------|
| First body part | Second cell  |
| Second line     | foo          |


[Previous Page](/3_approach_evolution)| [Next Page](/4_conclusion)