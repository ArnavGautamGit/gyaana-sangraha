---
{"dg-publish":true,"permalink":"/Goal-Tracking System (Legacy)/","tags":["Productivity"]}
---


---
# Nuclear Mode's Goal-Tracking System
> Template ***DERIVED*** from Shwetabh Gangwar's [[Attack Mode/Attack Mode (Course)\|Attack Mode (Course)]]. Where another smaller Course Nuclear Mode was included.

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

| Day       | Habitica Dailies | Habitica To-Dos | Total<br>Score | Daily Rating <br>(0-5) | Daily Goals for the day                                                      | Daily Summary of the day                                                              |
| --------- | ---------------- | --------------- | -------------- | ---------------------- | ---------------------------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| Monday    | 4/4              | 1/2             | 5/6            | 4.167                  | - Finish JavaScript<br>- Workout<br>- Keep the book Meditations in your bag. | - Workout done<br>- Couldn't finish JavaScript.<br>- Kept the book Meditations in bag |
| Tuesday   | 2/3              | 1/1             | 3/4            | 3.75                   | - Finish JS<br>- Start React<br>- Read                                       | - Finished JS<br>- Started React<br>- Read some                                       |
| Wednesday | 1/3              | 1/1             | 2/3            | 3.33                   | - React Karo<br>                                                             | - React Ki                                                                            |
| Thursday  | 0/2              | 1/1             | 0/3            |                        | - React<br>- Read                                                            | - React                                                                               |
| Friday    |                  |                 |                |                        |                                                                              |                                                                                       |
| Saturday  |                  |                 |                |                        |                                                                              |                                                                                       |
| Sunday    |                  |                 |                |                        |                                                                              |                                                                                       |


| Week       | Weekly Rating | Weekly Summary |
| ---------- | ------------- | -------------- |
| 2-8 June   |               |                |
| 9-15 June  |               |                |
| 16-22 June |               |                |
| 23-29 June |               |                |
| 30th June  |               |                |


| Month     | Avg Rating | Monthly Summary                                                                                                                                                            |
| --------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| January   | 2.5        | Could have done more, busy in weddings                                                                                                                                     |
| February  | 3.3325     | Improved, Learnt to Cook Lunch for myself (just in case)                                                                                                                   |
| March     | 2.458      | - Got Sick 1st Week <br>- PC crashed 2nd Week, <br>- 3rd Week's New Rating Formula may lower ratings                                                                       |
| April     | 3.091      | - Shifted to Laptop <br>- Back to Habitica, Need to regain rhythm                                                                                                          |
| May       | 3.2996     | - May began on a thursday with a 5/5 rating for 1st May. <br>- College Over & "Daily Goals" section added.<br>- Stopped following the template in the last 2 weeks of May. |
| June      |            | - Returned to following the template in June                                                                                                                               |
| July      |            | - First Paid month at AventIQ                                                                                                                                              |
| August    |            |                                                                                                                                                                            |
| September |            |                                                                                                                                                                            |
| October   |            | Internship at AventIQ ends this month.                                                                                                                                     |
| November  |            |                                                                                                                                                                            |
| December  |            |                                                                                                                                                                            |


| Year | Avg Rating | Yearly Summary                                |
| ---- | ---------- | --------------------------------------------- |
| 2025 |            | Year 1 of using Shwetabh's Attack Mode Course |


---
### Changes
1. After the Score used to be determined, we assigned an arbitrary rating to the day as a number between 1 and 5. In the last week of March 2025, a new system was introduced where Ratings had a more objective formula of multiplying the score with 5 to get the final score out of 5 with a possible rating of 0 (unlike previous system where rating was subjective and not doing anything could still get you a non-zero score)
2. Before 26th April 2025, the Score was determined by the number of tasks on Tasks.org App completed that were due for a given day and it was not as compatible with Habitica. Now Score is calculated as a sum of the dailies completed out of the total & any To-Do finished as Bonus!
3. 


### Ideas for Next Year
1. Have 52 entries for each week. No need to track months, it is a waste of time to compute since all months do not start on a Monday and the weeks which are split across months are not counted in full, yet have the same weightage. Use Daily Score to compute Weekly and Yearly Averages only.
	1. Yes, it does add to the challenge and yes, life is not fair
	2. But, this is not a scientific way of measurement if unequal weeks are given the same weightage during measurement.
2. Use Dataview or better more powerful plugin instead of regular Tables. 