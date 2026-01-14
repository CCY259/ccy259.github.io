---
layout: single
title:  "Some Problems in Linear Algebra"
date:   2026-01-14 08:30:00 +0800
categories: Linear-Algebra LaTeX
header:
   overlay_color: "#261E47"
excerpt: "Diagonalizable matrices, eigenvalues and eigenvectors"
---

<!-- We need to put space before $$ and after $$ to make sure the equation is on the center. -->


## Problems


**Problem 1.** Let $A, B \in M_n(\mathbb{R})$.
(i) If $A$ is diagonalizable, show that $(A^2 + I_n)^t$ is diagonalizable.
(ii) If $A$ and $B$ are simultaneously diagonalizable, i.e., there exits an invertible matrix $P \in M_n(\mathbb{R})$ such that $P^{-1}AP$ and $P^{-1}BP$ are diagonal matrices, show that $A^2 - B^2$ and $(A + B)(A - B)$ have the same eigenvalues.

	
**Problem 2.** Let $\varphi : \mathbb{R}^3 \to \mathbb{R}^3$ be a linear map. If $\varphi$ has three distinct eigenvalues, show that there exists a vector $u \in \mathbb{R}^3$ such that $u, \varphi(u), \varphi^2(u)$ are linearly independent. Here, $\varphi^2 = \varphi \circ \varphi$.



**Problem 3.** Let $c\in\mathbb{F}$. Show that an $n \times n$ matrix $A$ with characteristic polynomial $c_A(\lambda) = (\lambda - c)^n$ is diagonalizable if and only if $A = c I_n$.


**Problem 4.** Suppose that an $n \times n$ matrix $A$ has $A^k = 0$ for some integer $k > n$. Show that $A^n = 0$.


**Problem 5.** Let $\psi$ and $\phi$ be linear maps on a vector space $V$ over a field. If there exists an ordered basis $\mathcal{B}$ for $V$ such that 
$\lbrack \psi\rbrack_{\mathcal{B}}$ and 
$\lbrack \phi\rbrack_{\mathcal{B}}$ and  are both diagonal matrices, show that 
$\psi \circ \phi = \phi \circ \psi$.

	
**Problem 6.** Let $A, B \in M_n(\mathbb{F})$ be square matrices. If $AB$ is diagonalizable and $A$ is invertible, show that $BA$ is also diagonalizable.

**Problem 7.** Let $V$ be a vector space over a field $\mathbb{F}$. Let $\varphi_1$ and $\varphi_2$ be linear maps on $V$ such that
$$ 
(\varphi_1 \circ \varphi_2)(v) = \varphi_1^2(v)  + 45\varphi_2(v) + v
$$
for every $v \in V$. If $\lambda = 45$ is an eigenvalue of $\varphi_1$, show that $2026$ is an eigenvalue of the linear map $\varphi_1 \circ \varphi_2 - \varphi_2 \circ \varphi_1$.

**Problem 8.** Let $x,y\in\mathbb{F}^{2026}$ be column vectors. Let $A = x^ty$. Show that $A^{2026}$ has at most one nonzero eigenvalue. Then determine that eigenvalue in terms of $\operatorname{tr} A$.
