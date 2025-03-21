---
{"dg-publish":true,"permalink":"/McCabe's Software Metrics/","tags":["CompSci","Software-Development"]}
---

# Index/Contents
[[McCabe's Software Metrics#What are McCabe's Software Metrics?\|#What are McCabe's Software Metrics?]]
[[McCabe's Software Metrics#Footnotes\|#Footnotes]]

-----
# What are McCabe's Software Metrics?
These were Software Metrics developed by Thomas McCabe.
It does not look at the Metrics Objectively, (unlike [[Haalstead's Software Metrics\|Haalstead's Software Metrics]]) rather looks at the code hollistically with the sequence of occurance.
To chart the sequence of the code, it needs a Flow Graph {see [[McCabe's Software Metrics#^1\|#^1]]}

# Steps to Solve any Question
1. Create Flow Graph
2. If asked, create DD Path Graph {see [[McCabe's Software Metrics#^2\|#^2]]}.
3. If asked, $\large Complexity = e - n + 2p = Predicate Node + 1 = Number \ of \ Regions$
Sometimes, Complexity can also be $\large e - n + p$ if the ending node is connected to the starting node.
### How to create a Flow Graph?
Check the code.
```Cpp
#include <iostream>
using namespace std;

int main(){
	printf("hello");
	printf("goodbye");
}
```
Here, the Flow Graph will be 1 ---> 2 
Since there are no decision nodes i.e., no nodes which create branches (such as if-else or switchcase or loops) the DD Path Graph would be a trivial graph [[Graph Theory Fundamentals#^Trivial-Graph\|Graph Theory Fundamentals#^Trivial-Graph]]



---
Next Chapter --->[[Software Testing\|Software Testing]]
# Footnotes
1. ***Flow Graph***: also called Program Graph or Control Flow Graph. It is a directed graph where each vertex is a statement & the edges represent their sequence of execution. Note that comments and hash directives are ignored.
{ #1}

2. ***DD Path Graph***: Flow Graphs have a vertex for each node, making htem extremely hard to read. Hence DD path graphs simplify by combining all vertices between a decision node and the next decision node into one - reducing the number of nodes and simplifying the graph. These "groups" are logged in a Decision-to-Decision (DD) path table. These are never made unless asked.
{ #2}


