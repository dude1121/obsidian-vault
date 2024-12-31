---
tags:
  - mathematics
  - linear-algebra
---
The **dot product** (or, *scalar product*) is one of two common ways of multiplying vectors. It is sometimes called the scalar product because the result is not a [[vector]] but a [[scalar]]. This differs from the other form of vector multiplication, the [[Cross Product|cross product]]. The dot product is denoted with a dot " $\cdot$ ". Consider the two vectors $\vec{a}$ and $\vec{b}$. 
$$
\vec{a}=\begin{pmatrix}
2\\5\\
\end{pmatrix}\ \vec{b}=\begin{pmatrix}
3\\-2\\
\end{pmatrix}
$$
The dot product of these two vectors is given by,
$$
\vec{a}\cdot \vec{b}=(2\cdot 3)+(5\cdot -2)=-4
$$
In general, the dot product can be defined as,
$$
\vec{a}\cdot \vec{b}=\sum_{i=1}^n=a_{i}b_{i}=a_{1}b_{1}+a_{2}b_{2}+\dots+a_{n}b_{n}
$$
Important to note: **if the two vectors are perpendicular to one another, their dot product will be 0.**
$$
\begin{pmatrix}
1\\0\\
\end{pmatrix}\cdot \begin{pmatrix}
0\\1\\
\end{pmatrix}=\vec{0}
$$
On the other hand, if the two vectors are codirectional, their dot product will be the product of the two magnitudes.
$$
\vec{a}\cdot \vec{b}=ab
$$
Since a vector is codirectional with itself, the dot product of a vector with itself is therefore,
$$
\vec{a}\cdot \vec{a}=a^2
$$
We can also define the dot product geometrically. If two vectors make some angle $\theta$ with each other, their dot product is equal to the product of the two vectors' magnitudes and the cosine of $\theta$.
$$
\vec{a}\cdot \vec{b}=ab\cos \theta
$$
Meaning the angle between any two vectors can be found by,
$$
\theta=\arccos \left(\frac{\vec{a}\cdot \vec{b}}{ab}\right)
$$
The dot product is commutative, that is, the order in which the vectors are multiplied does not matter.
$$
\vec{a}\cdot \vec{b}=\vec{b}\cdot \vec{a}
$$