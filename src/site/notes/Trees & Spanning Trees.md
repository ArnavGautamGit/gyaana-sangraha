---
{"dg-publish":true,"permalink":"/Trees & Spanning Trees/","tags":["Academics"]}
---


---
# Trees & Spanning Trees
> A "Tree" is a [[Data Structure\|Data Structure]] named after the naturally found trees in the environment since they diverge into smaller and smaller branches. 

In proper definition, Tree is a Connected, Uni-Directed Acyclic [[Graph (Data Structure)\|Graph]]. 
The "Spanning Tree" is the subset of a [[Graph (Data Structure)\|Graph]] which all the vertices covered with a minimum possible number of edges and only one path containing any pair of the vertices. 
## Trees
- Can also be called as a Connected Undirected Acyclic Graph.
- Only 1 path is available between any pair of vertices
- Tree with $\large n$ number of vertices has $\large (n-1)$ edges
- Tree is a minimally connected graph.
## Spanning Tree
- Tree with respect to a graph
- Subset of a graph which has all the vertices covered with a minimum possible number of edges and only 1 path containing any pair of the vertices.
- Has all the properties of Trees.
## Minimum Spanning Tree (MST)
- A Spanning Tree for a graph that takes minimum cummulative edge cost. i.e., if all edges are to be added, this Spanning Tree takes the least cost compared to every other possible permutation/combination of edges.
- Minimum Spanning Trees can be calculated using three algorithms: 
	- Prim's Algorithm
	- Kruskal's Algorithm
	- Borůvka's Algorithm (Also called Sollin's Algorithm)

---
# What is the Borůvka's (Sollin's) Algorithm?
This was the first ever algorithm for finding an MST.
1. Initialise all vertices as individual components
2. Initialise MST as empty
3. While there are more components, do the following for each component:
	1. Find the smallest weight edge that connects to any component (if starting component is not given)
	2. Add this set to MST if not already added (except when loop is forming)
4. Note that you CAN go back to previously visited vertices if there exists another path which has lower cost except if it forms cycle or loop.
5. Repeat step 3 in loop until no vertex is left disconnected.
6. return MST

---
# What is the Kruskal's Algorithm?
1. Sort all edges in increasing order
2. Pick the smallest edge. Check if it forms Cycle.
3. If no cycle is formed, keep it. Else, discard it.
4. Repeat step 2 and 3 until there are $\large n-1$ edges left ($\large n=$ number of vertices)

---
# What is the Prim's Algorithm?
Start from any one vertex and keep connecting the edges with the smallest edge weights. No backtracking allowed.

---
Next Chapter ---> [[Graph Covering\|Graph Covering]]
# Footnotes
1. ***==Branches==***: They are the edges of the graph that are ALSO present in the Minimum Spanning Tree (MST).
{ #1}

2. ***==Chords==***: They are those edges that are only a part of the graph but not the MST.
{ #2}


