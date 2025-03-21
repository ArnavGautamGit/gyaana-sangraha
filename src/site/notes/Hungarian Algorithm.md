---
{"dg-publish":true,"permalink":"/Hungarian Algorithm/","tags":["Academics"]}
---

---
# Introduction to Hungarian Algorithm
It is also called the Kuhn-Munkres Algorithm, which solves the Assignment Problem (which is a variant of [[Stable Marriage Problem\|Stable Marriage Problem]])

Assignment Problem is defined as:
> Given workers and n tasks, with a cost or benefit for assigning worker to task, the objective is to find an assignment that minimizes (or maximizes) the total cost (or benefit).

---
# Hungarian Algorithm for Weighted Graphs
```
\\start
1. Subtract row minima and column minima.
2. The rows will have at least one zero somewhere.
3. Cover the zeroes with minimum lines.
4. If the number of lines is less than the order of the square matrix then create additional zeroes.
5. List uncovered & twice covered elements. (twice covered are going to be at intersection of lines)
6. Select minima of all uncovered.
7. Subtract it from all uncovered elements.
8. Add that minima selected in step 6 to twice covered elements.
9. You get Hungarian Matrix. Make graph accordingly.
\\end
```

---
# Hungarian Algorithm for Unweighted Graphs
```
\\start
1. Unless given in the question, we can start with any matching, no need for it to be maximal or maximum matching.
2. Find M-alternating paths starting from an eligible, unmatched vertex in set A.
3. Switch the matching & non-matching edges on the alternating path.
4. Do it with any remaining vertex that also fulfils the criteria of step 2.
\\end
```


---
# Footnotes