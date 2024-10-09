---
tags:
  - mathematics
  - linear-algebra
---
The **Cross Product** is a way of multiplying two [[Vector|vectors]] together. Unlike the [[Dot Product|dot product]], this method returns a vector, lending it to be often called the *vector product*. The cross product of two vectors will return a vector that is perpendicular to the plane created by the two vectors. Geometrically, the cross product's magnitude can be represented as the area of the parallelogram formed with the two vectors as its sides.
```tikz
\usepackage{tikz}
\begin{document}
\begin{tikzpicture}
\draw[gray, very thin, step=1cm](-7.9,-4.9) grid (7.9, 7.9);
\draw[very thick, <->](-7.5,0) -- (7.5,0) node[anchor=north west]{$x$};
\draw[very thick, <->](0,-4.5) -- (0,7.5) node[anchor=south east]{$y$};
\draw[red, thick, ->](-2,-3)--(5,1)node[right]{\large $\vec{a}$};
\draw[green,thick,->](-2,-3)--(-4,3)node[left]{\large $\vec{b}$};
\draw[dashed](-4,3)--(3,7) -- (5,1);
\fill[fill=black!30, opacity=0.4] (-2,-3)--(-4,3)--(3,7)--(5,1);
\draw (0.25,2.5)node[right]{\LARGE A};
\end{tikzpicture}
\end{document}
```
The area of the parallelogram above can be found by finding the magnitude of $\vec{a}\times \vec{b}$.

Due to its nature, the cross product is only valid in three-dimensional space. The direction of the resulting vector can be found by the [[Right Hand Rule|right hand rule]]. For the cross product $\vec{a}\times \vec{b}$, point your thumb in the direction of $\vec{a}$, and your index finger in the direction of $\vec{b}$. Your thumb will point in the direction of the resulting [[Normal|normal]] vector, $\vec{n}$. 

The cross product is defined as
$$
\vec{a}\times \vec{b}=ab\sin \theta \ \vec{n}
$$
where $\vec{n}$ is the normal vector perpendicular to the plane created by $\vec{a}$ and $\vec{b}$, and $\theta$ is the angle formed by $\vec{a}$ and $\vec{b}$. Another way to solve the cross product is to set up a $3$ x $3$ [[Matrix|matrix]] as such,
$$
\begin{pmatrix}
\hat{i}&\hat{j}&\hat{k} \\
a_{1}&a_{2}&a_{3} \\
b_{1}&b_{2}&b_{3} \\
\end{pmatrix}
$$
where $\hat{i}$, $\hat{j}$, and $\hat{k}$ are the three-dimensional [[Unit Vector|unit vectors]], and then evaluate its [[determinant]]. Note that the cross product can be found for two vectors in two-dimensional space (simply set $a_{3}$ and $b_{3}$ to $0$), but the resulting vector will make the entire [[Vector Space|vector space]] three-dimensional. 
