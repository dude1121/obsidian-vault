---
tags:
  - mathematics
  - geometry
---
In geometry, the **tangent line** to a [[Curve|curve]] at a given [[Point|point]] is a [[Line|straight line]] that touches the curve only at that point. A line is said to be "tangent" to a point $x=c$ on a curve $y=f(x)$ if the line passes through the point $(c,f(c))$ and has [[Slope|slope]] $f'(c)$. 
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}[domain=0:4, range=-1:4]
\draw[very thin, color=gray] (-0.1,-1.1) grid (3.9, 3.9);

\draw[->] (-0.2,0) -- (4.2,0) node[right] {$x$};
\draw[->] (0,-1.2) -- (0,4.2) node[above] {$f(x)$};

\draw[color=red] plot (\x, {((2/3)*\x - 1)^2+0.75}) node[right] {$f(x)$};
\draw[color=green] plot (\x,{(4/9)*\x - (1/36)});

\fill[color=blue] (2,31/36) circle[radius=2pt] node[below] {$P$};

\end{tikzpicture}
\end{document}
```
In the above example, the red line is some function, $f(x)$,  and the green line is the line tangent to the curve at some point, $P$.  This line only touches the function at the one point and never again. The slope of the line is equivalent to the derivative of $f(x)$ evaluated at the x value of $P$.