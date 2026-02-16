---
layout: single
title:  "Kronecker Lemma"
date:   2026-02-16 08:30:00 +0800
categories: Probability Analysis
header:
   overlay_color: "#261E47"
toc: false
---

<!-- We need to put space before $$ and after $$ to make sure the equation is on the center. -->

## Statement
Let $(a_n)$ and $(x_n)$ be real sequences such that $(a_n)$ is increasing and diverges to $\infty$ and the series $\sum_{n=1}^{\infty} \frac{x_n}{a_n}$ converges. Then 
$$
\frac{1}{a_n} \sum_{m=1}^n x_m \to 0
$$
as $n\to \infty$.

**Proof.**   Let $a_0 = 0$ and $b_0 = 0$. For $m \ge 1$, let $b_n = \sum_{k=1}^n \frac{x_k}{a_k}$.
Since $b_m - b_{m-1} = \frac{x_m}{a_m}$, we can write $x_m = a_m(b_m - b_{m-1})$ for $m\geq 1$. So
$$
\begin{aligned}
a_n^{-1} \sum_{m=1}^n x_m &= a_n^{-1} \sum_{m=1}^n a_m(b_m - b_{m-1})  \\
&= a_n^{-1} \left( \sum_{m=1}^n a_m b_m - \sum_{m=1}^n a_m b_{m-1} \right)  \\
&= a_n^{-1} \left( a_n b_n + \sum_{m=1}^{n-1} a_m b_m - \sum_{m=1}^n a_m b_{m-1} \right)  \\
&= a_n^{-1} \left( a_n b_n + \sum_{k=2}^n a_{k-1} b_{k-1} - \sum_{m=1}^n a_m b_{m-1} \right) & (\text{Reindex by setting } k=m+1) \\
&= b_n - a_n^{-1} \sum_{m=1}^n (a_m - a_{m-1})b_{m-1} & (\text{Note that } b_0=0)
\end{aligned}
$$

Let $c_n = a_n^{-1} \sum_{m=1}^n (a_m - a_{m-1})b_{m-1}$ for $n\geq 1$ and let $\ell$ be the limit of $b_n$. Since $(b_n)$ is bounded, the supremum $B:=\sup_n \lvert b_n\rvert$ exists. 

Now it suffices to show that $c_n\to\ell$ as $n\to \infty$.  Let $\varepsilon > 0$. Then there exists an integer $M$ such that for all $m \geq M$, $\lvert b_m - \ell\rvert < \varepsilon$. Since $\frac{2Ba_M}{a_n}\to 0$ as $n\to \infty$, there exists an integer $N$ such that for all $n \geq N$, $\frac{2Ba_M}{a_n} < \varepsilon$.

Note that $\sum_{m=1}^n \frac{a_m - a_{m-1}}{a_n} = \frac{a_n - a_0}{a_n} = 1$. 
For any $$n \geq \max\{M,N\}$$,
$$
\begin{aligned}
|c_n -\ell| &=
\left| \sum_{m=1}^n \frac{a_m - a_{m-1}}{a_n} b_{m-1} - 1\cdot \ell \right| 
\\
&=
\left| \sum_{m=1}^n \frac{a_m - a_{m-1}}{a_n} b_{m-1} - \frac{a_m - a_{m-1}}{a_n}\cdot \ell \right| 
\\
&= \left| \sum_{m=1}^n \frac{a_m - a_{m-1}}{a_n} (b_{m-1} - \ell) \right| \\
&\leq \sum_{m=1}^n \frac{a_m - a_{m-1}}{a_n} |b_{m-1} - \ell|\\
&= \sum_{m=1}^M \frac{a_m - a_{m-1}}{a_n} |b_{m-1} - \ell| + \sum_{m=M+1}^n \frac{a_m - a_{m-1}}{a_n} |b_{m-1} - \ell| \\
&< \frac{1}{a_n} \left(\sum_{m=1}^M (a_m - a_{m-1})\right) 2B + \left( \sum_{m=M+1}^n \frac{a_m - a_{m-1}}{a_n} \right) \varepsilon & (\text{Note that $|b_{m-1}-\ell| \leq 2B$}) \\
&= \frac{2Ba_M}{a_n}  + \frac{a_n - a_M}{a_n} \varepsilon  \\
&< \varepsilon + \frac{a_n}{a_n} \varepsilon
\\
&= 2\varepsilon,
\end{aligned}
$$
Since $\varepsilon$ is arbitrary, this completes the proof.  $\blacksquare$

### Remarks
- Sometimes it is helpful to "extend" the sum (e.g. $a_n = 0$) to simplify formulas. For example, it is hard to get the equality $\sum_{m=1}^n \frac{a_m - a_{m-1}}{a_n} = \frac{a_n - a_0}{a_n} = 1$ if we only consider $\sum_{m=2}^n \frac{a_m - a_{m-1}}{a_n}$. 
- Always simplify series of differences using telescoping sum.
- There are some bounding strategies:
   1. Triangle inequality
   2. Cut out negative terms
   3. Use supremum (if exists)
   4. Use Epsilon language
- The common technique when using Epsilon language is by splitting the sum as follows:

$$
\sum_{k=1}^n \cdots = \underbrace{\sum_{k=1}^N \cdots}_{\text{Other approaches (e.g. supremum)}} + \underbrace{\sum_{k=N+1}^{n} \cdots}_{\text{Bound using Epsilon language}} 
$$
