---
{"dg-publish":true,"permalink":"/Graph Traversal Algorithms/","tags":["Academics"]}
---

***Created on: 25/01/2024
Last updated: 25/01/2024***

----
# Index/Contents
[[Graph Traversal Algorithms#Lecture 4 What are Graph Traversal Algorithms? DFS? BFS?\|#Lecture 4 What are Graph Traversal Algorithms? DFS? BFS?]]
[[Graph Traversal Algorithms#Lecture 5 Topological Sort using DFS and BFS\|#Lecture 5 Topological Sort using DFS and BFS]]
[[Graph Traversal Algorithms#Lecture 6 Shortest Path in weighted, unweighted and negatively-weighted graphs\|#Lecture 6 Shortest Path in weighted, unweighted and negatively-weighted graphs]]
[[Graph Traversal Algorithms#Seven Bridges of Königsberg Problem\|#Seven Bridges of Königsberg Problem]]
[[Graph Traversal Algorithms#Footnotes\|#Footnotes]]

-----
# Lecture 4: What are Graph Traversal Algorithms? DFS? BFS?
## What are Graph Traversal Algorithms?
Specific Algorithms that are used to traverse the graph for specific applications. The Algorithms, (including reasons) are given below, there may be other applications and algorithms not dicussed here:
- For Topological Sort, we use:
	1. DFS - Depth First Search
	2. BFS - Breadth First Search

- For Shortest Distance between 2 points on a graph, we use:
	1. Dijkstra's Algorithm
	2. Bellman-Ford Algorithm
	3. Floyd-Warshall Algorithm
## What is DFS?
- DFS (or Depth First Search) is a graph traversal algorithm that walks a graph vertically/depth-wise and backtracks when it reaches a dead end.
- DFS uses a Stack and an array. 
- When we visit a specific vertex/node, it gets pushed into the Visiting Array. The array has no role until the end of the algorithm (when sequence needs to be printed).
- The entire Algorithm is run using the stack.
- Throughout the algorithm, whenever we say "visit" it means pushing the vertex into the Visiting Array.
```Pseudocode
//start
1. Start with any node if a starting node/vertex is not given in question.
2. Push that vertex into the stack, check for neighbours.
3. If there is a neighbour, repeat step 2.
4. If there is no neighbour, visit & pop the vertex on the top of the stack and look for alternate routes through some other neighbour. 
5. If no neighbours exist, then repeat step 4 till you either: 
	1. find an alternate route 
	2. stack is empty i.e., graph is fully traversed.
//end 
```
## What is BFS?
- BFS (or Breadth First Search) is a graph traversal algorithm that walks a graph horizontally, level wise. ***It is also called Kahn's Algorithm*** when used in Topological Sort
- BFS uses a Queue and an Array.
- When we visit a specific vertex/node, it gets pushed into the Visiting Array. The array has no role until the end of the algorithm (when sequence needs to be printed).
- The entire Algorithm is run using the Queue.
- Throughout the algorithm, whenever we say "visit" it means pushing the vertex into the Visiting Array.
```Pseudocode
//start
1. Start with the root vertex always.
2. Push the vertex into the queue, check for neighbours.
3. If there is a neighbour, repeat step 2.
4. If there are no neighbours, skip this vertex and visit the next one in the queue.
5. The next vertex either:
	1. Has at least 1 neighbour: Repeat Step 2
	2. Doesn't have any neighbours: Repeat Step 4
//end
```

---
# Lecture 5: Topological Sort using DFS and BFS
It is a ordering of a Directed Acyclic Graph (DAG) in a way where a vertex U is written before a vertex V for every edge that maps U ---> V
## Topological sort using DFS
![Topological Sort 1.png](/img/user/Vaulted%20Images/Topological%20Sort%201.png)
![Topological Sort 2.png](/img/user/Vaulted%20Images/Topological%20Sort%202.png)
## Topological Sort using Kahn's Algorithm
![Topological Sort 3.png](/img/user/Vaulted%20Images/Topological%20Sort%203.png)

---
# Lecture 6: Shortest Path in weighted, unweighted and negatively-weighted graphs
## Dijkstra's Algorithm - Single Source Shortest Path
- An Algorithm used to find the shortest path to all vertices from a single source vertex.
- Does not work for graphs with negatively weighted edges.
- The point $\large A$ is $\large0$ distance from itself, and we assume it to be infinitely away from the other two points.
$$\large 
Matrix \ for \ a \ 3 \ vertex \ graph \ at \ step \ 1:
\begin{bmatrix}
0 & \infty & \infty \\
\end{bmatrix}$$
- We also assume there are three edges $A \rightarrow B$, $A \rightarrow C$ and $B \rightarrow C$ with edge weights of20, 10 and 40 respectively.
$$\large 
At \ step \ 2:
\begin{bmatrix}
0 & \infty & \infty \\
0 & 20 & 40 \\
\end{bmatrix}$$
- Now we relax the minimum number out of this (except 0) i.e., 20. Relaxation is done through the following code: 
```C 
if d(u) + c(u,v) < d(v) {
	d(v) = d(u) + c(u,v);
}
/* EXPLANATION:
Here d(u) distance of u (vertex we are at) from the starting vertex.
d(v) is the distance of v (final vertex) from u.
c(u,v) is the current direct edge distance/cost from u to v.
if the sum of the distance of u from source and distance of getting to v is less than the distance of v fro source, we assign this distance as the new d(v) and relax the vertex.
*/
```
- Hereafter, it is simple, to get to C, since using the above code, we know going from A to B costs 20, and getting from B to C is 10. Also 20 + 10 < 40. Hence the final matrix is:
$$\large 
At \ step \ 3:
\begin{bmatrix}
0 & \infty & \infty \\
0 & 20 & 40 \\
0 & 20 & 30 \\
\end{bmatrix}$$
- Note, Dijkstra's Algorithm only allows 1 relaxation per vertex.
## Bellman-Ford Algorithm - For Edges of Negative Weights
1. Considerably harder to implement compared to Dijkstra's Algorithm.
2. Relaxes vertices more than once i.e., ($\large n-1$) times. Here $\large n =$ total number of vertices in the graph. Relaxation code is the same as Dijkstra's Algorithm
3. We can detect Negative Edge Cycles in graphs using BFA algorithm. In the same example as taken in the Dijkstra's Algorithm, just change the $\large A \rightarrow C$ edge to $\large C \rightarrow B$ and assign it a weight of $\large -30$. 
4. If the weights keep changing even after $\large(n-1)$ turns, negative edge cycle exists.
![Bellman-Ford Example.png](/img/user/Vaulted%20Images/Bellman-Ford%20Example.png)

---
# Seven Bridges of Königsberg Problem
The City of Königsberg in Germany is a city comprising of a pair of islands afloat on a river. There are 7 bridges that interconnect the city from the outside as well as itself.
Germans - who have a culture of walking have theorised a game problem: how to navigate the entire city with only using each of the bridges only ONCE.
![Bridges of Konigsberg.webp](/img/user/Vaulted%20Images/Bridges%20of%20Konigsberg.webp)
We have to use the concept of Euler Graph (read [[Graph Traversal Algorithms#^20\|#^20]], [[Graph Traversal Algorithms#^21\|#^21]], [[Graph Traversal Algorithms#^22\|#^22]]) to solve this problem. 
The City when converted into a graph is not an Euler Graph, hence no Euler Path exist.
![KonigsbergBridgesGraph.webp](/img/user/Vaulted%20Images/KonigsbergBridgesGraph.webp)
Hence there exists no solution i.e., There is no way to navigate the city through all the 7 bridges but only using each bridge just once.

> ***Shortcut to find Euler Circuit/Graph***: To find Eulerian Graphs, check if graph is connected and has no odd degree vertices. If yes, then it is an Eulerian Graph.

> ***Shortcut to find Euler Path***: To find Eulerian Path, check if graph is connected, if yes then see if two vertices a & b are connected & the only two distinvt odd vertices in the graph.

---
# Lecture 7: Hamiltonian Cycle & TSP in graph
## Hamiltonian Graph & Hamiltonian Cycle
- Hamiltonian Graph is defined as a graph which contains both Hamiltonian Cycle ([[Graph Traversal Algorithms#^23\|#^23]]) and Hamiltonian Path ([[Graph Traversal Algorithms#^24\|#^24]]. Technically, since every Hamiltonian Cycle is a Hamiltonian Path, just having an Hamiltonian Cycle is good enough.
- TSP here means: Travelling Salesman Problem. It is solved by Floyd Warshall Algorithm.
- Sufficient Conditions for Hamiltonian Cycles:
	1. ***==DIRAC's Theorem==***: Graph with $\large n\geq 3$ vertices and each vertex having degree $\dfrac{n}{2}$ then Hamiltonian Cycle is present.
	2. ***==ORE's Theorem==***:Graph with $\large n \geq 3$ vertices an each with vertex such as the sum of degrees of u and v is always $\large \geq n$  then Hamiltonian Cycle is present as long as u and v are not adjacent.
- The converse of these theorems is not always true. It doesn't need to be either.
- There are no necessary conditions.

---
Next Chapter ---> [[Trees & Spanning Trees\|Trees & Spanning Trees]]
# Footnotes
- ***Euler Graph***: A graph with a closed trail which includes every edge of the graph.
{ #20}

- ***Euler Path***: A path that uses all the edges of the graph exactly once but does not end at the same vertex is started. A graph that contains an Euler Path but not an Euler Circuit is a Semi-Eulerian Graph
{ #21}

- ***Euler Circuit***: A circular path/trail which traverses every edge of a graph exactly once. It can also be defined as an Euler Path that ends on the same vertex it started. A graph said to include an Euler Circuit is called an Euler/Eulerian Graph.
{ #22}

- ***Hamiltonian Cycle***: A cycle that visits each vertex exactly once (except starting vertex which is the only vertex to be repeated).
{ #23}

- ***Hamiltonian/Traceable Path***: A path that visits each vertex exactly once and no vertex is repeated. The path often ends on a diffferent vertex that the one it started from otherwise it will become a Hamiltonian Circuit.
{ #24}


