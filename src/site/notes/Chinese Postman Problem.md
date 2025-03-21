---
{"dg-publish":true,"permalink":"/Chinese Postman Problem/","tags":["Academics"]}
---

# Index/Contents
[[Chinese Postman Problem#What is Chinese Postman Problem?\|#What is Chinese Postman Problem?]]
[[Chinese Postman Problem#How to solve the Chinese Postman Problem?\|#How to solve the Chinese Postman Problem?]]
[[Chinese Postman Problem#Footnotes\|#Footnotes]]

-----
# What is Chinese Postman Problem?
It is a problem first proposed in 1962 by a Chinese Mathematician, Kuan Mei-Ko. Hence it is problem which is Chinese and not the Postman.
The Problem is to try to find a way such that the Postman is able to deliver mail to all cities in the minimum distance travelled i.e., a Eulerian Trail (Euler Circuit) around the graph using edges with minimum possible edge weight.

We learnt about Euler Circuit in [[Graph Traversal Algorithms#^22\|Graph Traversal Algorithms#^22]] 

Chinese Postman Problem at its core is a variation of the Eulerian Circuit problem which is defined specifically for undirected, connected graphs.

# How to solve the Chinese Postman Problem?
The easiest way to solve the Chines Postman Problem is to find the Eulerian Circuit in the graph. The solution is the same Circuit regardless of the fact that the graph is weighted or not (unless there are more than one Euler Circuit present - then either the graph has to be weighted or more than one solutions must be accepted).

### How are Euler Circuits found?
Since Euler Circuits cover all the edges of a graph without repeating them, Euler Graphs (which contain an Euler Cycle) should be easy to draw without lifting the pen off the paper in one go.

For bigger graphs, check if there are odd-degree vertices in the graph. If yes, then the graph is very less likely to be Euler. If there are 2 odd-degree vertices in the graph, the graph is only semi-Euler. 

# What if the Given Graph is not an Euler Graph?
If the given graph is not an Euler Graph, then we have to check if the graph is weighted or not.
If the graph is weighted, note which edges need to be repeated and add their edge weight with every repetition.
If the graph is unweighted, count the number of edges (count the repeated ones as many times as they are repeated).

Another approach is to add edges to make the graph Euler.
![Chinese Postman Problem.png](/img/user/Vaulted%20Images/Chinese%20Postman%20Problem.png)

Next Chapter --->[[Cut-Sets, Cut-Vertices & Connectivity\|Cut-Sets, Cut-Vertices & Connectivity]]
# Footnotes


