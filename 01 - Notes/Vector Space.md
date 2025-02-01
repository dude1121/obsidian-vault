---
tags:
  - mathematics
  - linear-algebra
---
A **vector space** is a set consisting of [[Vector|vector]] [[Element (Mathematics)|elements]] over some field of [[Scalar|scalars]] (this field is typically the [[Real Numbers]] or [[Complex Numbers]] but could really be any set). 

# Proper Definition

A **vector space** (or **linear space**) $V$ over a [[Field (mathematics)|field]] $F$ consists of a [[Set|set]] on which two operations (called **addition** and **scalar multiplication**, respectively) are defined so that for each pair of elements $x$, $y$, in $V$ there is a unique element $x+y$ in $V$, and for each element $a$ in $F$ and each element $x$ in $V$ there is a unique element $ax$ in $V$, such that the following conditions hold:
1) For all $x$, $y$ in $V$, $x+y=y+x$ ([[Commutative Property|commutativity]] of addition)
2) For all $x$, $y$, $z$ in $V$, $(x+y)+z=x+(y+z)$ ([[Associative Property|associativity]] of addition)
3) There exists an element in $V$ denoted by $0$ such that $x+0=x$ for each $x$ in $V$. 
4) For each element $x$ in $V$ there exists an element $y$ in $V$ such that $x+y=0$.
5) For each element $x$ in $V$, $1x=x$.
6) For each pair of elements $a$, $b$ in $F$ and each element $x$ in $V$, $(ab)x=a(bx)$.
7) For each element $a$ in $F$ and each pair of elements $x$, $y$ in $V$, $a(x+y)=ax+ay$.
8) For each pair of elements $a$, $b$ in $F$ and each element $x$ in $V$, $(a+b)x=ax+bx$.
The elements of the field $F$ are called *scalars* and the elements of the vector space $V$ are called *vectors*.

An object of the form $(a_{1},a_{2},\dots,a_{n})$, where the entries $a_{1},a_{2},\dots,a_{n}$ are elements of the field $F$ is called an *n-tuple* with entries from $F$. Two n-tuples $(a_{1},a_{2},\dots,a_{n})$ and $(b_{1},b_{2},\dots,b_{n})$ are said to be equal if $a_{i}=b_{i}$ for $i=1,2,\dots ,n$.