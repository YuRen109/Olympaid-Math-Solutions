# Problem

Let $S$ be a set of positive integers, possibly infinite, such that no positive integer greater than 1 divides all elements of $S$.  
Determine all non-periodic infinite sequences $a_1, a_2, ...$ of positive integers such that, for all positive integers $n$,  
1. $a_n \leq \left| a_{n+l} - l \right|$ for all $l \in S$, and
2. $a_n = \left| a_{n+l} - l \right|$ for at least one $l \in S$.

We say that an infinite sequence $a_1, a_2, ...$ is *periodic* if there exists a positive integer $t$ such that $a_n = a_{n+t}$ for all positive integers $n$.

# Key idea

# Solution

Suppose that such a sequence $a_1, a_2, ...$ in the problem statement exist. 
Then for all  $n \in \text{ℕ}$, there is some $s \in S$ such that $a_n \leq \left| a_{n+s} - s \right|$, 
and there is some $s^\star \in S$ such that $a_n = \left| a_{n+s^\star} - s^\star \right|$.  
In the following discussion we use the notion $s^\star$ to represent an element in $S$ such that 
$a_n = \left| a_{n+s^\star} - s^\star \right|$ for all $n \in \text{ℕ}$.

## Trivial case ($s^\star = 1$)

It is apparent that $S$ may be $\lbrace 1 \rbrace$. 
Suppose $S = \lbrace 1 \rbrace$ and $s^\star = 1$. 
Then for all $n \in \text{ℕ}$ we have $a_n = \left| a_{n+1} - 1 \right|$, or

$$a_n = a_{n+1} - 1 \text{  or  } a_n = 1 - a_{n+1}.$$

Since $a_{n+1} \geq 1$ and $a_{n} \geq 1$, we have $a_{n+1} = a_n + 1$ for all $n \in \text{ℕ}$.

## Case where $s^\star > 1$

Suppose $S \neq \emptyset$ and $S \neq \lbrace 1 \rbrace$ and $s^\star > 1$.

### <span id="claim1"></span>Claim 1 (property of $S$)

Let $s^\star \in S$ with $s^\star > 1$. 
Then there is some $s \in S$ such that $\text{gcd}(s^\star,s) = 1$.

*Proof.*  
Suppose there is no $s \in S$ such that $\text{gcd}(s^\star,s) = 1$. 
Then all the elements in $S$ have a common divisor $d > 1$, a contradiction to the property of $S$.  
$\square$

By [Claim 1](#claim1) we may pick $s \in S$ such that $\text{gcd}(s^\star,s) = 1$. 
Note that $s$ may be 1.  
Let  

$$
\begin{aligned}
&\text{𝒜} = \lbrace n \in \text{ℕ} \mid a_{n+s} \geq s + a_n \rbrace, \\
&\text{ℬ} = \lbrace n \in \text{ℕ} \mid a_{n+s} \leq s - a_n \rbrace, \\
&\text{𝒜}^\star = \lbrace n \in \text{ℕ} \mid a_{n+s^\star} = s^\star + a_n \rbrace , \\
&\text{ℬ}^\star = \lbrace n \in \text{ℕ} \mid a_{n+s^\star} = s^\star - a_n \rbrace .
\end{aligned}
$$

Then for all $n \in \text{ℕ}$ we have

$$ n \in \text{𝒜} \iff n \notin \text{ℬ} \text{  and  } n \in \text{𝒜}^\star \iff n \notin \text{ℬ}^\star. $$

### <span id="claim2"></span>Claim 2 (properties of $\text{𝒜}$ and $\text{𝒜}^\star$)
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
First, we prove that $n \in \text{𝒜}$ for all sufficiently large $n \in \text{ℕ}$. (So har we haven't determine what are sufficiently large $n$)  
We have that there is some $k \in \text{𝒜}^\star$ because, otherwise, we get $a_n$ with $a_{n+s^\star} = s^\star - a_n$ for all $n \in \text{ℕ}$, 
which is periodic.  
By [Claim 2](#claim2) we have $k + x s^\star \in \text{𝒜}^\star$, and moreover,  

$$ a_{k+xs^\star} = a_k + x s^\star > x s^\star $$

for all $x \in \text{ℕ}$.  

On the other hand, let $l \in \lbrace 1, 2, ..., s-1 \rbrace$.  
Since $\text{gcd}(s,s^\star) = 1$, by [Bézout's identity](https://en.wikipedia.org/wiki/B%C3%A9zout%27s_identity) there are some $x_0 \in \text{ℤ}$ and $y_0 \in \text{ℤ}$ such that 
$ x_0 s^\star - y_0 s = 1 $, or

$$ k + (l-k) x_0 s^\star = l + (l-k) y_0 s.$$

We have that for any $t \in \text{ℕ}$, $k + x s^\star = l + y s$, where

$$
\begin{aligned}
&x = (l-k) x_0 s^\star + t s, \\
&y = (l-k) y_0 s + t s^\star.
\end{aligned}
$$

For each $l \in \lbrace 1, 2, ..., s-1 \rbrace$ we pick a large enough $t_l \in \text{ℕ}$ such that $x s^\star > s $ and $y \geq 1$. 
Then 

$$ a_{l+ys} = a_{k+xs^*} > x s^\star > s,$$

implying that $l + (y-1) s \in \text{𝒜}$.

By [Claim 2] we have $n \in \text{𝒜}$ for all $n \geq \text{max}_l (l + (y-1) s)$

$\square$

### Claim 4
For all sufficiently large $n \in \text{ℕ}$ we have $a_{n+1} = a_n + 1$.

*Proof.*  

$\square$


### Claim 5
For all $n \in \text{ℕ}$ we have $a_{n+1} = a_n + 1$.

*Proof.*  

$\square$
