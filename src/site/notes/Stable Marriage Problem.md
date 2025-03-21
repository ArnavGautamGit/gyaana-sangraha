---
{"dg-publish":true,"permalink":"/Stable Marriage Problem/","tags":["CompSci"]}
---

---
# Solving Stable Marriage Problem using Matching
It is a problem derived from marriages.
Here, we are given two sets of individuals (where sets are defined by genders i.e., a set of cis-males and a set for cis-females).
The task is to optimally marry them according to the preference of each individual in the couple.

### Method 1: Use the Greedy Method w.r.t either set
The Greedy Method requires you to marry individuals of one set (example: boys) with their first preference in the second set.
But this can create "rogue couples" for those men who were lower in the set. 
Since sets cannot be ordered in any specific way, each answer wll have a different order of sets and hence a different matching of couples.
![SMP01.png](/img/user/Vaulted%20Images/SMP01.png)
![SMP02.png](/img/user/Vaulted%20Images/SMP02.png)
In this situation, we see 4 has a higher preference for C than his wife (B) and vice-versa.
This creates a rogue couple.
Stable Marriage Problem in Graph Matching is a problem where both the sets need to be connected (with a bipartite graph) with maximal matching i.e., marry everyone in both sets with no rogue couples.

So far we have seen that Greedy Approach does not work in this scenario since the ordering is not fixed, and men like 1 and 4 will get duped. We need to switch to Dynamic Programming.

### Method 2: Gary Shapley's Algorithm for Stable Marriages
Gary Shapley *proposed* the following Algorithm in 1962:
```
//start
1. Everyone is unmatched at initialisation.
2. For some man *m*, who is unmatched:
	1. w = m's most preferred woman he hasn't proposed to yet.
	2. m' = the man w is engaged to.
	3. m proposes w
	4. IF m' = 0 (i.e., if w is unmatched)
		w and m are engaged.
	5. ELSE IF m > m' (i.e., m is of higher preference to w than m')
		1. w and m are engaged
		2. m' becomes unmatched
	6. ELSE w rejects m and he remains unmatched.
3. Keep running Step 2 as loop until all are matched.
4. Once all are matched, marry them before they change their minds.
//end
```

### Method 3: Hall's Theorem
An algorithm proposed by Philip Hall in 1935, it was a proposed solution to a variant of the stable marriage problem: 
If there is a set of finite girls, each of whom knows several boys, under what conditions can all the girls marry the boys in such a way that each girl marries a boy she knows?

> Let G be a bipartite graph with sets A & B, then G has a matching of A if and only if:
> $$\Large|N(S)| \geq |S| \ \ \ \ \ \ \large \forall \ S \subseteq A $$
>  where, $\large|N(S)|$ is the Neighbours of S, and $\large|S|$ is the cardinality of A. {[[Stable Marriage Problem#^1\|#^1]]}

**==Here, S is a set of elements in set A (given that the mapping is from A --> B) which map to the same element in set B.==**
***Example***: If used for Job Assignment Problem, S is the set of individuals who applies for the same job (each of them may have applied for multiple jobs but there is one common job each has applied to).
#### Applications:
Job Assignment Questions
Personnel Assignment Questions
Creation of Latin Squares

# Footnotes
1. ***Cardinality*** of a particular set refers to the number of elements in that set.
{ #1}
