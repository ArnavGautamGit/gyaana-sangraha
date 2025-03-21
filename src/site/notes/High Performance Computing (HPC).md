---
{"dg-publish":true,"permalink":"/High Performance Computing (HPC)/"}
---


---
# High Performance Computing (HPC)
The HPC is built using a Supercomputer or a cluster of a computers, which has the following major parts:
1. ***Compute Nodes***: CPU-GPU combos that can solve & compute.
2. ***Accelerated Compute Nodes***: More CPU-GPU combos that can support the regular ones
3. ***Switch Fabrics***: Switches that help switching among compute nodes and computer clusters
4. ***Parallel File System***: For Memory. There is also an accelerated version & a backup memory system.

and there are many more parts which we don't need to learn much about it.

## How do Supercomputers work?
While regular computers of today can do multiple tasks, around 2-5 at the same time... Supercomputers or HPCs can do a lot bigger tasks much faster & safer. For example: They can actually encrypt and decrypt videos 40,000 30fps videos of 30 seconds each in about the same time (if not faster) than your PC can do the same thing once. 

Supercomputers are able to do this by dividing the task into chunks - and then divided those chunks among the different compute nodes which are like an individual PC in itself and then the HPC will collate the data and give you the output. All computing nodes can work in parallel to one another.
## Programming a Supercomputer/HPC
Supercomputers have a different language you need to program them since they are a scaled-up connected version of multiple computers:
GPUs pre-2007 used [[OpenGL\|OpenGL]] then Nvidia introduced [[Computer Unified Device Archiecture (CUDA)\|Computer Unified Device Archiecture (CUDA)]] in 2007 and two years later (in 2009) the [[OpenCL\|OpenCL]] language was made.
Now OpenCL and CUDA are the most used languages.

---
# Footnotes