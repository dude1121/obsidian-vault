---
tags:
  - mathematics
  - calculus
---
A **Laplace transform** (named after [[Pierre-Simon Laplace]]) is an [[Integral|integral]] [[Transform (Mathematics)|transform]] that converts a [[Real Numbers|real valued]] [[Function|function]] into a function of a [[Complex Numbers|complex]] variable $s$. This technique is useful for converting [[Derivative|differentiation]] and integration in the time domain into easier multiplication and division in the [[Laplace Domain|Laplace domain]]. 

The Laplace transform is defined as,
$$
\mathcal{L}\left[\ f(t)\ \right]=F(s)=\int_{0}^\infty e^{-st}\ f(t)\ dt
$$
where $\mathcal{L}[\ f(t)\ ]$ is the notation for the Laplace transform of the function $f(t)$.  $s$ is a complex frequency-domain parameter defined as,
$$
s=\sigma + i\omega
$$
where $\sigma$ and $\omega$ are real numbers.
# Common Laplace transforms
| $f(t)$                                 | $\mathcal{L}(f)$                          | $f(t)$                 | $\mathcal{L}(f)$                            |
| -------------------------------------- | ----------------------------------------- | ---------------------- | ------------------------------------------- |
| $1$                                    | $\displaystyle \frac{1}{s}$               | $te^{-at}$             | $\displaystyle \frac{1}{(s+a)^2}$           |
| $\displaystyle \frac{t^{n-1}}{(n-1)!}$ | $\displaystyle \frac{1}{s^n}$             | $t^{n}e^{-at}$         | $\displaystyle \frac{n!}{(s+a)^{n+1}}$      |
| $e^{-at}$                              | $\displaystyle \frac{1}{s+a}$             | $e^{-at}(1-at)$        | $\displaystyle \frac{s}{(s+a)^2}$           |
| $1-e^{-at}$                            | $\displaystyle \frac{a}{s(s+a)}$          | $[(b-a)t+1]e^{-at}$    | $\displaystyle \frac{s+b}{(s+a)^2}$         |
| $\cos at$                              | $\displaystyle \frac{s}{s^2+a^2}$         | $\sin at - at \cos at$ | $\displaystyle \frac{2a^3}{(s^2+a^2)^2}$    |
| $\sin at$                              | $\displaystyle \frac{a}{s^2+a^2}$         | $t\sin at$             | $\displaystyle \frac{2as}{(s^2+a^2)^2}$     |
| $1-\cos at$                            | $\displaystyle \frac{a^2}{s(s^2+a^2)}$    | $\sin at+at\cos at$    | $\displaystyle \frac{2as^2}{(s^2+a^2)^2}$   |
| $at - \sin at$                         | $\displaystyle \frac{a^3}{s^2(s^2+a^2)}$  | $t\cos at$             | $\displaystyle \frac{s^2-a^2}{(s^2+a^2)^2}$ |
| $e^{-at}-e^{-bt}$                      | $\displaystyle \frac{b-a}{(s+a)(s+b)}$    | $e^{-at}\sin bt$       | $\displaystyle \frac{b}{(s+a)^2+b^2}$       |
| $ae^{-at}-be^{-bt}$                    | $\displaystyle \frac{s(a-b)}{(s+a)(s+b)}$ | $e^{-at}\cos bt$       | $\displaystyle \frac{s+a}{(s+a)^2+b^2}$     |
# The linearity property
For a sum of two function $f(t)$ and $g(t)$ multiplied by constants $a$ and $b$, the Laplace transform is defined as,
$$
\mathcal{L}\ [\ a\ f(t)+b\ g(t)\ ]=a\ \mathcal{L}(f)+b\ \mathcal{L}(g)
$$
# Laplace transforms of derivatives
If we take the Laplace transform of the first derivative of a function, its Laplace transform is equal to,
$$
\mathcal{L}(f')=s\ \mathcal{L}(f)-f(0)
$$
There is a similar pattern for the second derivative,
$$
\mathcal{L}(f'')=s^2\ \mathcal{L}(f)-s\ f(0) - f'(0)
$$
In general then,
$$
\mathcal{L}(f^n)=s^n \mathcal{L}(f) - s^{n-1}\ f(0) - s^{n-2}\ f^1(0) -\dots-s\ f^{n-1}(0) - f^n(0)
$$
