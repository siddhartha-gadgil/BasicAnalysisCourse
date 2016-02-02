---
layout: post
title: "Assignment 3 - Quotients (due Tuesday, February 9, 2016)"
date: 2016-02-02 09:15:48 +0530
comments: true
categories: assignments
---

## Quotients of sets.

Let $A$ be a set and let $\sim\subset A \times A$. We call $\sim$ a binary relation and write $a \sim b$ for $(a, b)\in \sim$.
A subset $S\subset A$ is said to be _closed under $\sim$_ if whenever $x\sim y$ and one of $x$ and $y$ is in $S$, so is the other.

1. For $a\in A$, show that there is a (unique) set $[a]\subset A$ such that
  * $a$ is closed under $\sim$
  * if $S$ is closed under $\sim$ and $a\in S$  then $[a]\subset S$
2. Show that for $x\in A$, $x\in [a]$ if and only if $[x]=[a]$.
3. Conclude that
$\bar{A} = \\{S \subset A: \text{$S = [a]$ for some $a\in A$}\\}$
is a collection of disjoint sets whose union is $A$.
4. Define the map $q: A\to \bar{A}$ by $q(a) = [a]$. Let $B$ be a set and $f: A \to B$ be  a function. Show that the following are equivalent.
  * for all $a, b \in A$, $a\sim b \implies f(a) = f(b)$
  * there is a function $\bar{f} : \bar{A} \to B$ such that $\bar{f} \circ q = f$
