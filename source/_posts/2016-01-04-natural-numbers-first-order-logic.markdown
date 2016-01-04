---
layout: post
title: "Natural Numbers- First Order Logic"
date: 2016-01-04 17:04:08 +0530
comments: true
categories:
---

We begin by taking a deeper look at the foundations of natural numbers and their arithmetic. Generally students see the formalization of mathematics, in a tradition going back to Euclid, as beginning with _axioms_ or _definitions_. So for instance, one of the axioms concerning the natural numbers can be:

 $$\forall n\ 0 + n = n.$$

Theorems are the logical consequences of the axioms.

But, for the axiomatic approach to make sense, we first need certain _rules_. These are purely syntactic in nature.

### Language: ###
Suppose we want to create an alien version of the natural numbers. We could remove some axioms and add new ones. However, we cannot have _axioms_ such as:

$$\forall n\  0 + n - = \exists \forall.$$

$$3 + (4 - n).$$

Indeed the first is nonsense - it is not a valid mathematical expression. The second is a mathematical expression, but represents a natural number, not an expression that can be true or false. Thus, we need rules for specifying what are
valid mathematical expressions, and also which of these represent _formulas_, i.e., which can be true or false.

###Rules of inference: ###

Once we know what are valid formulas, we can declare some of them to be our axioms, i.e., we declare that they are true. The rules of inference tell us what formulas we can deduce as consequences of others. Thus theorems are consequences of the axioms.

# First-Order Logic:

The logic that underlies the usual foundations of mathematics is called _Predicate Calculus_ or first-order logic. The natural numbers can be represented in first-order logic, as we see briefly below. However, the usual way of viewing natural numbers, and everything else, in mathematics is to describe __Sets__ in first order logic and then view natural numbers as corresponding to certain sets.

## First-order languages

We have to first describe valid mathematical expressions. In first order logic, these are of two kinds, _Terms_ and _Formulas_. Terms represent elements in a fixed _domain of discourse_, such as natural numbers or the collection of all sets, while formulas can be true or false. Both terms and formulas may depend on some variables.

More precisely,

* a first-order language is determined by collections of
  * constants
  * variables (we can assume the variables to always be, say, $x_1$, $x_2$, $x_3$, ...)
  * functions - with a specified degree for each function.
  * predicates (relations) - with a specified degree for each predicate.

* Terms are expressions that can be built recursively by:
  * constants and variables are terms.
  * if $f(x_1, \dots, x_n)$ is a function of degree $n$ and $t_1$, ..., $t_n$ are terms then $f(t_1, \dots, t_n)$ is a term.

* Formulas are expressions that can be built recursively by:
  * if $p(x_1, \dots, x_n)$ is a predicate of degree $n$ and $t_1$, ..., $t_n$ are terms then $p(t_1, \dots, t_n)$ is a formula.
  * If $P$ and $Q$ are formulas, so are $P\wedge Q$, $P \vee Q$, $P \implies Q$, $P\iff Q$ and $\neg P$.
  * If $P$ is a formula and $x$ is a variable, then $\forall x P$ and $\exists x P$ are formulas.

## Rules of inference

Some of the most important rules of inference are as below.

### Tautologies
Tautologies are formulas built from formula variables $P$, $Q$ etc. (i.e., $P$ , $Q$ are variables representing formulas) which are true for all _truth values_ of the variables. For instance, the statement _"P or (not P)"_ is true if $P$ is true and also if $P$ is false. Similarly, we have the tautology $P \implies (Q \implies P)$.

We can deduce (without any axioms) that any formula obtained by substituting formulas for the formula variables in a tautology is true.

### Modus Ponens

The main rule of inference, going back to antiquity, is Modus Ponens: given $P$ and $P \implies Q$, we can deduce $Q$.


## Natural numbers in first-order logic

The natural numbers can be described in first-order logic.

* The language of natural numbers has
  * a single constant $0$.
  * a function $S$ (successor) of degree $1$ and functions $+$, $\cdot$ of degree $2$.
  * a predicate $=$ of degree $2$
* Equality is often taken as part of the logic, so in first-order logic with equality, we are assumed to have a predicate $=$ and some axioms
  * $\forall x\ x = x$
  * $\forall x\forall y\ x = y \implies y = x$
  * $\forall x \forall y\forall z\ (x = y)\wedge (y = z) \implies x = z$
* The Peano axioms for natural numbers in first-order logic are
  * $\forall x\ 0 \neq S(x)$
  * $\forall x,y\ S(x) = S(y) \implies x = y$
  * $\forall x\in \mathbb{N}  x + 0 = x$
  * $\forall x,y\in \mathbb{N}  x + S(y) = S(x + y)$
  * $\forall x\in \mathbb{N}  x \cdot 0 = 0$
  * $\forall x,y\in \mathbb{N}  x \cdot S(y) = x \cdot y + x$

## Natural numbers as sets

We will not pursue in detail the first-order theory of natural numbers, but instead view them as sets. Thus, each natural number is a set, and the set of natural numbers is a set whose elements are sets. Formally, sets are defined as a first-order theory.

The details of axiomatizing natural numbers (as sets), as the details of most of  this course, are in Terence Tao's books Analysis I & II.
