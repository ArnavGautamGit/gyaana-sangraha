---
{"dg-publish":true,"permalink":"/Introduction to UML/","tags":["Academics","Software-Development"]}
---

# Index/Contents
[[Introduction to UML#What is UML?\|#What is UML?]]
[[Introduction to UML#Footnotes\|#Footnotes]]

-----
# Unified Modelling Language (UML)
> It is a modelling technique which primarily focuses on building diagrams and chart the functionalities and design elements of a project.

It is a step which typically falls after [[Project Scheduling#Requirement Engineering & Analysis\|Project Scheduling#Requirement Engineering & Analysis]]

UML has three main components:
1. Elements (Things) ---> Classes, Interfaces etc.
2. Relationships between Elements ---> Association, Generalization etc.
3. Diagrams ---> Combination of the Elements and their Relationships (like Class Diagrams)

Association is depicted by a solid arrow. In class diagrams, it may be only a solid line and the arrow defined with the name to show which direction the association is.
Generalisation is depicted with a solid arrow with hollow tip
Dependency is shown with a dotted arrow with a solid tip
Realisation is shown as a dotted arrow with a hollow tip.

---
# Types of UML Diagrams

- ### Type 1: Structural Diagrams
	- [[Class Diagram\|Class Diagram]] ---> shows a set of classes, interfaces and their relationships.
	- [[Object Diagram\|Object Diagram]] ---> shows a set of objects and their relationships.
	- Component Diagram ---> shows the organization and dependencies among a set of components.
	- Deployment Diagram ---> shows the configuration of runtime processing nodes.
- ### Type 2: Behavioural Diagrams
	- [[Use Case Diagram\|Use Case Diagram]] ---> shows use cases, actors and their relationship
	- [[Sequence Diagram\|Sequence Diagram]] ---> shows interaction of actors with objects and other objects in a sequencial manner like they are supposed to occur according to time.
	- [[Collaboration Diagram\|Collaboration Diagram]] ---> shows the structural organization of the objects that send and receive messages. 
	- [[Statechart Diagram\|Statechart Diagram]] ---> shows a state machine consisting of states, transitions an events.
	- [[Activity Diagram\|Activity Diagram]] ---> used to analyze the bahaviour within more complex use-cases.

---
# Two ways of defining classes in UML Class Diagrams
![UML Class Diagram 1.png](/img/user/Vaulted%20Images/UML%20Class%20Diagram%201.png)

---
# Four Ways of defining objects in UML Object Diagram
![UML Object Diagram 1.png](/img/user/Vaulted%20Images/UML%20Object%20Diagram%201.png)

---
# What are Packages?
Packages are a way of grouping classes into common categories. Classes and Objects are modelled when showing the package they belong to. Classes and objects will interact with classes and objects of different packages—hence multiple packages create a system.

A Package is expressed by appending the name of package and a double colon before the class name in either a class or an object.
![UML Packages.png](/img/user/Vaulted%20Images/UML%20Packages.png)

---
# The Four Phases of Unified Process in UML
1. Inception ---> Analysis Phase with Use-Case Diagrams
2. Elaboration ---> Design Phase with Class Diagrams and Sequence Diagrams
3. Construction ---> Implementation of the project, Actual Coding
4. Transition ---> Deployment Phase

---
Next Chapter --->[[Code Optimization\|Code Optimization]]
# Footnotes


