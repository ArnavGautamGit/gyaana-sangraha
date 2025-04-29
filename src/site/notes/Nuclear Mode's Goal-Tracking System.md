---
{"dg-publish":true,"permalink":"/Nuclear Mode's Goal-Tracking System/","tags":["Productivity"]}
---


---
# Nuclear Mode's Goal-Tracking System
> Template ***DERIVED*** from Shwetabh Gangwar's [[Attack Mode (Course)\|Attack Mode (Course)]]. Where another smaller Course Nuclear Mode was included.

Contains a Goal List, Daily Tasks and Progress towards the Goals.
Using this note everyday will keep me accountable to the Goals I have set.

---
### Goal List
The List of Goals you want to achieve:
- [ ] Get a SGPA of 9 this semester.
- [ ] Get a Job
	- [x] Get an internship
	- [ ] Convert to PPO
- [ ] Get in shape
	- [ ] Eat Healthy
	- [ ] Regular Resistance Workout
- [ ] Get Intelligent (by reading more books)

---
### Daily Recurring Tasks (Dailies)
The Tasks that are repeated at a Frequency, check Habitica App. Some of the tasks could be stuff like: Completing College Notes and Calorie Tracking.

All one needs is to find a way to stay accountable to the goals & tasks for the day. Since it is an era of technology, one needs an app to keep them accountable and often gamification of productivity is a good way of staying accountable. 
So there is a big clash between Habitica (representing gamified productivity) and Tasks.org App (representing serious productivity).
[[Habitica App vs Tasks App (Productivity)\|Habitica App vs Tasks App (Productivity)]]

---
### Tracking Progress
Each Day is tracked on the Habitica App. 
The App divides the day into three parts: Habits, Dailies and To-Do

Habits section lists out any good habits one wants to inculcate & bad habits one wants to leave. Anytime you click minus (-) sign on the bad habit (claiming you performed it) you gamified self loses health. On clicking the plus (+) sign on a positive habit, you gain XP to level up. Levelling up fills your health back to the maximum.

Dailies section lists out any Recurring Tasks that are due today. It is expected players use it to mark daily deliverables towards one's positive habits. However this is not a restriction or guideline which is explicitly mentioned, players can set whatever they want.

To-Do Section details a to-do list for tasks that occur only once and need to be finished on a specific deadline. Example: "Submit XYZ assignment before ABC date"

At the end of each day, unfinished Dailies damage the user's health while unfinished Tasks or unmarked Habits do not.

> ***To avoid the hyphen in "To-Do" being mistaken by LaTeX language for a minus (-) sign, we will use the term "tasks" instead in all formulae.***

Each Day has a Score. The Score for a day is calculated by the following Formula:
$$\Large Score =\dfrac{{Dailies \ Done} + {Tasks \ Done}}{{Total \ Dailies} + {Active \ Tasks}}$$
$$\Large Rating = Score \times 5$$
Now, even the rating of 0 is possible.
The Weekly Rating is the average of all the individual days in a week. The Monthly Rating is the average of Weekly Rating.

| Day    | Habitica Dailies | Habitica To-Dos | Total<br>Score | Daily Rating (0-5) | Daily Summary                                                                               |
| ------ | ---------------- | --------------- | -------------- | ------------------ | ------------------------------------------------------------------------------------------- |
| Mond   | 1/3              | 1/1             | 2/4            | 2.5                | Submitted the Hard Copy Version of UAV Assignment 2. <br>Missed on Workout & College Notes. |
| Tuesd  | 2/2              | 1/1             | 3/3            | 5                  | Finished & Submitted International Studies PBL Report.<br>Need to Finish College Notes.     |
| Wedns  |                  |                 |                |                    |                                                                                             |
| Thursd |                  |                 |                |                    |                                                                                             |
| Friday |                  |                 |                |                    |                                                                                             |
| Satur  |                  |                 |                |                    | Presentation at 9:00 AM of Major Project 2 in College                                       |
| Sund   |                  |                 |                |                    |                                                                                             |


| Week      | Weekly Rating | Weekly Summary                                                                                                                                                                                                   |
| --------- | ------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1-6 Apr   | unknown       | Only Known Rating is 5/5 on 1st April                                                                                                                                                                            |
| 7-13 Apr  | 2.4446        | Permanently Shifted to Laptop & PC is only used for printing                                                                                                                                                     |
| 14-20 Apr | 2.774         | Regaining Rhythm after coming back to Habitica                                                                                                                                                                   |
| 21-27 Apr | 3.642         | Changed the formula for calculating Score to break tasks into dailies and to-dos like Habitica does. Seems to have made it more compatible with Habitica while the older system worked better for Tasks.org App. |
| 28-30 Apr |               |                                                                                                                                                                                                                  |


| Month     | Avg Rating | Monthly Summary                                               |
| --------- | ---------- | ------------------------------------------------------------- |
| January   | 2.5        | Could have done more, busy in weddings                        |
| February  | 3.3325     | Improved, Learnt to Cook Lunch for myself (just in case)      |
| March     | 2.458      | Got Sick, PC crashed, New Rating Formula may lower ratings    |
| April     |            | Shifted to Laptop and back to Habitica, Need to regain rhythm |
| May       |            |                                                               |
| June      |            |                                                               |
| July      |            |                                                               |
| August    |            |                                                               |
| September |            |                                                               |
| October   |            |                                                               |
| November  |            |                                                               |
| December  |            |                                                               |


| Year | Avg Rating | Notes                                         |
| ---- | ---------- | --------------------------------------------- |
| 2025 |            | Year 1 of using Shwetabh's Attack Mode Course |


---
### Changes
1. After the Score used to be determined, we assigned an arbitrary rating to the day as a number between 1 and 5. In the last week of March 2025, a new system was introduced where Ratings had a more objective formula of multiplying the score with 5 to get the final score out of 5 with a possible rating of 0 (unlike previous system where rating was subjective and not doing anything could still get you a non-zero score)
2. Before 26th April 2025, the Score was determined by the number of tasks on Tasks.org App completed that were due for a given day and it was not as compatible with Habitica. Now Score is calculated as a sum of the dailies completed out of the total & any To-Do finished as Bonus!