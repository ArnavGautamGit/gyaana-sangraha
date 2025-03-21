---
{"dg-publish":true,"permalink":"/Run CUDA on Google Colaboratory/"}
---


---
# Run CUDA on Google Colaboratory
[[Google Colaboratory\|Google Colaboratory]] is a colaborative research platform run by [[Google\|Google]] and it can be used to run [[Computer Unified Device Archiecture (CUDA)\|Computer Unified Device Archiecture (CUDA)]] on its GPU which is provided by them.

This note describes the process to do so.

Step 1: Run the command to check if the GPU is an [[NVIDIA\|NVIDIA]] one.
```bash
!nvcc --help
```

Step 2: Run the comand to create a new file in a separate code block. Q1 is used so that it easier for me to do the [[Assignment - 10 (Answers)\|Assignment - 10 (Answers)]] for my Internship.
```bash 
%%writefile q1.cu

# Add your code here which needs to be inside q1.cu 
```

Step 3: Run the command to confirm q1.cu exists
```bash
!ls
```

Step 4: Run the command to compile the code
```bash
!nvcc -o Q1 q1.cu
```

Step 5: Run the file
```bash
!./Q1
```

---
# Footnotes