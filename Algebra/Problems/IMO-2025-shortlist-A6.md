# Problem

Let $S$ be a set of positive integers, possibly infinite, such that no positive integer greater than 1 divides all elements of $S$.  
Determine all non-periodic infinite sequences $a_1, a_2, ...$ of positive integers such that, for all positive integers $n$,  
1. $a_n \leq \left| a_{n+l} - l \right|$ for all $l \in S$, and
2. $a_n = \left| a_{n+l} - l \right|$ for at least one $l \in S$.

We say that an infinite sequence $a_1, a_2, ...$ is *periodic* if there exists a positive integer $t$ such that $a_n = a_{n+t}$ for all positive integers $n$.

# Key idea

# Solution

Let $\text{𝕊}$ denote the set of all subsets $S$ of $\text{ℕ}$ such that no positive integer greater than 1 divides all elements of $S$.  
For any finite non-empty subset $T$ of $\text{ℕ}$, let $\text{gcd}(T)$ denote the greatest common divisor of all elements of $T$.  
Then we have the following result:
### <span id="claim1"></span>Claim 1 (property of $S$)
For any non-empty $S \in \text{𝕊}$ there exists a finite non-empty subset $S^\prime$ of $S$ such that $\text{gcd}\left(S^\prime\right) = 1$.  

*Proof.*   
For the case where $S$ is finite, we have that $\text{gcd}(S) = 1$ because, otherwise, 
$\text{gcd}(S)$ would be a positive integer that divides all elements of $S$ and is also greater than 1.  
In this case we may find $S^\prime = S$.  

For the case where $S$ is infinite, suppose that every finite subset $S^\prime$ of $S$ satisfies that $\text{gcd}\left(S^\prime\right) > 1$.  
Construct an infinite sequence $s_1, s_2, ...$ of elements of $S$ such that  
1. $s_1$ is the smallest number in $S$, and 
2. $s_n$ is the smallest number in $S \backslash \lbrace s_1, s_2, ..., s_{n-1} \rbrace$ , for every $n \in \text{ℕ}$.  

The above process is ordering the elements of $S$.  
For any $n \in \text{ℕ}$ we denote $S_n = \lbrace s_1, s_2, ..., s_n \rbrace$.  
Then we have that $\text{gcd}(S_n) > 1$ for all $n \in \text{ℕ}$, and 

$$ s_1 = \text{gcd}(S_1) \geq \text{gcd}(S_2) \geq \text{gcd}(S_3) \geq ... , $$

which implies that for all sufficiently large $n$ we have $\text{gcd}(S_n) = d$, where $d \in \text{ℕ}$.  
However, $d > 1$ and, by induction, we get that $d$ divides all elements of $S$, a contradiction.  

$\square$


Suppose that there is some $S \in \text{𝕊}$ such that such a non-periodic sequence $a_1, a_2, ...$ of positive integer, 
which may be dependent of $S$, in the problem statement exist.  
In this case, let $S^\star \subseteq S$ denote the subset such that for each $s^\star \in S^\star$ and for all $n \in \text{ℕ}$ 
we have $a_n = \left| a_{n+s^\star} - s^\star \right|$.  
The condition 2 in the problem statement implies that $S^\star$ is non-empty, and therefore, $S$ is non-empty.  


For any $s \in S$ and for any $s^\star \in S^\star$ we denote  

$$
\begin{aligned}
\text{𝒜}(s) &= \lbrace n \in \text{ℕ} \mid a_{n+s} \geq s + a_n \rbrace, \\
\text{ℬ}(s) &= \lbrace n \in \text{ℕ} \mid a_{n+s} \leq s - a_n \rbrace = \text{ℕ} \backslash \text{𝒜}\left( s \right), \\
\text{𝒜}^{\star}(s^\star) &= \lbrace n \in \text{ℕ} \mid a_{n+s^\star} = s^\star + a_n \rbrace , \\
\text{ℬ}^{\star}(s^\star) &= \lbrace n \in \text{ℕ} \mid a_{n+s^\star} = s^\star - a_n \rbrace = \text{ℕ} \backslash \text{𝒜}^{\star}\left( s^\star \right).
\end{aligned}
$$

Then, as stated in the problem, we have that  

$$ \left[ n \in \text{𝒜}(s) \iff n \notin \text{ℬ}(s) \right] \text{  and  } \left[ n \in \text{𝒜}^{\star}(s^\star) \iff n \notin \text{ℬ}^{\star}(s^\star) \right] $$

for any $s \in S$, any $s^\star \in S^\star$ and any $n \in \text{ℕ}$.  

Furthermore, we have the following results.  

### <span id="claim2"></span>Claim 2 (properties of $\text{𝒜}(s)$ and $\text{𝒜}^{\star}(s^\star)$)  
Let $s \in S$, $s^\star \in S^\star$ and $k \in \text{ℕ}$.  Then  
2.1    $k \in \text{𝒜}(s) \iff \left[ a_{k} > s \text{  or  } a_{k+s} > s \right]$.  
2.2    $k \in \text{𝒜}^{\star}(s^\star) \iff \left[ a_{k} > s^\star \text{  or  } a_{k+s^\star} > s^\star \right]$.  
2.3    if $k \in \text{𝒜}(s)$, then $k + ns \in \text{𝒜}$ for all $n \in \text{ℕ}$.  
2.4    if $k \in \text{𝒜}^{\star}(s^\star)$, then $k + ns \in \text{𝒜}^\star$ for all $n \in \text{ℕ}$.  

*Proof.*  
$k \in \text{𝒜}$ implies that $a_{k+s} \geq s + a_{k} > s$.  
Suppose $k+s \in \text{ℬ}$. Then $a_{k+2s} \leq s - a_{k+s}$, which implies that  

$$ a_{k+s} \leq s - a_{k+2s} < s, $$

a contradiction. Hence, $k+s \in \text{𝒜}$. By induction we complete the proof of Claim 2.3.  
In a similar way we can prove Claim 2.4.  
$\square$


We may always find a finite non-empty subset $S^\prime$ of $S$ such that $\text{gcd}\left(S^\prime\right) = 1$ and $S^\prime \cap S^\star \neq \emptyset$ by the following process: 
1. find a finite non-empty subset $S^{\prime\prime}$ of $S$ such that $\text{gcd}\left(S^{\prime\prime}\right) = 1$ by [Claim 1](#claim1)
2. find an element $s^\star \in S^\star$ since $S^\star$ is non-empty
3. let $S^{\prime} = \lbrace s^\star \rbrace \cup S^{\prime\prime}$

Such a $S^{\prime}$ may be written as $S^{\prime} = \lbrace s_1, s_2, ..., s_k \rbrace$ where $k \in \text{ℕ}$, $s_1 \in S^\star$ and $s_1, s_2, ..., s_k \in S$.  
Denote $\text{𝒜}_i = \text{𝒜}(s_i)$ for each $i \in \lbrace 1, 2,..., k \rbrace$ and, especially $\text{𝒜}^{\star}_1 = \text{𝒜}^{\star}(s_1)$.  

The result of a trivial case where $k = 1$ is shown as follows.  

### <span id="claim3"></span>Claim 3 (trivial case of $S^{\prime}$)

3.1 $k = 1$ if and only if $S^\prime = \lbrace 1 \rbrace$.  
3.2 If $k=1$, then $a_{n+1} = a_n + 1$ for all $n \in \text{ℕ}$ (with $a_1 \in \text{ℕ}$).  

*Proof.*  
It is apparent that Claim 3.1 holds.  
Now we will prove Claim 3.2.  
Since $1 \in S^\star$, for all $n \in \text{ℕ}$ we have $n \in \text{𝒜}^{\star}(1) \iff n \notin \text{ℬ}^{\star}(1) $, or  

$$ a_{n+1} = a_n + 1 \iff a_{n+1} \neq 1 - a_n .$$

Suppose $a_{k+1} = 1 - a_k$ for some $k \in \text{ℕ}$. Then $a_{k+1} + a_k = 1$, which is a contradiction 
since $a_k \geq 1$ and $a_{k+1} \geq 1$.  
Hence, $a_{n+1} = a_n + 1$ for all $n \in \text{ℕ}$.  
Since $a_n \in \text{ℕ}$ for all $n \in \text{ℕ}$, it suffices to let $a_1 \in \text{ℕ}$.

$\square$

Before jumping into the discussion of general cases, we state some useful theorems here.  

### <span id="Bézout"></span>Theorem ([Bézout's identity](https://en.wikipedia.org/wiki/B%C3%A9zout%27s_identity))
Let $N = \lbrace n_1, n_2, ..., n_k \rbrace$ be a set of $k$ positive integers with $\text{gcd}(N) = 1$.  
Then there exist $x_1, x_2, ..., x_k \in \text{ℤ}$ 
such that 

$$x_1 n_1 + x_2 n_2 + ... + x_k n_k = 1.$$

### <span id="num_semi"></span>Theorem (a corollary from a fundamental theorem of [Numerical semigroup](https://en.wikipedia.org/wiki/Numerical_semigroup))
Let $N = \lbrace n_1, n_2, ..., n_k \rbrace$ be a set of $k$ positive integers with $\text{gcd}(N) = 1$.  
Then for all sufficiently large $m \in \text{ℕ}$ there exist $x_1, x_2, ..., x_k \in \text{ℕ}$ 
such that 

$$x_1 n_1 + x_2 n_2 + ... + x_k n_k = m.$$

*Proof.*  
This a simple corollary from a fundamental theorem of [Numerical semigroup](https://en.wikipedia.org/wiki/Numerical_semigroup).  

Suppose $k = 1$. Then $\text{gcd}(N) = 1$ implies that $N = \lbrace 1 \rbrace$, 
and for all $m \in \text{ℕ}$ we may find $x_1 = m$ such that $x_1 m = m$.  
Suppose $k > 1$. It suffices to show that for each $r \in \lbrace 1, 2, ..., n_1 - 1 \rbrace$ 
there exist $x_2 \in \text{ℕ}$, ..., $x_k \in \text{ℕ}$ such that $x_2 n_2 + ... + x_k n_k \equiv r \pmod{x_1}$.  
Let $r \in \lbrace 1, 2, ..., n_1 - 1 \rbrace$. 
By [Bézout's identity](#Bézout) we may find $z_1, z_2, ..., z_k \in \text{ℤ}$ such that $\sum^{k}_{i=1} z_i n_i = 1$, or  

$$\sum^{k}_{i=2} (r z_i) n_i \equiv r \pmod{x_1}.$$

Note that for all $t_{r,2}, t_{r,3}, ..., t_{r,k} \in \text{ℤ}$ we have

$$\sum^{k}_{i=2} (r z_i + t_{r,i} x_1) n_i \equiv r \pmod{x_1}.$$

For each $r \in \lbrace 1, 2, ..., n_1 - 1 \rbrace$ and 
for each $i \in \lbrace 2, 3, ..., k-1 \rbrace$ 
we may pick a sufficiently large $t_{r,i}$ such that $x_i = r z_i + t_{r,i} x_1 > 0$ to complete the proof.  

$\square$


### <span id="claim4"></span>Claim 4 
For all sufficiently large $n \in \text{ℕ}$ we have $n \in \text{𝒜}^\star_1 \cap \text{𝒜}_2 \cap ... \cap \text{𝒜}_k = \text{𝒜}^\star_1 \cap \left( \bigcap_{i=2}^{k} \text{𝒜}_i \right)$.

*Proof.*  
We have that there is some $C \in \text{𝒜}^\star_1$ because, otherwise, we get $a_n$ with $a_{n+s_1} = s_1 - a_n$ for all $n \in \text{ℕ}$, 
which is periodic.  

For each $i \in \lbrace 1, 2, ..., k-1\rbrace$ we pick $c_i \in \text{ℕ}$ with $c_i s_i > s_{i+1}$.  
Then by the following process we may show that $ C + \sum_{i=0}^{k-1} (c_i + x_i) s_i + x_k s_k \in $ for all $x_0, x_1, ..., x_k \in \text{ℕ}$:  

By [Claim 2](#claim2) and the fact that $C \in \text{𝒜}^\star_1$ we have $k + y_0 s_1 \in \text{𝒜}^\star$, and $$ a_{k+xs^\star} = a_k + x s^\star > x s^\star $$

for all $x \in \text{ℕ}$.  

$\square$

### <span id="claim4"></span>Claim 4
For all sufficiently large $n \in \text{ℕ}$ we have $a_{n+1} = a_n + 1$.

*Proof.*  
By [Claim 3](#claim3) there exists some $N \in \text{ℕ}$ such that $a_{n + s} \geq a_n + s$ and $a_{n + s^\star} = a_n + s^\star$ for all $n \geq N$.  
Suppose there is some $n \geq N$ such that $a_{n + s} > a_n + s$. Then 

$$ a_n + s s^\star = a_{n + s s^\star} = a_{n + s^\star s} > a_n + s^\star s, $$

a contradiction. Hence, we have that $a_{n + s} = a_n + s$ for all $n \geq N$.

Again, by [Bézout's identity](https://en.wikipedia.org/wiki/B%C3%A9zout%27s_identity) there are some $x \in \text{ℤ}$ and $y \in \text{ℤ}$ such that 
$x s^\star + y s = 1$. Note that it is either $x s^\star > 0 > y s$ or $y s > 0 > x s^\star$.  

For the case where $x s^\star > 0 > y s$ we have

$$ a_{n+1} = a_{n + x s^\star + y s} = a_{n + x s^\star} + y s = a_n + y s + x s^\star = a_n + 1 $$

for all $n \geq N$.  
Similarly, for the case where $x s^\star > 0 > y s$ we can also conclude that $a_{n+1} = a_n + 1$ for all $n \geq N$.

$\square$


### <span id="claim5">Claim 5
For all $n \in \text{ℕ}$ we have $a_{n+1} = a_n + 1$.

*Proof.*  
Suppose that $\text{ℬ} \cup \text{ℬ}^\star = \text{ℕ} \backslash (\text{𝒜} \cap \text{𝒜}^\star)$ is non-empty. 
By [Claim 3](#claim3) we know $\text{ℬ} \cup \text{ℬ}^\star$ has a largest number, denoted by $m$.  
Then $m \in \text{ℬ}$ or $m \in \text{ℬ}^\star$ and $m + 1 \in \text{𝒜} \cap \text{𝒜}^\star$.  
Suppose $m \in \text{ℬ}$. Then $m + 1 \in \text{𝒜}$. We have $a_{m + s} \leq s - a_m$ and $a_{m + s} = a_{m+1} + s-1$, 
implying that $a_{m+1} + a_{m} \leq 1$, a contradiction. Hence,  $m \notin \text{ℬ}$.  
In a similar way we have $m \notin \text{ℬ}^\star$.  
After an argument process similar to [Claim 4](#claim4) we complete the proof.  
$\square$

Concluding [the trivial case](#trivial) and [Claim 5](#claim5) we get the only solution is that 
for all $n \in \text{ℕ}$, $a_{n+1} = a_n + 1$ with an initial condition $a_1 \in \text{ℕ}$, or 

$$a_{n} = n + c$$

for some $c \in \text{ℕ} \cup \lbrace 0 \rbrace$.

### What I learned
