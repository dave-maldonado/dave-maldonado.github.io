---
layout: post
title: "natural deduction"
date: 2014-02-12 14:54:03 -0500
comments: true
categories: USF logic
---

&rarr; &not; &amp; &or;

This semester I'm taking a class in symbolic logic offered by the Philosophy
department. I decided to take it after seeing the relatively poor coverage of
logic in the Computer Science department's discrete math course.

The class covers propositional and predicate logic and the natural deduction
system using Fitch diagrams. I'm about a month and a half in and we've covered
the basic syntax and deriving proofs in the propositional logic. I thought I'd
share what I've learned so far.

So to start you've probably seen the truth tables for the basic logical
connectives but I'll quickly repeat them here. If this sounds like Greek already
check this blog post out for some logic basics.

<!--more-->

Negation

|&nbsp; P &nbsp;|&nbsp; &not; &nbsp;|
|:-------------:|:-----------------:|
|&nbsp; T &nbsp;|&nbsp; F &nbsp;    |
|&nbsp; F &nbsp;|&nbsp; T &nbsp;    |

---
Conjunction

|&nbsp; P &nbsp;|&nbsp; Q &nbsp;|&nbsp; &amp; &nbsp;|
|:-------------:|:-------------:|:-----------------:|
|&nbsp; T &nbsp;|&nbsp; T &nbsp;|  &nbsp; T &nbsp;  |
|&nbsp; T &nbsp;|&nbsp; F &nbsp;|  &nbsp; F &nbsp;  |
|&nbsp; F &nbsp;|&nbsp; T &nbsp;|  &nbsp; F &nbsp;  |
|&nbsp; F &nbsp;|&nbsp; F &nbsp;|  &nbsp; F &nbsp;  |

---
Disjunction

|&nbsp; P &nbsp;|&nbsp; Q &nbsp;|&nbsp; &or; &nbsp;|
|:-------------:|:-------------:|:----------------:|
|&nbsp; T &nbsp;|&nbsp; T &nbsp;| &nbsp; T &nbsp;  |
|&nbsp; T &nbsp;|&nbsp; F &nbsp;| &nbsp; T &nbsp;  |
|&nbsp; F &nbsp;|&nbsp; T &nbsp;| &nbsp; T &nbsp;  |
|&nbsp; F &nbsp;|&nbsp; F &nbsp;| &nbsp; F &nbsp;  |

---
Conditional

|&nbsp; P &nbsp;|&nbsp; Q &nbsp;|&nbsp; &rarr; &nbsp;|
|:-------------:|:-------------:|:------------------:|
|&nbsp; T &nbsp;|&nbsp; T &nbsp;|  &nbsp; T &nbsp;   |
|&nbsp; T &nbsp;|&nbsp; F &nbsp;|  &nbsp; F &nbsp;   |
|&nbsp; F &nbsp;|&nbsp; T &nbsp;|  &nbsp; T &nbsp;   |
|&nbsp; F &nbsp;|&nbsp; F &nbsp;|  &nbsp; T &nbsp;   |

---
Bi-Conditional

|&nbsp; P &nbsp;|&nbsp; Q &nbsp;|&nbsp; &harr; &nbsp;|
|:-------------:|:-------------:|:------------------:|
|&nbsp; T &nbsp;|&nbsp; T &nbsp;|  &nbsp; T &nbsp;   |
|&nbsp; T &nbsp;|&nbsp; F &nbsp;|  &nbsp; F &nbsp;   |
|&nbsp; F &nbsp;|&nbsp; T &nbsp;|  &nbsp; F &nbsp;   |
|&nbsp; F &nbsp;|&nbsp; F &nbsp;|  &nbsp; T &nbsp;   |
