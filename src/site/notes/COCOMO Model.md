---
{"dg-publish":true,"permalink":"/COCOMO Model/","tags":["Academics","Software-Development"]}
---

# Index/Contents
[[COCOMO Model#What is COCOMO Model?\|#What is COCOMO Model?]]
[[COCOMO Model#Types of Cocomo (based on Software Type)\|#Types of Cocomo (based on Software Type)]]
[[COCOMO Model#Important Formulae required to solve questions\|#Important Formulae required to solve questions]]
[[COCOMO Model#Formulae in Intermediate Cocomo\|#Formulae in Intermediate Cocomo]]
[[COCOMO Model#Footnotes\|#Footnotes]]

-----
# What is COCOMO Model?
Cocomo (also spelled as in all-capital letters such as: "COCOMO") is an abbreviation derived from its original name which was: ***Co***ntructive ***Co***st ***Mo***del.
It was first proposed by B.W Boehn in 1981 (in his own book "Software Engineering Economics")

It was an idea used for Software Estimation - it was very adept at reliably estimating mainly cost, effort, size and time but it was majorly used to measure effort & duration (hence cost was derived from it) since that is what cocomo (at least in its initial structure) focused on.

COCOMO has existed in three types:
1. ***Basic COCOMO***
2. ***Intermediate COCOMO***
3. ***Detailed COCOMO***

While Basic & Intermediate varaints are in syllabus, we have to note that the Detailed one isn't.
I am not sure of the GATE syllabus, since it is also said that COCOMO is considered an important topic in [[Graduate Aptitude Test for Engineering (GATE)\|Graduate Aptitude Test for Engineering (GATE)]].

# Types of Cocomo (based on Software Type)
Cocomo can be typed on the basis of the tpe of software the devs are trying to build since each software type may need a different type of testing and help to make it work.

Cocomo can be widely divided into 3 categories on the basis of Software type:
1. ***==Organic==***: Little Innovation if any, small application program of $\lt$ 50 KLOC with experienced developers.
2. ***==Semi-Detached==***: Some Innovation, a medium sized program of 50 to 300 KLOC being made by developers being in a mixture of experience (i.e., some are experienced, while others may be freshers)
3. ***==Embedded==***: Large System or Hardware-oriented programs of 300+ KLOC being made by programmers of limited experience.

# Important Formulae required to solve questions
$$\Large Effort \ (E) = a_1 \times (KLOC)^{a_2}$$
$$\Large Duration \ (D) = b_1 \times (E)^{b_2}$$
$$\Large Staff \ Size = \dfrac{E}{D} = Staff \ Salary \times number \ of \ employees$$
$$\Large Productivity \ (P) = \dfrac{Size \ (in \ KLOC)}{Effort}$$
![Cocomo Reference Table.png](/img/user/Vaulted%20Images/Cocomo%20Reference%20Table.png)

### Weakness of Basic Cocomo
1. Doesn't define Hardware Constrainsts,
2. Doesn't define Work Environment
3. Doesn't define Personnel Quality/Experience & other attributes.

# Formulae in Intermediate Cocomo
Intermediate Cocomo is majorly the same as the basic but introduces a new factor named "Effort Adjustment Factor" i.e., EAF. (EAF is typically between 0.9 and 1.4)

$$\Large Effort \ (E) = a_1 \times (KLOC)^{a_2} \times EAF$$
$$\Large Duration \ (D) = b_1 \times (E)^{b_2}$$
To calculate the EAF, we have to multiply the two or more attributes we have been given from the tables below:
![Cocomo Reference Table 2.png](/img/user/Vaulted%20Images/Cocomo%20Reference%20Table%202.png)
![Cocomo Reference Table 3.png](/img/user/Vaulted%20Images/Cocomo%20Reference%20Table%203.png)

---
# Footnotes


