---
{"dg-publish":true,"permalink":"/Planar Graphs & Planarity Detection/","tags":["CompSci"]}
---

# Index/Contents
[[Planar Graphs & Planarity Detection#What is a Planar Graph?\|#What is a Planar Graph?]]
[[Planar Graphs & Planarity Detection#The Utilities Problem\|#The Utilities Problem]]
[[Planar Graphs & Planarity Detection#Planarity Detection Algorithm\|#Planarity Detection Algorithm]]
[[Planar Graphs & Planarity Detection#Homeomorphic Graph\|#Homeomorphic Graph]]
[[Planar Graphs & Planarity Detection#Kuratowski's Theorem\|#Kuratowski's Theorem]]
[[Planar Graphs & Planarity Detection#What are Dual Graphs?\|#What are Dual Graphs?]]
[[Planar Graphs & Planarity Detection#Footnotes\|#Footnotes]]

-----
# What is a Planar Graph?
- A Graph that can be drawn on a plain surface without any of its edges intersecting is known as a planar graph. It is an important concept in Graph Theory.
- A planar graph can be drawn both in planar and non-planar format
- Non-planar graphs are more easily understandable.

## Representation of Planar Graphs
![Planar Graphs.png](/img/user/Vaulted%20Images/Planar%20Graphs.png)
Each Planar Graph has atleast 2 regions {see [[Planar Graphs & Planarity Detection#^1\|#^1]]} where:
$$\Large Sum \ of \ all \ degrees \ of \ a \ region = 2 \times number \ of \ edges$$

## Euler's theorem on planar graph
$$\Large \vert V \vert - \vert E \vert + \vert R \vert = 2$$
here, 
$\large \vert V \vert =$ number of vertices in the graph
$\large \vert E \vert =$ number of edges in the graph
$\large \vert R \vert=$ number of regions in the graph (including infinite region)

---
# The Utilities Problem
We need to connect three amenities (Power, Water, Gas) to three houses without having any of the lines intersect with one-another.
This problem has no solution since it forms a graph resembling the $\large K_{(3,3)}$ graph which is a Kuratowski's Graph {see [[Planar Graphs & Planarity Detection#^2\|#^2]]}

---
# Planarity Detection Algorithm 
## Elementary Reduction
1. Remove Cycles
2. Eliminating one of the 'n' parallel edges between a pair of vertices. there should only be one edge connecting any pair of vertices.
3. Remove Vertices of degree 2 and merge them with neighbouring vertex.
4. At every step, all the preceeding steps need to be repeated before moving forward (even at the last step, we need to check if there are parallel edges, self-loops etc.) until one of 3 situations are seen:
	1. a single edge
	2. a complete graph of 4 vertices
	3. Non-separable single graph with n $\geq$ 7, e $\geq$ 7.
5. If condition 3 among the above arrives, we have to check with a formula: 
   $$\Large e\geq 3n-6$$
here, 
$\large e =$ number of edges
$\large n=$ number of vertices

## For Hamiltonian Graphs
1. Find Hamiltonian Cycle
2. Restructure the graph such that the Hamiltonian Cycle forms a polygon and the other edges form the diagonals. The order of vertices around the polygon must be the same as the Hamiltonian Cycle.
3. Remove the intersections of diagonals by moving them outside the graph.
4. If any intersections are present outside the graph then try to move one of the edges inside.
5. If neither 3 nor 4 is possible i.e., the diagonals intersect no matter what we do, the graph is non-planar. If not, then you obtain the planar graph.

---
# Homeomorphic Graph
A graph is said to be homeomorphic of another, if the same graph can be obtained from the other by using just 2 of these steps:
1. Merging a vertex & forming a single edge (creating Minors)
2. Adding vertices on straight edges. (creating Subdivisions)

---
# Kuratowski's Theorem
No subgraphs of the given graph should be homomorphic to the two Kuratowski's graphs. Else the given graph will be considered non-planar. ([[Planar Graphs & Planarity Detection#^2\|#^2]])
This was improved in 1935 by Dr. Wagner who published the [[Wagner Theorem\|Wagner Theorem]] in his PhD thesis.

---
# What are Dual Graphs?
![Dual Graphs 1.png](/img/user/Vaulted%20Images/Dual%20Graphs%201.png)
![Dual Graphs 2.png](/img/user/Vaulted%20Images/Dual%20Graphs%202.png)
![Dual Graphs 3.png](/img/user/Vaulted%20Images/Dual%20Graphs%203.png)


Next Chapter --->[[Colouring & Applications\|Colouring & Applications]]
# Footnotes
1. A ***Region*** is characterised by a set of edges/vertices forming its boundary. Each Graph has an infinite region outside the graph as well. The ***Degree of a Region*** is the number of edges surrounding a region. The best way to find it is to find a "film nagative of the region" and then counting the edges.
{ #1}

2. ***Two graphs $\large K_5 \ and \ K_{(3,3)}$ are called as Kuratowski's graph***. They are complete, 5-regular graph and regular, 6-vertex connected bipartite graph respectively.
{ #2}

3. 

