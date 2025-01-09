---
{"dg-publish":true,"permalink":"/Graph Covering/","tags":["Academics"]}
---

# Index/Contents
[[Graph Covering#What is Graph Covering?\|#What is Graph Covering?]]
[[Graph Covering#Footnotes\|#Footnotes]]

-----
# What is Graph Covering?
A Covering is a subgraph of a given graph G which contains either all vertices or all edges of G.
The type that covers all vertices is called the Vertex Covering Graph, the one that covers the edges is known as Edge/Line Covering Graph.

## Line Covering
A subset C of given graph G where every vertex of G is incident with at least one line/edge in C. i.e., each edge that is a part of the subset C ust cover all vertices of the original graph G. Since each vertex is connected to a minimum of 1 vertex, the minimum degree is 1.

#### Minimal Line Covering
A Line Covering where none of the edges can be deleted i.e., a line covering that ceases to be a line covering if any of the edges in C are removed.

#### Minimum Line Covering
A minimal line covering which uses the least number of edges in it i.e the smallest of all mathematically possible minimal line coverings.

## Vertex Covering
Each vertex in subset C covers all the edges in the graph G. Note that for directed grahs, we segregate for outdegree & indegree but in undirected graphs its all the same.

#### Minimal Vertex Covering
A vertex covering where none of the none of the vertices can be deleted i.e., the vertex covering ceases to be a vertex covering if any of the vertices in K are removed.

#### Minimum Vertex Covering
A minimal vertex which uses the least possible number of vertices in it i.e., the smallest of all mathematically possible minimal vertex coverings.

---
# Vertex Cover Problem
The problem is to find the minimum vertex covering of any given graph algorithmically.
We have two ways of doing this:
1. Approximation algorithm
2. Greedy Algorithm

Approximation randomly selects any vertices and removes all surrounding edges whereas Greedy selects the vertices based on a decreasing order of their degree.

---
# Set Covering Problem
> ***Definition***: Given a finite set of elements and a collection of subsets that cover these elements, the goal is to select the minimum number of subsets that cover all the elements.

The problem is known to be NP-hard.

Application: Fire Station Placement Problem

---
Next Chapters --->[[Analytical Graph Theory - Centrality\|Analytical Graph Theory - Centrality]], [[Wagner Theorem\|Wagner Theorem]], [[Network Flow\|Network Flow]]
# Footnotes


