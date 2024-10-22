---
{"dg-publish":true,"permalink":"/Primality Testing/","tags":["Mathematics"]}
---


---
# Primality Testing
> Process of testing whether a given number is a [[Prime Numbers\|Prime Number]] or not.

Primality of small numbers under 100 can be tested by checking Divisibility Rules taught in school. Checking for bigger numbers require the use of specific Primality Tests. 

> Note: *If a number fails the any Primality Test, it is a [[Composite Numbers\|composite number]], if it passes the test, the number may or may not be prime (since High Probability $\large \neq$ Proven).*

For the sake of brevity, I will avoid creation of a new note and add some Primality Tests in this note itself.

### Fermat Test
"If a number $\large n$ is prime, $\large n-1$ raised as a power to any base would yield $\large 1 \ mod \ n$."
Mathematically: $$\Large a^{n-1}=1 \ mod \ n$$It is to be noted that while 561 satisfies this test, but it has 17 as a [[Prime Factors\|Prime Factor]], meaning it is composite. Hence it is ***NOT*** 100% full-proof that any number passing these tests will definitely be [[Prime Numbers\|Prime Numbers]].

### Miller-Rabin Test
"If a number $\large n$ is prime, $\large n-1$ must be equal to any $\large m$ multiplied to ($\large 2^K$). For any value of $\large a$ greater than 1 and less than $\large n-1$ , we can compute $\large b_0$ by modding $\large a^m$ with $\large n$ which if  $(\large b_0=+1)$ means $\large n$ is composite and for a resulting value of -1 it means $\large n$ is probably prime. If $\large b_0$ is neither then we mod it with $\large n$ to get $\large b_1$ and so on."

Mathematically: $$\Large n-1 = m \times 2^K$$
$$\Large b_0 = a^m (mod \ n)$$
$$\Large if \ \ b_0 =+1: \ \ n = composite$$
$$\Large if \ \ b_0 =-1: \ \ n = prime$$
$$\Large if \ \ b_0 =neither, \ \ try \  finding \ b_1$$
$$\Large Use: \ \ b_i = (b_{i-1})^2 \cdot(mod \ n)$$



---
# Footnotes