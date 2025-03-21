---
{"dg-publish":true,"permalink":"/Cut-Sets, Cut-Vertices & Connectivity/","tags":["Academics"]}
---

# Index/Contents
[[Cut-Sets, Cut-Vertices & Connectivity#Terminology used in this chapter\|#Terminology used in this chapter]]
[[Cut-Sets, Cut-Vertices & Connectivity#How to find Articulation Points?\|#How to find Articulation Points?]]
[[Cut-Sets, Cut-Vertices & Connectivity#How are Bridges identified in a graph?\|#How are Bridges identified in a graph?]]
[[Cut-Sets, Cut-Vertices & Connectivity#Footnotes\|#Footnotes]]

-----
# Terminology used in this chapter:
1. ***==Cut-Edge==***: Any edge (except any back edge) whose removal makes the graph disconnected. Also called "bridge". 
2. ***==Cut-Sets==***: Set or Collection of minimum number of edges which need be removed to disconnect a given graph. {see [[Cut-Sets, Cut-Vertices & Connectivity#^1\|#^1]] and [[Cut-Sets, Cut-Vertices & Connectivity#^2\|#^2]]}
3. ***==Cut-Vertex==***: Vertex whose removal makes the graph disconnected. It is also called an "Articulation Point (AP)".
4. ***==Vertex Cut-Set==***: Set or Collection of minimum number of ***VERTICES*** which need be removed to disconnect a given graph.
5. ***==Fundamental Cut-Set==***: Defined only with reference to a Spanning Tree. It is a cut-set of a Spanning Tree
6. ***==Connectivity==***: It is of 2 kinds...
	1. ***Edge Connnectivity***: Number of edges in the smallest possible cut-set.
	2. ***Vertex Connectivity***: Number of vertices in the smallest possible vertex cut-set. Also defined as the number of cut-vertices required to disconnect ther tree.
7. ***==Separable Graph==***: A graph which contains at least one Cut-Vertex/Articulation Point/AP i.e., Any graph is said to be separable if it can be disconnected by removal of simply just one vertex.
8. ***==Bi-Connected Graph==***: A non-separable graph (a graph with no vertices whose removal disconnects the graph i.e., a graph with no Cut-Vertices/Articulation Points/AP) is also called as a ***Bi-connected Graph***.

---
# How to find Articulation Points?
As dicussed in previous headings, Cut-Vertices are called Articulation Points.
There are two ways to find them: (a) Naive approach, (b) Tarjan's Approach

## Naive Approach
```
\\start
For every vertex 'v' do the following:
1. Remove vertex 'V'.
2. Check if the graph is disconnected,
	1. if yes, V is an articulation point.
	2. if no, V is not an articulation point.
3. Add verx 'V' back to the graph.
\\end
```

## Tarjan's Approach
```
\\start
Root of DFS tree is always an AP if it has 2 or more children.
1. Check if Root Node has more than 1 subtree (children)
	1. if yes, Root is an AP.
	2. if no, Root is not an AP.
2. Identify and Exclude all leaf nodes from the tree. Mark them as visited if needed.
3. Check of it has any subgraphs originating from it
	1. If yes, check if there is a back edge from any of its sucessors to ancestors.
		1. if yes, remove node - check if graph is disconnected
			1. if yes, then node is an AP
			2. if no, then node is not an AP
		2. If no, then node is not an AP
	2. If no then node is an AP.
4. If not then check next node in DFS
5. Repeat steps 1-4 until either:
	1. AP is found OR
	2. All nodes have been visited
\\end
```

---
# How are Bridges identified in a graph?
Bridges (as discussed before) are edges whose removal will disconnect the graph.
We know that APs are points which also disconnect the graph if they are removed. We can utilise the connection of the concepts to figure out a shortcut very easily.

Remove the AP and see which of the subtrees of the DFS tree get disconnected. If one of them has a back edge to an ancestor of the AP and one doesn't, it means the sub tree with no back edge will get disconnected from the graph upon removal of the AP. Now add the AP back and see which edge connected the AP to that specific sub tree with no back edge to any of the AP's ancestor vertices. This edge is the Bridge Edge.

In simpler words, the edge connected to AP that leads to any subtree of AP which lacks a back edge to any of its ancestors is a Bridge Edge since the removal of that edge would disconnect that particular subtree from the graph. Note that back edges are never counted as a Bridge Edge.

---
Next Chapter --->[[K-mers & Genome Sequencing\|K-mers & Genome Sequencing]]
# Footnotes
1. Using the definition of a Cut-Set, we can say that a cut-edge is a cut-set with only a single edge as its lone element.
{ #1}

2. Any subset of a cut-set cannot be a cut-set.
{ #2}

3. if Vertex Connectivity is $\large K(G)$, Edge Connectivity is $\large \lambda(G)$ and Smallest Vertex Degree is $\large \delta(G)$ then the relation between them is ==$\large K(G) \leq \lambda(G) \leq \delta(G)$==
{ #3}

4. A Block of a graph G is a maximally connected subgraph of G that has no cut-vertex.
{ #4}


