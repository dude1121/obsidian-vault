---
tags:
  - mathematics
  - linear-algebra
---
A **vector** is a quantity with both a magnitude and direction. In [[physics]], vectors are often used for things like [[displacement]], [[Force|force]], or [[Field|fields]]. A vector is typically denoted with a bolded variable $\mathbf{v}$ or an arrow above the variable name $\vec{v}$, or sometimes both $\vec{\mathbf{v}}$. Graphically, a vector is represented with an arrow whose length denotes the magnitude and the direction in which the arrow points is the vector's direction. Typically vectors are said to originate at the [[origin]], but their position is usually irrelevant, as the magnitude and direction are what is important.

A vector can be written with either as *column vectors*, *row vectors*, or for two-dimensional or three-dimensional vectors, the "hat" notation with three [[Unit Vector|unit vectors]] may be used (although this is typically used in physics only, not mathematics). 
$$
\vec{a}=\begin{pmatrix}
a_{1}\\a_{2}\\ \vdots \\a_{n}
\end{pmatrix}
$$
$$
\vec{a}=\left(a_{1},\ a_{2},\ \dots,\ a_{n}\right)
$$
$$
\vec{a}=a_{1}\mathbf{\hat{i}}+a_{2}\mathbf{\hat{j}}+a_{3}\mathbf{\hat{k}}
$$

# Vector Addition

Vectors are added together in what is commonly called the "tip-to-tail" method.
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[step=1cm,gray,very thin](-0.9, -0.9) grid (6.9,6.9);
\draw[very thick, <->] (-0.5,0) -- (6,0) node[anchor=north west] {$x$};
\draw[very thick, <->] (0,-0.5) -- (0,6) node[anchor=south east] {$y$};
\draw[green, thick,->] (0,0) -- (3,0) node[anchor=south west] {$\vec{a}$};
\draw[red, thick,->] (0,0) -- (1,4) node[anchor=south west] {$\vec{b}$};
\end{tikzpicture}
\end{document}
```
Consider the above diagram with two vectors, $\vec{a}$ and $\vec{b}$. If we want to add these vectors together, we can slide $\vec{b}$'s "tail" over to the "tip" of $\vec{a}$. 
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[step=1cm,gray,very thin](-0.9, -0.9) grid (6.9,6.9);
\draw[very thick, <->] (-0.5,0) -- (6,0) node[anchor=north west] {$x$};
\draw[very thick, <->] (0,-0.5) -- (0,6) node[anchor=south east] {$y$};
\draw[green, thick,->] (0,0) -- (3,0) node[anchor=north west] {$\vec{a}$};
\draw[orange, thick, ->] (0,0) -- (4,4) node[anchor=south west] {$\vec{c}$};
\draw[red, thick,->] (3,0) -- (4,4) node[anchor=north west] {$\vec{b}$};

\end{tikzpicture}
\end{document}
```
The resulting vector, $\vec{c}$, is the sum of the two vectors $\vec{a}$ and $\vec{b}$. Mathematically, we can represent this as,
$$
\begin{aligned}
\vec{a}&=\begin{pmatrix}
3\\0\\
\end{pmatrix}\\
\vec{b}&=\begin{pmatrix}
1\\4\\
\end{pmatrix}\\
\vec{a}+\vec{b}&=\begin{pmatrix}
3+1\\0+4\\
\end{pmatrix}\\
&=\begin{pmatrix}
4\\4\\
\end{pmatrix}
\end{aligned}
$$
# Vector Subtraction

Subtraction is very similar to vector addition. To complete it, we first must discuss what the *negative* or *additive inverse* of a vector means. Given a vector $\vec{a}$,
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[very thin,gray,step=1cm](-3.9,-3.9) grid (3.9,3.9);
\draw[very thick, <->](-3.5,0)--(3.5,0)node[anchor=north west]{$x$};
\draw[very thick, <->](0,-3.5)--(0,3.5)node[anchor=south east]{$y$};
\draw[green,thick,->](0,0)--(3,2)node[anchor=west]{$\vec{a}$};
\end{tikzpicture}
\end{document}
```
Its negative is defined as a vector with the same magnitude but opposite direction, such that
$$
\vec{a}+(-\vec{a})=\vec{0}
$$
In this case above, $-\vec{a}$ would be,
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[very thin,gray,step=1cm](-3.9,-3.9) grid (3.9,3.9);
\draw[very thick, <->](-3.5,0)--(3.5,0)node[anchor=north west]{$x$};
\draw[very thick, <->](0,-3.5)--(0,3.5)node[anchor=south east]{$y$};
\draw[green,thick,->](0,0)--(3,2)node[anchor=west]{$\vec{a}$};
\draw[red,thick,->](0,0)--(-3,-2)node[anchor=east]{$-\vec{a}$};
\end{tikzpicture}
\end{document}
```
Using the same vectors as above, lets now subtract $\vec{b}$ from $\vec{a}$ instead of adding them together. Since subtraction is really just addition with negative values, we will "subtract" these vectors by adding $\vec{a}$ to $-\vec{b}$.

```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[very thin, gray, step=1cm](-5.9,-5.9) grid (5.9, 5.9);
\draw[very thick, <->](-5.5,0)--(5.5,0)node[anchor=north west]{$x$};
\draw[very thick, <->](0,-5.5)--(0,5.5)node[anchor=south east]{$y$};
\draw[green, thick, ->](0,0)--(3,0)node[anchor=north west]{$\vec{a}$};
\draw[red, thick, ->](0,0)--(1,4)node[anchor=west]{$\vec{b}$};
\draw[red, dashed, thick, ->](0,0)--(-1,-4)node[anchor=east]{$-\vec{b}$};
\draw[red, dashed, thick, ->](3,0)--(2,-4);
\draw[orange,thick,->](0,0)--(2,-4)node[anchor=east]{$\vec{c}$};
\end{tikzpicture}
\end{document}
```
  Using the same "tip-to-tail" method that allows us to add vectors, we can subtract $\vec{b}$ from $\vec{a}$. Graphically we see that the resultant vector is located at $\vec{c}=(\begin{smallmatrix}2\\-4\\\end{smallmatrix})$ .

# Scalar Multiplication & Division

We can multiply vectors and [[Scalar|scalars]] together by way of *scalar multiplication*. The result of this operation is a vector with the same direction as the original vector, but whose magnitude has been scaled by the scalar. For example,
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[step=1cm,gray,very thin](-0.9, -0.9) grid (6.9,6.9);
\draw[very thick, <->] (-0.5,0) -- (6,0) node[anchor=north west] {$x$};
\draw[very thick, <->] (0,-0.5) -- (0,6) node[anchor=south east] {$y$};
\draw[green, thick,->] (0,0) -- (2,0.5) node[anchor=south west] {$\vec{a}$};
\draw[green, thick,->] (0,0) -- (4,1) node[anchor=south west] {$2\vec{a}$};
\end{tikzpicture}
\end{document}
```
The original vector, 
$$
\vec{a}=\begin{pmatrix}
2\\0.5\\
\end{pmatrix}
$$
is multiplied by the scalar $2$. This results in the vector,
$$
2\vec{a}=\begin{pmatrix}
2\cdot 2\\2\cdot 0.5\\
\end{pmatrix}=\begin{pmatrix}
4\\1
\end{pmatrix}
$$
In general,
$$
k \vec{a}=\begin{pmatrix}
ka_{1}\\ ka_{2}\\\vdots\\ ka_{n}\\
\end{pmatrix}
$$
where $k$ is some scalar value. Note that if $k=-1$, we get the additive inverse from above, where the magnitude is unchanged but the direction has been reversed.

Division can be viewed as multiplication by $\frac{1}{k}$. 

# Dot Product
![[Dot Product]]

# Cross Product

![[Cross Product]]
