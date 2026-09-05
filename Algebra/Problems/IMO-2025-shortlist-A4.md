# <span id="problem"></span>Problem
Let $\text{ℤ}\_{\geq 0}$ be the set of all nonnegative integers.  
Let $f: \text{ℤ}\_{\geq 0} \to \text{ℤ}\_{\geq 0}$ be an unbounded function such that, 
if $m$ and $n$ are nonnegative integers satisfying  

$$f(m+n) =  \max \lbrace f(0), f(1), \cdots, f(m+n)\rbrace,$$

then 

$$f(m+n) = f(m) + f(n).$$

Prove that there exist positive integers $A$, $B$, $C$ and $D$ such that 
for all nonnegative integers $n$,  

$$f(An + B) = Cn + D.$$  

We say that $f$ is *unbounded* if for each nonnegative integer $N$, there exists some nonnegative integer $n$ such that $f(n) \geq N$.

# Source

[IMO 2025 Problems](https://www.imo-official.org/problems/2025/)

# Key Idea


# Solution

<details open>

   <summary>Click to open</summary>

Let 

$$\text{ℳ} = \lbrace k \in \text{ℤ}\_{\geq 0} \mid f(k) = \max \lbrace f(0), f(1), \cdots, f(k)\rbrace \rbrace.$$

### <span id="claim1"></span>Claim 1 ($f(0) = 0$ and $f(1) > 0$)
$f(0) = 0$ and $f(1) > 0$.

*Proof.*  
It is apparent that $0 \in \text{ℳ}$.  
Plugging $m=n=0$ we get $f(0+0) = f(0) + f(0)$, or $f(0) = 0$.  

Consider the set $\lbrace n \in  \text{ℕ} \mid f(n) > 0 \rbrace$, which is non-empty because of the unboundedness of $f$.  

Let $k \in \text{ℕ}$ be the smallest number of $\lbrace n \in  \text{ℕ} \mid f(n) > 0 \rbrace$.  
Then $k \in \text{ℳ}$.  

If $k=1$, then we complete the proof.  

Suppose that $k \geq 2$. Then 

$$f(1) = f(2) = \cdots = f(k-1) = 0.$$

However, $0 < f(k) = f(1) + f(k-1) = 0 + 0 = 0$, a contradiction.  

$\square$  

<span id="def_ai"></span>Inspired by [Claim 1](#claim1), construct a sequence $a_0, a_1, \cdots$ as follows.  

1. Define $a_0 = 1$ and $A_1 = \lbrace n \in  \text{ℕ} \mid n > f(a_0) \rbrace$.
2. For each $i \in \text{ℕ}$ we define $a_i$ to be the smallest number of $A_i$ (if $A_i$ has been defined), 
   and then define  $A_{i+1} = \lbrace n \in  \text{ℕ} \mid n > f(a_i) \rbrace$.  
   Note that such an $a_i$ exists because of the unboundedness of $f$ for each $i \in \text{ℕ}$. 

Then $a_i \in \text{ℳ}$ for each $i \in \text{ℤ}\_{\geq 0}$.  
Therefore, we have the following propery:

$$f(a_i) = f(n) + f(a_i - n)$$

for each $i \in \text{ℤ}\_{\geq 0}$ and each nonnegative integer $n \leq a_i$.  

Using this property, we may derive the following claim.

### <span id="claim2"></span>Claim 2
For each $i \in \text{ℤ}\_{\geq 0}$ and each $k \in \text{ℕ}$,  
if 

$$a_i < k < a_{i+1},$$

then

$$0 \< f(k) \< f(a_i).$$

*Proof.*  
Let $k \in \text{ℕ}$ with $a_i < k < a_{i+1}$.  
Then by [the definition](#def_ai) of $a_n$ we get $0 \leq f(k) \leq f(a_i)$.  

Suppose that $f(k) = 0$.  
Then $f(a_{i+1}) = f(a_{i+1} - k) + 0 > f(a_i)$.  
However, $a_{i+1} - k < a_{i+1}$, a contradiction to [the definition](#def_ai) of $a_n$.  

Suppose that $f(k) = f(a_i)$.  
Then $f \in \text{ℳ}$ since, 
otherwise, we would get some $k^\prime \in \text{ℕ}$ such that 
$a_i < k^\prime < k < a_{i+1}$ but $f(k^\prime) > f(k) = f(a_i)$.  
Therefore, $f(k) = f(a_{i}) + f(k - a_{i})$, or $f(k - a_{i}) = 0$.  
Since $0 < k - a_{i} < a_{i+1}$,  

$$ f(a_{i}) \< f(a_{i+1}) = f(a_{i+1} - k + a_i) + f(k - a_{i}) = f(a_{i+1} - k + a_i) $$

However, $a_{i+1} - k + a_i < a_{i+1}$, a contradiction to [the definition](#def_ai) of $a_n$.


$\square$  


We will look into the distribution of $a_0, a_1, \cdots$ with [Claim 2](#claim2).  


### <span id="claim3"></span>Claim 3
For each $i \in \text{ℕ}$ we have

3.1 $a_{i+1} -a_i \geq a_i -a_{i-1}$, and  
3.2 $f(a_{i+1}) - f(a_i) \leq f(a_i) - f(a_{i-1})$

*Proof.*  
First, we will prove Claim 3.1.  
Suppose that $a_{j+1} -a_j < a_j -a_{j+1}$ for some $j \in \text{ℕ}$.  
Then 

$$a_{j-1} < a_{j+1} - a_{j} + a_{j-1} < a_{j}.$$

By [Claim 2](#claim2) we have $f(a_{j+1} - a_{j} + a_{j-1}) < f(a_{j-1})$.  
However, 

$$
\begin{aligned}
f(a_{j+1}) &= f(a_{j+1} - a_{j} + a_{j-1}) + f(a_j - a_{j-1}) \\
&= f(a_{j+1} - a_{j} + a_{j-1}) + f(a_j) - f(a_{j-1}) \\
&\< f(a_{j-1}) + f(a_j) - f(a_{j-1}) = f(a_j),
\end{aligned}
$$

a contradiction [the definition](#def_ai) of $a_n$. 

Hence, Claim 3.1 holds.  

Claim 3.2 is a corollary of Claim 3.1:  

By Claim 3.1 we have $a_{i+1} > a_{i+1} - a_i + a_{i-1} \geq a_i$ for each $i \in \text{ℕ}$.  
By [Claim 2](#claim2) we have 

$$f(a_{i+1}) - f(a_i) + f(a_{i-1}) = f(a_{i+1} - a_i + a_{i-1}) \leq f(a_i),$$

or $f(a_{i+1}) - f(a_i) \leq f(a_{i}) - f(a_{i-1})$.

$\square$  



### <span id="claim4"></span>Claim 4
There exists $l \in \text{ℕ}$ such that 
for each $i \in \text{ℕ}$ with $i > l$ we have $a_{i+1} -a_i = a_i -a_{i+1}$.

*Proof.*  


$\square$  


By [Claim 4](#claim4) we may find $l \in \text{ℕ}$


</details>

# What I Learned
