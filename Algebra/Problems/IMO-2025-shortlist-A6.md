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

We may always find a finite non-empty subset $S^\prime$ of $S$ such that $\text{gcd}\left(S^\prime\right) = 1$ and $S^\prime \cap S^\star \neq \emptyset$ by the following process: 
1. find a finite non-empty subset $S^{\prime\prime}$ of $S$ such that $\text{gcd}\left(S^{\prime\prime}\right) = 1$ by [Claim 1](#claim1)
2. find an element $s^\star \in S^\star$ since $S^\star$ is non-empty
3. let $S^{\prime} = \lbrace s^\star \rbrace \cup S^{\prime\prime}$

Such a $S^{\prime}$ may be written as $S^{\prime} = \lbrace s_1, s_2, ..., s_k \rbrace$ where $k \in \text{ℕ}$, $s_1 \in S^\star$ and $s_1, s_2, ..., s_k \in S$.  
Denote $\text{𝒜}_i = \text{𝒜}(s_i)$ for each $i \in \lbrace 1, 2,..., k \rbrace$ and, especially $\text{𝒜}^{\star}_1 = \text{𝒜}^{\star}(s_1)$.  

The result of a trivial case where $k = 1$ is shown as follows.  

### <span id="claim2"></span>Claim 2 (trivial case of $S^{\prime}$)

2.1 $k = 1$ if and only if $S^\prime = \lbrace 1 \rbrace$.  
2.2 If $k=1$, then $a_{n+1} = a_n + 1$ for all $n \in \text{ℕ}$ (with $a_1 \in \text{ℕ}$).  

*Proof.*  
It is apparent that Claim 2.1 holds.  
Now we will prove Claim 2.2.  
Since $1 \in S^\star$, for all $n \in \text{ℕ}$ we have $n \in \text{𝒜}^{\star}(1) \iff n \notin \text{ℬ}^{\star}(1) $, or  

$$ a_{n+1} = a_n + 1 \iff a_{n+1} \neq 1 - a_n .$$

Suppose $a_{k+1} = 1 - a_k$ for some $k \in \text{ℕ}$. Then $a_{k+1} + a_k = 1$, which is a contradiction 
since $a_k \geq 1$ and $a_{k+1} \geq 1$.  
Hence, $a_{n+1} = a_n + 1$ for all $n \in \text{ℕ}$.  
Since $a_n \in \text{ℕ}$ for all $n \in \text{ℕ}$, it suffices to let $a_1 \in \text{ℕ}$.

$\square$

Before jumping into the discussion of general cases, we state some useful theorems here.  

### Theorem ([Bézout's identity](https://en.wikipedia.org/wiki/B%C3%A9zout%27s_identity))
Let $N = \lbrace n_1, n_2, ..., n_k \rbrace$ be a set of $k$ positive integers with $\text{gcd}(N) = 1$.  
Then there exist $x_1 \in \text{ℤ}$, $x_2 \in \text{ℤ}$, ..., $x_k \in \text{ℤ}$ 
such that 

$$x_1 n_1 + x_2 n_2 + ... + x_k n_k = 1.$$

### Theorem (a corollary from a fundamental theorem of [Numerical semigroup](https://en.wikipedia.org/wiki/Numerical_semigroup))
Let $N = \lbrace n_1, n_2, ..., n_k \rbrace$ be a set of $k$ positive integers with $\text{gcd}(N) = 1$.  
Then for all sufficiently large $m \in \text{ℕ}$ there exist $x_1 \in \text{ℤ}$, $x_2 \in \text{ℤ}$, ..., $x_k \in \text{ℤ}$ 
such that 

$$x_1 n_1 + x_2 n_2 + ... + x_k n_k = m.$$

### <span id="claim3"></span>Claim 2 (properties of $\text{𝒜}$ and $\text{𝒜}^\star$)
Let $k \in \text{ℕ}$.  Then  
2.1    if $k \in \text{𝒜}$, then $k + ns \in \text{𝒜}$ for all $n \in \text{ℕ}$.  
2.2    if $k \in \text{𝒜}^\star$, then $k + ns \in \text{𝒜}^\star$ for all $n \in \text{ℕ}$.  

*Proof.*  
$k \in \text{𝒜}$ implies that $a_{k+s} \geq s + a_{k} > s$.  
Suppose $k+s \in \text{ℬ}$. Then $a_{k+2s} \leq s - a_{k+s}$, which implies that  

$$ a_{k+s} \leq s - a_{k+2s} < s, $$

a contradiction. Hence, $k+s \in \text{𝒜}$. By induction we complete the proof of Claim 2.1.  
In a similar way we can prove Claim 2.2.  
$\square$

### <span id="claim3"></span>Claim 3
For all sufficiently large $n \in \text{ℕ}$ we have $n \in \text{𝒜}$ and $n \in \text{𝒜}^\star$.

*Proof.*  
First, we will prove that $n \in \text{𝒜}$ for all sufficiently large $n \in \text{ℕ}$. (So har we haven't determine what are sufficiently large $n$)  
We have that there is some $k \in \text{𝒜}^\star$ because, otherwise, we get $a_n$ with $a_{n+s^\star} = s^\star - a_n$ for all $n \in \text{ℕ}$, 
which is periodic.  
By [Claim 2](#claim2) we have $k + x s^\star \in \text{𝒜}^\star$, and moreover,  

$$ a_{k+xs^\star} = a_k + x s^\star > x s^\star $$

for all $x \in \text{ℕ}$.  

On the other hand, let $l \in \lbrace 1, 2, ..., s-1 \rbrace$.  
Since $\text{gcd}(s,s^\star) = 1$, by [Bézout's identity](https://en.wikipedia.org/wiki/B%C3%A9zout%27s_identity) there are some $x_0 \in \text{ℤ}$ and $y_0 \in \text{ℤ}$ such that 
$x_0 s^\star - y_0 s = 1$, or

$$ k + (l-k) x_0 s^\star = l + (l-k) y_0 s.$$

We have that $k + x_t s^\star = l + y_t s$, where

$$
\begin{aligned}
&x_t = (l-k) x_0 s^\star + t s, \\
&y_t = (l-k) y_0 s + t s^\star,
\end{aligned}
$$

for any $t \in \text{ℕ}$.

For each $l \in \lbrace 1, 2, ..., s-1 \rbrace$ we pick a large enough $t_l \in \text{ℕ}$ such that $x_{t_l} s^\star > s$ and $y_{t_l} \geq 1$. 
Then 

$$ a_{l+y_{t_l} s} = a_{k+x_{t_l} s^*} > x_{t_l} s^\star > s,$$

implying that $l + (y_{t_l} - 1) s \in \text{𝒜}$.

By [Claim 2](#claim2) we have $n \in \text{𝒜}$ for all $n \geq \max_{l} (l + (y_{t_l} - 1) s)$.  
Next, we will prove that $n \in \text{𝒜}^\star$ for all sufficiently large $n \in \text{ℕ}$.  
Since we have proven that $n \in \text{𝒜}$ for all sufficiently large $n \in \text{ℕ}$, we can pick some $p \in \text{𝒜}$ and, 
after a similar argument, we can complete this part.  

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
