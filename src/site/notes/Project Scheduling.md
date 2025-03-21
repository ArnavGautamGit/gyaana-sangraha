---
{"dg-publish":true,"permalink":"/Project Scheduling/","tags":["CompSci","Software-Development"]}
---

***Created on: 29/01/2024
Last updated: 29/01/2024***

----
# Index/Contents
[[Project Scheduling#What is Project Scheduling?\|#What is Project Scheduling?]]
[[Project Scheduling#Footnotes\|#Footnotes]]

-----
# What is Project Scheduling?
It is the art of Scheduling the project in such a manner that neither the Client does not think they are being made to wait nor the developers think they are being made to work a bit too hard on the project. 
But we understand how processes are scheduled, we need to understand what Processes are!

---
# What is a Project?
- Even though it can be defined in multiple ways by multiple parties, projects are those softwares a developer is tasked to create.
- We learned in [[Software Development Models\|Software Development Models]] that how a software/project has multiple requirements and features, based on which we create UML diagrams and flowcharts.
- These Charts are divided into small modules.
- Here, we call each module as a task or activity.
- In a way, A project is a collection of activity such that the start of 1st activity is the start of the project and the completion of the last activity is the completion of the project

---
# Activity Dependencies & Tabular Representation
- Tasks/Activities may depend on each other - i.e., it would be impossible to start a task before finishing another task.\
- Some companies may measure Duration in Days, some in weeks. Some may also have an extra column named "date" so we can account for Weekends.
- Dependencies column is not always filled, since not every task is dependent upon another task, if you see an empty cell for dependencies, then it is perfectly fine to be reassured that there is no such dependency.
- There is also a term known as a milestone! It takes 0 days (on a graph) after the task achievement. It is written as M in the bracket of a dependency.

| Activity | Duration | Dependencies |
| -------- | -------- | ------------ |
| T1       | 8        |              |
| T2       | 15       |              |
| T3       | 15       | T1 (M1)      |

---
# Activity Network Diagram
- Very similar a flowchart or Resource Allocation Graph
- Free ke number if done right.
- Dummy ka dhyaan rakhna bas.

---
# Requirement Engineering & Analysis
- This was the first step in all [[Software Development Models\|Software Development Models]]
- ***The goal*** is to develop & maintain sophisticated & descriptive "System Requirement Specification" document (also called the SRS document)
## Process of Requirement Engineering:
- ***==Feasibility Study==***: Rough idea presented by the client is analysed for something tht can be realistically and legally built or not.
- ***==Requirement Gathering==***: List of requirements and what features need to be coded to fulfill said requirements  
- ***==Software Requirement Specification (SRS)==***: A Document in which the System Analysts document all the requirements in a technical language, along with the feasibility, legality, estimated budget & estimated timeline.
- ***==Software Requirement Validation (SRV)==***: Requirements and the SRS are validated to check if anything is illegal, if the solution is impractical or the experts have interpreted the requirements inaccurately.
## What all should the SRS document contain?
- Client Requirements as expressed in natural language
- Technical Requirements as expressed in Structured Language.
- Design description should be in pseudo code.
- Format of forms and Graphical User Interface (GUI) screenshots.
- Mathematical Notations wherever used.
## Types of Requirements with the analogy of a phone:
1. ***System Rerquirements***: Phone's operational constrainst written in structured and technical language. Contract between client and contractor.
2. ***User Requirements***: Natural Language and Diagrams are used to market the phone.
3. ***Functional Requirements***: Features of the phone, Camera quality, Screen Refresh Rate.
4. ***Non-functional Requirements***: Colour of the phone or its durability.

---
# Requirement Elicitation Techniques
- Technique to find out (or draw out) the requirements for an intended software system by communicating with clients and stakeholders.
- #### Technique 1: Interview
	- Structured Inteview: Questions to ask and Information to be gathered is already decided.
	- Open Interviews: Un-structured Interviews.
	- Oral Interview
	- Written Interview
	- one-to-one interview
	- Group interview
- #### Technique 2: Surveys + Questionaire
	- Set of questions with objective
	- if options are not encompassing all possible answers then results may be wrong since the surveyee wouldn't be able to enter their true answer.
	- Due to the flaw mentioned above, the survey/questionaire technique is considered ==unreliable== and ==not taken seriously== unless supplemented with another one of the techniques.
- #### Technique 3: Task Analysis
	- Team of engineers analyse the operation for which the new system is required.
	- IF the client already has some software which was previously being used to perform certain operation (preferably similar/the same operation) it is studied and requirements of proposed system is collected
- #### Technique 4: Brainstorming
	- An informal debate among stakeholders is held and their inputs are recorded.
- #### Technique 5: Prototyping
	- UI without details for user to interpret the features of intended software product.
	- Gives better idea of requirements.
	- If there is no software installed at the client's end for reference, the developer creates a prototype.
- #### Technique 6: Observation:
	- Team of experts make a visit to the client's workplace to understand the actual working of the organisation. To see what environment and people will run the software andf at what load.
## Requirement Specification
The process of writing down the user and systems requirements in the SRS (or any other requirements') document.
![Requirement Engineering 1.png](/img/user/Vaulted%20Images/Requirement%20Engineering%201.png)

---
Next Chapter ---> [[Introduction to UML\|Introduction to UML]]
# Footnotes


