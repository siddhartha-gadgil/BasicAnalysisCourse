---
layout: post
title: "Natural Numbers - Axioms, Addition, Recursion"
date: 2016-01-08 09:54:13 +0530
comments: true
categories:
---

We see, following the text how to axiomatize the natural numbers and define addition and multiplication from these. We elaborate on only one result, namely one allowing us to make recursive definitions.

**Theorem:** Let $X$ be a set, let $x_0\in X$ and let $g(n, x)$ be a function $g: \mathbb{N} \times X \to X$. There is a unique function $f: \mathbb{N}\to X$ such that $f(0)= x_0$ and $\forall n \in\mathbb{N}\ f(n++) = g(n, f(n))$.

**Proof:** The idea is to construct the graph of $f$ as the smallest set containing a specified starting point and closed under a shift.

Let $\mathcal{U} = \\{S \subset \mathbb{N}\times X : (0, x_0)\in S,\ (n, x)\in S\Rightarrow (n++, g(n++, x))\in S\\}$.Consider the set

$$S_0 = \bigcap\limits_{S \in \mathcal{U}} S$$

It is easy to see that $S_0\in \mathcal{U}$.

**Lemma:** For every $n\in \mathbb{N}$, there exist a unique $x_n\in X$ such that $(n, x_n) \in S_0$.

**Proof:** We prove this by induction on $n$. First, let $n=0$. Note that $(0, x_0)\in S$ for all $S\in \mathcal{U}$, and so $(0, x\_0) \in S\_0$. Now suppose $(0, x\_0')\in S\_0$ with $x\_0'\neq x_0$. Let $S = \\{(n, x) \in S\_0: (n, x) \neq (0, x\_0')$. We claim that $S\in \mathcal{U}$.

Firstly, as $(0, x_0) \in S_0$ and $x_0' \neq x_0$, $(0, x_0)\in S$. Next, suppose $(n, x)\in S$, then using $(n++, g(n++, x))\in S_0$ and $n++ \neq 0$, we see that $(n++, g(n++, x))\in S$. Thus $S\in \mathcal{U}$. By definition of $S\_0$, we must have $S\_0 \subset S$. But $(0, x\_0')$ is in $S\_0$ but not $S$, a contradiction. This shows that $x\_0\in X$ is the unique point $x \in X$ such that $(0, x)\in S_0$.

The induction step is similar. Assume $(n, x_n)\in S_0$ and this is the unique point. Then $(n, x_n)\in S$ for all $S \in \mathcal{U}$, from which we deduce that $(n++, g(n++, x))\in S_0$. To show uniqueness, if $x\_{n++}'$ is another point with $(n++, x_{n++}')\in S_0$, then we construct $S$ from $S_0$ by deleting this point. A similar argument to the above then gives a contradiction.
