---
tags:
  - mathematics
  - set-theory
  - proofs
---
A **set** in mathematics is any well-defined collection of objects called [[Element (Mathematics)|elements]]. In this context, well-defined means that it is possible to decide if a given object belongs to the set or not.

A set can be written as a list of elements surrounded in curly braces.
$$
\{1,2,3\}
$$
The order of the elements are not important, and repeated elements may be ignored. Therefore, the set
$$
\{2,3,1,1,3\}
$$
is equivalent to the set above it.

Typically uppercase letters denote sets and lowercase letters denote elements within a given set. An element is stated to be within a set by the notation,
$$
x \in A
$$
This is read as "x is an element of A". If $x$ is not an element in $A$, then we write
$$
x \notin A
$$
# Describing a Set

Sometimes a set may be defined as a finite list of the elements it contains. E.g.,
$$
A=\{1,2,3,4\}
$$
Other times it is inconvenient to list every single member of a set, so we can instead describe it by specifying a property that all elements within the set have. This is expressed with the notation $\{x|P(x)\}$ which is read as "the set of all $x$ such that $P(x)$". As an example, $\{x\text{ }|\text{ }x\text{ is a positive integer less than 4}\}$, describes the set $\{1,2,3\}$. 

If a set follows a certain pattern and continues up to a certain limit, an ellipsis may be used to indicate this. As an example, the set of all positive numbers from $1-1000$ might be described as,
$$
A=\{1,2,3,\dots,1000\}
$$

# Cardinality

![[Cardinality]]

# Commonly Used Sets

Some sets are referenced so often that there exists shorthand for these sets. These sets include:

The [[Empty Set|empty set]]. A set with no members (i.e. a set with cardinality $0$) is known as the "empty set". This set is typically denoted as $\emptyset$ where $\emptyset=\{  \}$. 

The [[Natural Numbers|natural numbers]] are defined as
$$
\mathbb{N}=\{ 1,2,3,4,\dots \}
$$
The [[Integer|integers]] are defined as
$$
\mathbb{Z}=\{ \dots,-3,-2,-1,0,1,2,3,\dots \}
$$
The [[Rational Numbers|rational numbers]] are defined as
$$
\mathbb{Q}=\left\{ \frac{p}{q}\text{ }|\text{ }p,q \in \mathbb{Z}, q\neq 0 \right\}
$$
The [[Irrational Numbers|irrational numbers]] are defined as
$$
\mathbb{I}=\mathbb{R} \setminus \mathbb{Q}=\{ x\ |\ x \not\in \mathbb{Q}, x \in \mathbb{R}\}
$$
The [[Real Numbers|real numbers]] are defined as
$$
\mathbb{R}=\{ x\ |\ x \in \mathbb{Q} \text{ OR } x \in \mathbb{I} \}
$$
The [[Complex Numbers|complex numbers]] are defined as
$$
\mathbb{C}=\{ a+bi\ |\ a,b \in \mathbb{R}, i=\sqrt{ -1 } \}
$$
The [[Universal Set|universal set]] (or sometimes, the "universe") is the set of all things currently under discussion and it is denoted by $\mathbb{U}$.

# Set Equality

Two sets $A$ and $B$ are said to be equal if every element of $A$ is an element of $B$ and every element of $B$ is an element of $A$. This can be expressed as,
$$
A \subseteq B \ \ \ \ \ \ \ \ B \subseteq A 
$$
Put a different way, for all elements $x$ in $A$ there exists an element $y$ in $B$.
$$
\forall \ x \in A, \ \exists \ y \in B
$$
