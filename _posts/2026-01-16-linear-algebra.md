---
layout: single
title:  "Some Techniques in Linear Algebra"
date:   2026-01-16 08:30:00 +0800
categories: Linear-Algebra LaTeX
header:
   overlay_color: "#261E47"
excerpt: "With Some Challenging Problems"
---

<!-- We need to put space before $$ and after $$ to make sure the equation is on the center. -->


## The dimension problem and its inequality
#### Known results commonly used
Let $V$ and $W$ be finite-dimensional vector spaces over a field.
1. (Subspace Dimension Theorem) 
$$
\dim(V+W) = \dim V + \dim W - \dim (V\cap W).$$
2. (Rank-Nullity Theorem) Let $\psi:V\to W$ be a linear map. Then
$$
\operatorname{rank}\psi + \operatorname{null}\psi = \dim V.
$$
3. $W\subseteq V \Rightarrow \dim W\leq \dim V$.
4. If $W\subseteq V$ and $\mathcal{B} = \{b_1,\dots, b_k\}$ is a basis for $W$, then $\mathcal{B}$ can be extended to a basis $\mathcal{C} = \{b_1,\dots, b_k, b_{k+1},\dots, b_n\}$ for $V$, where $n = \dim V$.
5. Let $v_1,\dots, v_k\in V$ be linearly independent vectors. Then $k\leq \dim V$.

#### Strategies
1. Always simplify the problem using Subspace Dimension Theorem and Rank-Nullity Theorem.
2. When you do not know what is the dimension of a subspace of $V$, you might bound it using $\dim V$.
3. Extending a linearly independent set to a basis is a common approach to deal with dimension problem.
4. If a linear map $\psi$ is involved and you have some elements, you could investigate their images if the elements themselve do not give useful information.
5. When you want to study $\psi(W)$ where $W$ is a subspace of $V$, it is convenient to think about the restriction mapping $\psi|_W$ since $\psi|_W(W) = \psi(W)$. Now we can apply the Rank-Nullity Theorem to $\psi|_W$.

**Example 1.** Let $V$ be a $7$-dimensional vector space. Let $U$ and $W$ be subspaces of $V$ such that $\dim U = 4$ and $\dim W = 5$. Prove that $U \cap W \neq \{0\}$.

**Example 2.** Let $\psi: V \to W$ be a linear map.

(i) Show that there exists a subspace $U$ of $V$ such that $V = \ker\psi \oplus U$.

(ii) Let $\mathcal{B} = \{b_1, \dots, b_k\}$ be a basis for $U$. Use this basis $\mathcal{B}$ to construct a basis for $\operatorname{im}\psi$. Justify your answer.

**Example 3.** Let $\psi: V \to W$ be a linear map and let $U$ be a subspace of $V$. Prove that
$$ 
\dim(\psi(U)) = \dim U - \dim(U \cap \ker \psi). 
$$

**Example 4.** Let $\psi:V\to V$ be linear map on an $n$-dimensional vector space $V$ over a field $\mathbb{F}$. Let $W$ be a subspace of $V$ and let
$$
U =\{v\in V: \psi(x)\in W\}.
$$
(i) Show that $U$ is a subspace of $V$.

(ii) Prove that 
$$
\dim W\leq \dim U \leq \dim W + \operatorname{null}\psi.
$$


## The matrix manipulation
#### Known results commonly used
1. $\det (AB) = \det(A)\det (B)$
2. $\det(\alpha A) = \alpha^n \det(A)$ where $A\in M_n(\mathbb{F})$ and $\alpha \in\mathbb{F}$.
3. $\operatorname{rank}(A+B) \leq \operatorname{rank}(A) + \operatorname{rank}(B)$
4. $\operatorname{rank}(AB)\leq \min\{\operatorname{rank}(A),\operatorname{rank}(B)\}$
5. $\operatorname{rank}(PAQ) = \operatorname{rank}(A)$ where $P$ and $Q$ are invertible matrices.
6. Kernel and image of a linear map are classical subspaces considered when solving problems.
7. Given two linear maps $\psi:U\to V$ and $\phi:V\to W$. Then $\phi\circ \psi = 0$ implies that $\operatorname{im}\psi \subseteq \ker\phi$.


#### Strategies
1. Deduce the result based on the given conclusion. 
2. Always write out something to approach the hypothesis.
3. Usual manipulations:
   - Create the zero: $0 = A - A$.
   - Create the identity: $I_n  = AA^{-1}$.
   - Multiplication on left/right. Be careful that $(A-B)(A+B) = A^2 - B^2 + AB - BA$.
   - Moving terms to LHS/RHS.
   - Scalar multiplication.


**Example 1.** Let $A,B\in M_n(\mathbb{R})$ be matrices such that $A^2 = B^2 = I_n$ and $\det A + \det B = 0$. Show that $\det(A+B) = 0$.

**Example 2.** Let $A\in M_n(\mathbb{R})$ be a matrix of rank $k$ such that $A^2 = A$. Show that $\operatorname{rank}(A-I_n) = n - k$.

**Example 3.** Let $A\in M_{n,m}(\mathbb{R})$ and $B\in M_{m,n}(\mathbb{R})$. If $I_n - AB$ is invertible, show that $I_m-BA$ is invertible.

**Example 4.** Let $V$ and $W$ be finite-dimensional vector spaces over a field $\mathbb{F}$. Let $f:V\rightarrow W$ and $g:W\rightarrow V$ be linear maps such that $f(g(w)) =w$ for all $w\in W$. Show that there exist subspaces $V_1,V_2$ of $V$ which satisfy the following three conditions:
1. $V = V_1\oplus V_2$.
2. $g(f(v)) = 0$ for any $v\in V_1$.
3. $g(f(v)) = v$ for any $v\in V_2$.


