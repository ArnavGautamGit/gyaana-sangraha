---
{"dg-publish":true,"permalink":"/Graph Theory Fundamentals/","tags":["Academics"]}
---

***Created on: 08/01/2024
Last updated: 08/01/2024***

----
# Index/Contents
[[Graph Theory Fundamentals#Lecture 1 & 2 What is a Graph?\|#Lecture 1 & 2 What is a Graph?]]
[[Graph Theory Fundamentals#Lecture 3 Isomorphism and Complements of a Graph\|#Lecture 3 Isomorphism and Complements of a Graph]]
[[Graph Theory Fundamentals#Footnotes\|#Footnotes]]

-----
# Lecture 1 & 2: What is a Graph?
A Graph is defined as a collection of vertices and edges.
It is widely used in Linguistics (tracking relationship between languages), Computer Networks, Rail & Road Maps, Dependency Graphs, UMLs and many more such concepts are based on Graphs.
## Types of Graphs
- ***Finite Graphs***: Have finite vertices and edges.
- ***Trivial Graphs***: One vetex, no edges.
{ #Trivial-Graph}

- ***Simple Graphs***: Neither self-loops ([[Graph Theory Fundamentals#^9c\|#^9c]]) nor parallel edges. ([[Graph Theory Fundamentals#^9b\|#^9b]])
- ***Multi-Graphs***: Parallel Edges present but no self-loops.
- ***Pseudo Graph***: Has both Parallel Edgs and self-loops.
- ***Sparse Graph***: Number of Edges << (Number of Vertices)$\large ^{2}$ 
- ***Dense Graph***: Graph that is not sparse is dense.
- ***Null Graph***: Graph with only vertices and no edges.
- ***Complete Graph***: Graph with an edge between every pair of vertices.
	  i.e., $m =\dfrac{n(n-1)}{2}$ 
	  where $\large m$ is the number of edges and $\large n$ is the number of vertices
- ***Regular Graph***: All vertices have the same degree. All complete graphs are regular but not vice versa.
- ***D-Regular Graph***: All vertices have $\large degree = D$
- ***Bipartite Graph***: Two sets A&B are connected by a graph which is considered Bipartite if each of the vertex of Set A is connected to each vertex of Set B and vice versa.
- ***Labelled Graph***: A graph where every edge and vertex is labelled.
## Types of Subgraphs
### 1. Vertex Disjoint Subgraph
$\large G_1$ and $\large G_2$ are considered Vertex Disjoint subgraphs of $\large G$ if they are 2 subsets of G with no intersection of vertices.
### 2. Edge Disjoint Subgraph
$\large G_1$ and $\large G_2$ are considered Edge Disjoint subgraph if they are two subgraphs of $\large G$ with no intersection of common edges. Vertices can be common. Every Vertex Disjoint Subgraph is an Edge Disjoint one.
## Types of Regular Graphs
1. ***Grid Graph***: 2-dimensional grid like graphs. $\large P_n \times P_m$
2. ***Cubic Graph***: 3-regular complete graphs (like [[Peterson Graph\|Peterson Graph]])
3. ***Hypercube Graph***: N-regular Complete Graphs

---
# Lecture 3: Isomorphism and Complements of a Graph
## What is a Complement of a Graph?
It contains all vertices of the original graph but has all the edges that the original graph did not have i.e., number of common edges among Graph G and its complement G' is zero.
$|V(G)| = |V(G')|$ 
$\Rightarrow|E(G)| \bigcap |E(G')| = \phi$

$\large Edges \ in \ Complement \ Graph=\ (^nC_2  - m)= \dfrac{n(n-1)}{2} -m$
where, $\large n =$ number of vertices.
and $\large m =$ number of edges in original graph 

***==Example 1==***: If a graph has 10 vertices and 21 edges. The number of edges in its complement graph will be:
$\dfrac{10(10-1)}{2} - 21$ 
$\Rightarrow 45 - 21 = 24$
There are 24 edges in the complement graph.

***==Example 2==***: If a graph has 30 edges and its complement has 36 edges, the number of vertices will be:
$\large 30+36=66=\dfrac{n(n-1)}{2}$
$\large \Rightarrow 132 = n(n-1)$
$\large \Rightarrow n^2 - n - 132 = 0$
$\large \Rightarrow (n+11)(n-12) = 0$
Hence, there are 12 vertices in the graph (Vertices cannot be -11).
## What is Isomorphism in Graphs?
Two Graphs $G_1$ and $G_2$ are said to be isomorphic if they have all the same properties (like number of vertices, number of edges and degrees of vertices) but with a different representation from each other.
### Necessary Conditions for Isomorphism
1. Equal Number of Vertices.
2. Equal Number of Edges.
3. Same Degree Sequence (when written in ascending order).
4. Cycles must be the same (if they are present).
### Sufficient Conditions for Isomorphism
Necessary Conditions need to be satisfied, but they don't ***guarantee*** two graphs to be isomorphic.
For that we need to prove ONLY ONE out of the following:
1. Complements of both given graphs must be isomorphic.
2. Corresponding Subgraphs need ot be isomorphic.
3. Both Given graphs have the same Adjacency Matrix [[Graph Theory Fundamentals#^18\|#^18]]

---
Next Chapter---> [[Graph Traversal Algorithms\|Graph Traversal Algorithms]]
# Footnotes
- ***Neighbours***: Adjacent vertices. Represented by N(a). Where, 'a' is the name of the vertex whose Neighbours we want to find/list.
{ #1}

- ***Degree***: Number of edges connected to a vertex. Represented by d(vertex).
{ #2}

- ***In-degree***: Number of incoming edges to a vertex.
{ #3}

- ***Out-degree***: Number of outgoing edges from a vertex.
{ #4}

- ***Total Degree***: It is the sum of the degrees of all vertices. Calculated by doubling the number of edges.
{ #5}

- ***Walk***: Traversal of a graph is called walk.
{ #6}

- ***Path***: A type of walk, where vertices and edges cannot be repeated.
{ #7}

- ***Trail***: A type of walk where Vertices can be repeated but not the edges.
{ #8}

- ***Cycle***: A path whose first and last vertex is the only one which can be repeated (edge repetition is still disallowed here). It is suppoed to have a common starting/ending vertex to form a ring (also called "loop" or "ring").
{ #9a}

- ***Parallel Edges***: Pair of vertices connected with more than 1 edge. Forms a cycle.
{ #9b}

- ***Self-loops***: An edge that connects a vertex to itself.
{ #9c}

- ***Reachability***: When there exists a path connecting two vertices, it is considered reachable from the starting vertex. Denoted by $\large R_G$.
{ #10}

- ***Connectivity***: (Used generally in Undirected Graphs) All vertices are reachable from all other vertices.
{ #11}

- ***Sub-graph***: Subset of graphs. Also called "components".
{ #12}

- ***Connected Components***: Maximal Connected Sub-graph.
{ #13}

- ***Tree***: Unidirected, connected, acyclic graph.
{ #14}

- ***Forest***: Undirected, disconnected, acyclic graph (seldom called a "collection of trees")
{ #15}

- ***Distance***: Minimum number of edges (shortest path) between two vertices. Denoted by $\large S_G = max\{S_G(u, v)\}$
{ #16}

- ***Diameter***: Maximum shortest path length over all pairs of vertices. Denoted as $\large diam(G) = max\{S_G(u,v)\}$. 
{ #17}

- ***Adjacency Matrix***:
{ #18}

- ***Adjacency List***:
{ #19}



