---
tags:
  - mathematics
  - complex-numbers
  - imaginary
---
**Complex numbers** are an extension of the [[Real Numbers|real numbers]] $\mathbb{R}$ by use of the imaginary unit, $i$ (or in electrical engineering, $j$) where the unit is defined as,
$$
i=\sqrt{ -1 }
$$
and therefore,
$$
i^2=-1
$$
A complex number is expressed in one of two ways: rectangular form, and polar form. In rectangular form, the complex number $z$ is expressed as,
$$
z=a+bi
$$
where $a$ is the *real* part, and $b$ is the *imaginary* part. In polar form the complex number $z$ is expressed as,
$$
z=r\angle\theta
$$
where $r$ is the magnitude of the complex number, its distance from the origin ($0+0i$) and $\theta$ is the angle the number makes with the $\mathrm{Re}$ axis.

For example, consider the complex number $1+2i$. We can display this number graphically by use of the [[complex plane]].
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[step=1cm,gray,very thin](-3.9, -3.9) grid (3.9,3.9);
\draw[very thick, <->] (-3.5,0) -- (3.5,0) node[anchor=north west] {Re};
\draw[very thick, <->] (0,-3.5) -- (0,3.5) node[anchor=north west] {Im};
\draw[thick, ->] (0,0) -- (1,2) node[pos=0.5, anchor=south east] {$\sqrt{5}$} node[anchor=south west] {$(1+2i)$};
\draw[dashed](1,0) -- (1,2) node[pos=0.5, anchor=west]{$2$};
\draw[dashed](0,0) -- (1,0) node[pos=0.5, anchor=north]{$1$};
\end{tikzpicture}
\end{document}
```
Note that from this point we can form a right angle triangle. From [[Pythagorean Theorem]] we can find the length of the hypotenuse, the *magnitude* of this complex number. We can also use $\arctan$ to find the angle that it makes with the $\mathrm{Re}$ axis.
$$
|z|=\sqrt{ 1^2+2^2 }=\sqrt{ 5 }
$$
$$
\theta=\arctan\left(\frac{2}{1}\right)=63.435\degree
$$
$$
z=\sqrt{ 5 }\angle 63.435\degree=1+2i
$$
The set of all complex numbers is denoted with $\mathbb{C}$. Basic mathematical operations like addition, subtraction, multiplication, and division are similar to that of [[Vector|vectors]]. 
$$
(a_{1}+b_{1}i) + (a_{2}+b_{2}i)=(a_{1}+a_{2})+(b_{1}+b_{2})i
$$
# Conjugate

The complex *conjugate* of a complex number $z=a+bi$ is defined as $\bar{z}=a-bi$. This has the geometric effect of "reflecting" the number about the $\mathrm{Re}$ axis.
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[step=1cm,gray,very thin](-3.9, -3.9) grid (3.9,3.9);
\draw[very thick, <->] (-3.5,0) -- (3.5,0) node[anchor=north west] {Re};
\draw[very thick, <->] (0,-3.5) -- (0,3.5) node[anchor=north west] {Im};
\draw[thick, ->] (0,0) -- (1,2) node[anchor=south west] {$z$};
\draw[dashed](1,-2) -- (1,2);
\draw[thick,->] (0,0)--(1,-2) node[anchor=south west]{$\bar{z}$};
\end{tikzpicture}
\end{document}
```
