---
tags:
  - mathematics
---
A **function** is an assignment of unique inputs to unique outputs. In the language of [[Set|sets]], a function from set $X$ to set $Y$ is an assignment of one element of set $X$ to exactly one element of set $Y$. Put differently,
$$
\forall x \in X,\exists y \in Y 
$$
The set $X$ is called the [[Domain|domain]] of the function and the set $Y$ is the [[Codomain|codomain]]. A function $f$ may be specified by the notation $f:X\to Y$. This could alternatively be written $x \mapsto y$. Typically these sets are assumed to be the [[Real Numbers|real numbers]] unless otherwise stated.
# Functional Notation
This type of notation requires the function be named, and in general the typical name of an arbitrary function is $f$. If more functions are defined this becomes $g$ then $h$, and so on. The name of the function is followed by its argument(s). E.g.
$$
\begin{aligned}
f(x)&&\sin(\pi)&&f(x^3+1)
\end{aligned}
$$
The argument can be a variable, a value within the function's domain, or an expression.
# Function rules
Not every equation can define a function. For example, the equation $y=x^2$ defines $y$ as a function of $x$ because it determines exactly one value of $y$ for each value of $x$. However, $y^2=x$ is *not* a function because inputs of $x$ can correspond to multiple values of $y$. For example, $x=4$ could correspond to $y=2$ or $y=-2$.

To determine whether the graph of some equation is a valid function we can do what is called the *vertical line test*. 
```tikz
\usepackage{tikz}
\usepackage{pgfplots}
\begin{document}
\begin{tikzpicture}
\begin{axis}[domain=-3:5,
		samples=100,
		enlarge x limits=false,
		grid=both,
		no markers,
		axis equal,
		xlabel={$x$},
		ylabel={$y$},
		ymin=-5, ymax=5]
\addplot [red, thick] {x^2};
\addplot [green, thick, samples=200] {sqrt(x)};
\addplot [green, thick, samples=200] {-sqrt(x)};
\addplot [orange, dashed] coordinates {(1,-5)(1,5)};
\end{axis}

\end{tikzpicture}
\end{document}
```
Note the two plots above: the red plot of the equation $y=x^2$ and the green plot of the equation $y=\pm \sqrt{ x }$. A dashed vertical line is drawn at $x=1$. It only passes through the red plot once at the point $(1,1)$ because $y=1$ is the only point that $x=1$ corresponds to, thus making $y=x^2$ a function. The orange line passes through the green plot twice, because $x=1$ corresponds to two values in this equation, therefore making it not a function.
# Even, odd functions and symmetry
A function is said to be *even* if it satisfies $f(-x)=f(x)$ throughout its entire domain. The function $f(x)=\cos x$ is an even function. Even functions have the property of being symmetrical about the $y$-axis.
```tikz
\usepackage{tikz}
\usepackage{pgfplots}
\begin{document}
\begin{tikzpicture}
\begin{axis}[
			axis line style = thick,
			axis lines = middle]
\addplot [red, thick, domain=-2*pi:2*pi, samples=200] {cos(deg(x))};
\end{axis}
\end{tikzpicture}
\end{document}
```
If a function satisfies $f(-x)=-f(x)$ for its entire domain then the function is said to be *odd*. The function $f(x)=\sin x$ is an odd function. These functions have the property of being symmetrical about the origin, that is, the line $y=x$.
```tikz
\usepackage{tikz}
\usepackage{pgfplots}
\begin{document}
\begin{tikzpicture}
\begin{axis}[
			axis line style = thick,
			axis lines = middle,
			ymin=-1, ymax=1]
\addplot [red, thick, domain=-2*pi:2*pi, samples=200] {sin(deg(x))};
\addplot [orange, dashed, thick] {x};
\end{axis}
\end{tikzpicture}
\end{document}
```
# Types of functions
Functions can broadly be broken into two main categories: *algebraic* and *transcendental*.
## Algebraic functions
Algebraic functions are functions that can be constructed using algebraic operations (e.g., [[Addition|addition]], [[Subtraction|subtraction]], [[Multiplication|multiplication]], [[Division|division]], etc.) starting with [[Polynomial|polynomials]]. This obviously, then, includes [[Linear Function|linear functions]], [[Quadratic Function|quadratic functions]], and [[Cubic Function|cubic functions]], but also includes [[Rational Function|rational functions]]. 
## Transcendental functions
Any function that does not fit into the definition of algebraic functions are categorized as *transcendental*. These include the [[Trigonometric Functions|trigonometric functions]], [[Exponential Function|exponential functions]], and [[Logarithmic Functions|logarithmic functions]].