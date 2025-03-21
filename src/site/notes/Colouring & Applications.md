---
{"dg-publish":true,"permalink":"/Colouring & Applications/","tags":["Academics"]}
---

# Index/Contents
[[Colouring & Applications#What is a Properly Coloured Graph?\|#What is a Properly Coloured Graph?]]
[[Colouring & Applications#Footnotes\|#Footnotes]]

---
# What is a Properly Coloured Graph?
A graph with all vertices coloured such that no adjacent/neighbouring vertices have the same colour as each other.
Also defined as a graph using "Proper Colouring" for colouring all vertices of the graph.
In the exam, or any colouring problem, we need to colour all the vertices with the minimum chromatic number. {see [[Colouring & Applications#^1\|#^1]]}

## Shortcuts
1. For a cyclic graph with odd-numbered vertices, chromatic number is 3.
2. For a cyclic graph with even-numbered vertices, chromatic number is 2.
3. For a complete graph, the chromatic number is equal to the number of vertices.
4. For a bipartite graph with no isolated vertices, chromatic number is 2.
5. If some verttex has a degree = d, chromatic number of that local sub-graph = d.

---
# How are graphs coloured?
Partitioning vertices of same colour into a set. i.e., a 3-chromatic graph will have 3 sets of partitions. These sets are called Colour Classes and the process is known as Chromatic Partitioning.
Now, we need to check if the given graph is a Uniquely Colourable Graph {[[Colouring & Applications#^2\|#^2]]} or not.
Graphs may or may not be uniquyely colourable and it is completely fine.
The Third step is to find the Maximum Independent Set {[[Colouring & Applications#^3\|#^3]]} of vertices which can be given one colour. Repeat the third step until no un-coloured vertex is left.

---
# What is a Chromatic Polynomial?

---
Next Chapter --->[[Graph Matching\|Graph Matching]]
# Footnotes
1. ***==Chromatic Number==*** is the total number of distinct colours used in any graph.
2. ***==Uniquely Colourable Graph==*** is a term used for graphs which have only one chromatic partition pattern using minimum chromatic number.
3. The ***==Maximum Independent Set== (often shortened to 'MIS')*** is an independent set of maxuimum possible size of vertices, edges or regions that can be given the same colour.

