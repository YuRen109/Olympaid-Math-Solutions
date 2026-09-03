# Problem

Let $S$ be a set of positive integers, possibly infinite, such that no positive integer greater than 1 divides all elements of $S$.  
Determine all non-periodic infinite sequences $a_1, a_2, ...$ of positive integers such that, for all positive integers $n$,  
1. $a_n \leq \left| a_{n+l} - l \right|$ for all $l \in S$, and
2. $a_n = \left| a_{n+l} - l \right|$ for at least one $l \in S$.

We say that an infinite sequence $a_1, a_2, ...$ is *periodic* if there exists a positive integer $t$ such that $a_n = a_{n+t}$ for all positive integers $n$.

# Key idea

# Solution

Suppose that such a sequence $a_1, a_2, ...$ in the problem statement exist. 
Then there there is some $s \in S$ such that $a_n \leq \left| a_{n+s} - s \right|$, 
and there is some $s^\star \in S$ such that $a_n = \left| a_{n+s^\star} - s^\star \right|$.

## Trivial case ($s^\star = 1$)

It is apparent that $S$ may be $\{ 1 \}$. 
Therefore, 1 may be an element of $S$.  
Suppose $s^\star = 1$. Then for all $n \in \text{ℕ}$ we have $a_n = \left| a_{n+1} - 1 \right|$, or

$$a_n = a_{n+1} - 1 \text{ or } a_n = 1 - a_{n+1}$$

Since $a_{n+1} \geq 1$ and $a_{n} \geq 1$, we have $a_{n+1} = a_n + 1$ for all $n \in \text{ℕ}$.

## Case where $s^\star > 1$

Suppose $s^\star > 1$.

### Claim 1 (property of $S$)

Let $s^\star \in S$ with $s^\star > 1$. 
Then there is some $s \in S$ such that $\text{gcd}(s^\star,s) = 1$.

*Proof.*  
Suppose there is no $s \in S$ such that $\text{gcd}(s^\star,s) = 1$. 
Then all the elements in $S$ have a common divisor $d > 1$, a contradiction to the property of $S$.  


By Claim 1 we may pick $s \in S$ such that $\text{gcd}(s^\star,s) = 1$. 
Note that $s$ may be 1.  
Let  
$$
A = \left\{ n \in \text{ℕ} |

$$



