---
layout: post
title: "Natural Numbers - Axioms, Addition, Recursion"
date: 2016-01-08 09:54:13 +0530
comments: true
categories:
---

We see, following the __text__ how to axiomatize the natural numbers and define addition and multiplication from these. We elaborate on only one result, namely one allowing us to make recursive definitions.

**Theorem:** Let $X$ be a set, let $x_0\in X$ and let $g(n, x)$ be a function $g: \mathbb{N} \times X \to X$. There is a unique function $f: \mathbb{N}\to X$ such that $f(0)= x_0$ and $\forall n \in\mathbb{N}\ f(n++) = g(n, f(n))$.

**Proof:** The idea is to construct the graph of $f$ as the smallest set containing a specified starting point and closed under a shift.

Let $\mathcal{U} = \\{S \subset \mathbb{N}\times X : (0, x_0)\in S,\ (n, x)\in S\Rightarrow (n++, g(n++, x))\in S\\}$. Note that $\mathcal{U}$ is non-empty as $\mathbb{N}\times X \in \mathcal{U}$.

Consider the set

$$S_0 = \bigcap\limits_{S \in \mathcal{U}} S$$

It is easy to see that $S_0\in \mathcal{U}$.

**Lemma:** For every $n\in \mathbb{N}$, there exist a unique $x_n\in X$ such that $(n, x_n) \in S_0$.

**Proof:** We prove this by induction on $n$. First, let $n=0$. Note that $(0, x_0)\in S$ for all $S\in \mathcal{U}$, and so $(0, x\_0) \in S\_0$. Now suppose $(0, x\_0')\in S\_0$ with $x\_0'\neq x_0$. Let $S = \\{(n, x) \in S\_0: (n, x) \neq (0, x\_0')$. We claim that $S\in \mathcal{U}$.

Firstly, as $(0, x_0) \in S_0$ and $x_0' \neq x_0$, $(0, x_0)\in S$. Next, suppose $(n, x)\in S \subset S_0$, then  $(n++, g(n++, x))\in S_0$. Further, as $n++ \neq 0$, we see that $(n++, g(n++, x)) \neq (0, x_0')$. Hence $(n++, g(n++, x))\in S$. Thus $S\in \mathcal{U}$.

By definition of $S\_0$, as $S\in \mathcal{U}$, $S\_0 \subset S$. But $(0, x\_0')$ is in $S\_0$ but not $S$, a contradiction. This shows that $x\_0\in X$ is the unique point $x \in X$ such that $(0, x)\in S_0$.

The induction step is similar. Assume $(n, x_n)\in S_0$ and this is unique, i.e., $(n, x)\in S_0 \implies x = x_n$. Then $(n, x_n)\in S$ for all $S \in \mathcal{U}$, from which we deduce that $(n++, g(n++, x))\in S_0$. To show uniqueness, suppose $x\_{n++}'\in X$ is a point with $(n++, x\_{n++}')\in S\_0$ but $x\_{n++}' \neq x\_{n++} := g(n++, x)$. Let $S = S_0 \setminus \\{(n++, x_{n++}')\\}$. We again show that $S \in \mathcal{U}$ and obtain a contradiction to $S_0 \subset S$.

Namely, as $(0, x_0) \in S_0$ and $n++ \neq 0$, $(0, x_0)\in S$. Next, suppose $(m, x)\in S \subset S_0$, then  $(m++, g(m++, x))\in S_0$. If $(m++, g(m++, x)) \notin S$, then we must have $(m++, g(m++, x)) = (n++, x\_{n++}')$. Hence $n = m$, so $x = x\_n$. It follows that $x\_{n++}' = g(m++, x) = g(n++, x\_n)$, a contradiction. Thus, if $(m, x)\in S$, $(m++, g(m++, x)) \in S$, completing the proof that $S\subset \mathcal{U}$, and contradicting $S_0 \subset S$.

This completes the proof of the lemma.

$$\tag*{$\square$}$$

To prove the theorem, we define the function $f$ by $f(n) = x_n$. As we will see, in terms of set theory the function just corresponds to the set $S_0$. It is straightforward to show by induction than $f$ indeed has the desired properties, and is the unique such function.

$$\tag*{$\square$}$$
