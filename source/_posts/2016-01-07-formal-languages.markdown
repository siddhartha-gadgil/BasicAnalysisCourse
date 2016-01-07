---
layout: post
title: "Formal Languages"
date: 2016-01-07 09:51:26 +0530
comments: true
categories:
---

Just like a Dictionary, which can define words only in terms of other words, foundations of mathematics _cannot_ be fully self-contained, but _must_ make reference to the external world. This is done through _rules_ governing the foundations. However, what we can, and do, insist on is that the collection of rules is small and clean, so that

* they can be communicated to at least all scientifically literate people, who will all interpret them the same way.
* they can be machine implemented, and we can be convinced that the machine implementation of the rules coincides with our understanding of them.

Such rules are generally specified in terms of a _Formal Grammar_.

### Formal Grammars

A formal grammar has an alphabet $\mathcal{A}$ (mathematically a set), whose elements are letters. This may be finite or infinite, but in the latter case we must have agreement (as above) on what are the letters. Further, these letters can be divided into classes (e.g. variables, constants, paranthesis). We should be able to agree upon and determine when a letter belongs to a given class.

An _expression_ is a finite sequence of letters. We can _concatenate_ two expressions, i.e., write one after the other. In a formal language,

* we define certain distinguished classes of expressions (e.g. Terms, Formulas) by specifying how these can be built by (non-trivial) concatenation from
  * letters in a specific class,
  * specific letters,
  * words in appropriate distinguished classes, including in general the class being defined.
* as words from which a given word is built must be shorter, we can determine when a word belongs to a distinguished class.
* we can more generally _pattern match_ on one or more words: for example, given two words, we can determine whether
**the two words are of the form $P$ and $P \implies Q$ where $P$ and $Q$ are formulas.**

### Syntactic foundations of mathematics: First-order logic and Set theory.

As sketched earlier, we can define first-order languages in a formal grammar, with two distinguished classes of expressions - terms and formulas. A theory consists of a first order language together with a collection of formulas, which we call the _Axioms_ of the theory. Typically, we insist that these include a set of _logical axioms_.

Rules of deduction (inference), i.e., rules telling us how to deduce formulas from other formulas, can be described in terms of pattern matching and concatenation as above. Mathematics has foundations the language and axioms of _Set Theory_. In principle, any mathematical theorem can be written in this language, and a proof can be written as a sequence of applications of the rules of deduction starting with the axioms of set theory and the logical axioms.
