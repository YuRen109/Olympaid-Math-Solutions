# Problem

Let $S$ be a set of positive integers, possibly infinite, such that no positive integer greater than 1 divides all elements of $S$.  
Determine all non-periodic infinite sequences $a_1, a_2, ...$ of positive integers such that, for all positive integers $n$,  
1. $a_n \leq \left| a_{n+l} - l \right|$ for all $l \in S$, and
2. $a_n = \left| a_{n+l} - l \right|$ for at least one $l \in S$.

We say that an infinite sequence $a_1, a_2, ...$ is *periodic* if there exists a positive integer $t$ such that $a_n = a_{n+t}$ for all positive integers $n$.

# Key idea

# Solution

Suppose that such sequences $a_1, a_2, ...$ in the problem statement exist. 
Then there there is some $s \in S$ such that $a_n \leq \left| a_{n+s} - s \right|$, 
and there is some $s^* \in S$ such that $a_n = \left| a_{n+s^*} - s^* \right|$.

## Trivial case ($s^* = 1$)

It is apparent that 1 may be an element of $S$.  
If $a_n =$
