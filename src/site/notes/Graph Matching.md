---
{"dg-publish":true,"permalink":"/Graph Matching/","tags":["Academics"]}
---

# Index/Contents
[[Graph Matching#What is Graph Matching?\|#What is Graph Matching?]]
[[Graph Matching#Footnotes\|#Footnotes]]

-----
# What is Graph Matching?
Matching refers to a subgraph such that each vertex has a degree of 1 or 0 i.e., each vertex is connected to a vertex with a maximum degree = 1.
Note that this is only possible for disconected subgraphs which are essentially a set of disconnected edges.
Hence, Matching can also be defined as a congruent edges of a graph where congruency is defined using degree of the vertices connected by the said edge.

# Maximum Bipartite Matching Problem
A set of people L and set of jobs R are given, we need to perform matching to confirm that most people should land a job. The Graph resulting would be a Bipartite graph with set L and set R. 
In this graph, we will have to find the Maximum Matching {[[Graph Matching#^2\|#^2]]} to find the maximum number of people that can find a job such that each vacancy is filled with no overhiring - i.e., individual degree of each of the vertices $\leq$ 1

This problem & other problems like this fall under the category of Maximum Bipartite Matching Problem.

There are 3 algorithms to solve the Maximum Bipartite Matching Problem (i.e., 3 algorithms to find Maximum Matching) are given below:
1. Stable Matching Algorithm (used in [[Stable Marriage Problem\|Stable Marriage Problem]])
2. [[Hungarian Algorithm\|Hungarian Algorithm]]



---
Next Chapter --->[[Graph Covering\|Graph Covering]]
# Footnotes
1. ***==Maximal Matching==*** is a set of edges where no more matching edges can be added to it. It does not necessarily contain maximum number of edges.
{ #1}

2. ***==Maximum Matching==*** is a set of edges where the maximum number of matching edges possible in the graph are included in the set i.e., it is a maximal matching of maximum possible edges in a graph.
{ #2}

3. ***==Perfect Matching==*** is a Maximum Matching where the degree of each vertex is 1 and total number of vertices are V/2 where V = total number of vertices in the graph. Similarly any Maximum Matching edge set where the vertices involved are odd, there will be one vertex which will have a degree = 0. Such matchings are called ***==Near-perfect matching==***.
{ #3}

4. Any path that alternates between matching and non-matching edges (where one edge is matching but the next isn't but the next-to-next is and so on) is called an ***Alternating Path***. Any Alternating Path with free end points i.e., the startring and ending edges are both non-matching is called an ***==Augmented Path==. If we flip the matching and non-matching edges, it results in a new Matching containing M+1 edges.***
{ #4}

5. 


