---
{"dg-publish":true,"permalink":"/K-mers & Genome Sequencing/","tags":["Academics"]}
---

# Index/Contents
[[K-mers & Genome Sequencing#What are K-mers?\|#What are K-mers?]]
[[K-mers & Genome Sequencing#How are De Bruijn Graphs made?\|#How are De Bruijn Graphs made?]]
[[K-mers & Genome Sequencing#What are types of questions asked in the topic?\|#What are types of questions asked in the topic?]]
[[K-mers & Genome Sequencing#Footnotes\|#Footnotes]]

-----
# What are K-mers?
All possible chunks or sub-sequences (of any length K) obtained from a simple reading of any given DNA or Genome Sequence.
Using an analogy of Masonry, K-mers are the individual bricks whereas the Genome Sequence is the fully built wall. The Cement used to bind the bricks into a wall is the De Bruijn Graph.

The De Bruijn graph is a directed graph representing overlaps between sequences and symbols.
We know that an individual symbol is known as a K-mer.

---
# How are De Bruijn Graphs made?
Each K-mer has a length of K.
Each K-mer defines an edge in the graph.
Say that $\large K=3$,
Individual K-mers will be named as: AGT, GTC, TCD etc.
We need to find the individual Genomes (which will act as the vertices in the graph) by splitting the middle term in the K-mers.
If any Genome repeats, then merge them into 1 vertex.
AGT ---> Edge from AG to GT.
GTC ---> Edge from GT to TC.
TCD ---> Edge from TC to CD.
Here, TC is coming up twice, so we make sure to merge it.

---
# How are Whole Sequences Calculated?
1. Take the entire K letters of the first K-mer. This starts the Genome.
2. For the subsequent K-mers, take only the last letter.
3. For the example given previously, the Genome Sequence will be AGTCD.

---
# What are types of questions asked in the topic?
1. [[K-mers & Genome Sequencing#Whole Sequence Given, find K-mers & graph\|#Whole Sequence Given, find K-mers & graph]]
2. [[K-mers & Genome Sequencing#K-mers given, make graph and find sequence\|#K-mers given, make graph and find sequence]]
## Whole Sequence Given, find K-mers & graph
1. Take the entire sequence and we need to be given the value of K.
2. Using the value of K, find the sequence's first K-mer.
3. Use the value of K-1 to find the size of individual vertices.
4. Using both the pieces of information, we can build the De Bruijn Graph.
## K-mers given, make graph and find sequence
Easier variation than the one above simply because this is the conventional question. The technique was developed to build Sequences our of individual K-mers.
1. Take K-mers.
2. Check if ending letters/numbers of one match with the starting of another.
3. Connect the two and build an edge.
4. Continue until all vertices and edges are used up and graph is complete.
5. Now, find the sequence [[K-mers & Genome Sequencing#How are Whole Sequences Calculated?\|#How are Whole Sequences Calculated?]]

---
Next Chapter --->[[Planar Graphs & Planarity Detection\|Planar Graphs & Planarity Detection]]
# Footnotes


