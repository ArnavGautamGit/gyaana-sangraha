---
{"dg-publish":true,"permalink":"/Cache Memory/","tags":["Academics","COA"]}
---


-----
# What is Cache Memory?
- Very fast memory made to balance/buffer the difference of operatioinal speeds between CPU and RAM.
- Cache Memory is made using Static RAM (SRAM) modules whereas the RAM used in Main Memory is made using Dynamic RAM (DRAM) modules.
- Cache Memory is divided into lines (each being 4 to 64 bytes long). Entire line is read in one go.
- Cache lines are sometimes also called blocks.
![Memory Hierarchy.png](/img/user/Vaulted%20Images/Memory%20Hierarchy.png)
There is an L1 cache inside the processor and an L2 cache common for all the different cores/processors of the entire CPU unit.
L2 cache is obviously slower than the L1 cache.

---
# What are Hit-Ratio and Miss-Ratio?
> The ***==Hit-Ratio==*** is the ratio of hits to the total number of references (hits + misses).
> It is a popular measure of performance of any Cache Memory.

$\large Hit \ Ratio = \dfrac{Hits}{Hits + Misses}$
{ #hit}


> ***==Miss-Ratio==*** is the ratio of misses to the total number of references (hits + misses).
> It is a popular measure of accuracy of any Cache Memory.

$\large Miss \ Ratio = \dfrac{Misses}{Hits + Misses}$

***==Termminology==***:
1. ***Hit*** is defined as a memory reference locates the correct word that needed to be fetched by the CPU.
2. ***Miss*** is the situation when the word is found in the main memory and not in the cache.
3. ***Hit Access Time***: Time taken (in clock cycles) to return a cache hit.
4. ***Miss Penalty***: Time taken (in clock cycles) to process a miss.

---
# What is Cache Mapping?
> The transformation of data from main memory to cache memory is called as Mapping.

There are three kinds of mapping:
1. Associative Mapping
2. Direct Mapping
3. Set-Associative Mapping
### Associative Mapping
- Fastest and most flexible
- Stores both Address and content (data) of the memory word.
- Any location in the cache can store any word from main memory.
- ==Scans the entire Cache for the word==
- In case of the cache being full, the decision to which word is to be replaced by the next incoming one is dependent only on the algorithm chosen. Generally FIFO is used.
### Direct Mapping
- Cheaper to implement than Associative Mapping.
- Of the 15 bits, least significant 9 constitute index field and others are tags.
- ==Each Reference needs a specific address of the line/block.==
- All of the words need to have unique Index Address. Same index but unique tags cannot be processed. Similar to Pauli's Exclusion Principle in Quantum Physics.
### Set-Associate Mapping
- Improvement of Direct Mapping
- 2 or more words can be stored under the same index address.
- Each data word is stored together with all its tag and tag-data itens in one word of cache is said to form a set.
- ==Data is scanned for in the set provided in the reference.==

---
# How does Cache Memory Work?
Cache Memory works on two principles:
1. ***==Temporal Locality==***: The files that were recently referenced have a higher probability to be referenced again.
2. ***==Spatial Locality==***: The files that were recently referenced have a higher probability to have their neighbouring files referenced next.

---
# Footnotes


