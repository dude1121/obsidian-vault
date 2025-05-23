---
tags:
  - mathematics
---
A **limit** is the value a [[Function|function]] or [[Sequence (Mathematics)|sequence]] approaches as the argument (or index) approaches some value. Limits are often defined using *limit notation*,
$$
\lim_{ x \to a }f(x)=L 
$$
which would be read as "the limit of $f(x)$ as $x$ approaches $a$ is $L$." This means that the value of the function $f(x)$ approaches some value $L$ as the variable $x$ gets closer and closer to some other value $a$, however crucially $x\neq a$. This caveat means that a limit for a function can be defined at some value even if the function itself is [[Undefined|undefined]] at that point. This is because the limit describes the *behaviour* of the function, not the actual *value* of the function.

For example, consider the value of $\displaystyle \lim_{ x \to 0 }\frac{\sin x}{x}$. The function itself is clearly undefined when $x=0$, but examining values of $x$ close to $0$ reveals that this function actually approaches $1$. 
# One-sided limits
Consider the [[Heaviside Function|Heaviside function]], $H$.
$$
H(t)=\begin{cases}
1&t\geq 0 \\
0& t< 0
\end{cases}
$$
There is no single value this function approaches at $t=0$. However, we can take the one-sided limit of $H(t)$ to see its behaviour from either side of $t=0$. We indicate this by,
$$
\begin{align}
\lim_{ t \to 0^- }H(t)=0&&\text{and}&&\lim_{ t \to 0^+ }H(t)=1  
\end{align}
$$
The $^-$ and $^+$ signs indicate the direction we are approaching the limit from. A limit approaching from the negative direction is known as a *left-hand* limit and a limit approaching from the positive direction is known as a *right-hand* limit.
# Limit existence
There are some circumstances where a limit is said to not exist. Primarily, if the left and right hand limits do not agree with one another, we say that the limit does not exist. Using the same function as above,
$$
\lim_{ t \to 0 }H(t) \text{ does not exist} 
$$
This might be noted as,
$$
\lim_{ t \to 0 }H(t)=\text{DNE} 
$$
# Limit laws
Suppose $c$ is a [[Constant|constant]] and the limits $\lim_{ x \to a }f(x)$ and $\lim_{ x \to a }g(x)$ both exist. Then,
$$
\begin{align}
1. &\lim_{ x \to a }[f(x)+g(x)]=\lim_{ x \to a }f(x)+\lim_{ x \to a } g(x)\\ \\
2. &\lim_{ x \to a }[f(x)-g(x)]=\lim_{ x \to a }f(x)-\lim_{ x \to a }g(x) \\
3.&\lim_{ x \to a }[cf(x)]=c\lim_{ x \to a }f(x) \\
4.&\lim_{ x \to a }[f(x)g(x)]=\lim_{ x \to a }f(x)\cdot \lim_{ x \to a }g(x) \\
5.&\lim_{ x \to a }\frac{f(x)}{g(x)}=\frac{\lim_{ x \to a }f(x) }{\lim_{ x \to a }g(x) }\text{ if }\lim_{ x \to a }g(x) \neq 0       
\end{align}
$$
# Relation to continuity
A function is said to be [[Continuous Function|continuous]] at some value $a$ if
$$
\lim_{ x \to a }f(x)=f(a) 
$$
This implicitly requires three things for $f$ to be continuous at $a$,
1. $f(a)$ must be defined (i.e., $a$ is within the domain of $f$)
2. $\lim_{ x \to a }f(x)$ exists
3. $\lim_{ x \to a }f(x)=f(a)$
# Precise limit definition
Consider the following function
$$
f(x)=\begin{cases}
2x-1&\text{if } x\neq 3 \\
6&\text{if }x=3
\end{cases}
$$
Intuitively we see that when $x$ is close to $3$ then $f(x)$ is close to $5$, therefore $\lim_{ x \to 3 }f(x)=5$. To obtain more detailed information about how $f(x)$ varies when $x$ is close to $3$ we ask the following question:
$$
\text{How close to 3 does }x\text{ need to be so that }f(x)\text{ differs from }5\text{ by less than }0.1\text{?}
$$
The distance from $x$ to $3$ is $|x-3|$ and the distance from $f(x)$ to $5$ is $|f(x) - 5|$, so our problem is to find the number $\delta$ such that,
$$
|f(x)-5| < 0.1\ \ \text{ if }\ \ |x-3|<\delta\ \  \text{ but }\ \ x\neq 3
$$
If $|x-3|>0$ then $x\neq 3$ so an equivalent formulation is to find a number $\delta$ such that,
$$
|f(x)-5|<0.1\ \ \text{ if }\ \ 0<|x-3|<\delta
$$

# Relation to derivatives
The idea of a limit is crucial to the definition of a [[Derivative|derivative]]. Specifically,
$$
f'(x)=\lim_{ h \to 0}\frac{f(x+h)-f(x)}{h} 
$$
## L'Hôpital's Rule
If either
$$
\lim_{ x \to c }f(x)=\lim_{ x \to c }g(x)=0  
$$
or
$$
\lim_{ x \to c }|f(x)|=\lim_{ x \to c }|g(x)|=\infty 
$$
then
$$
\lim_{ x \to c }\frac{f(x)}{g(x)}=\lim_{ x \to c }\frac{f'(x)}{g'(x)}  
$$
That is, if you are evaluating a limit that is a quotient of functions of $x$ and substituting in $c$ gives an *indeterminate form* ($\frac{0}{0}$ or $\frac{\infty}{\infty}$) then you can take the derivative of the two functions and evaluate the limit this way. Going back to the example of $\lim_{ x \to o }\frac{\sin x}{x}$,
$$
\begin{align}
\lim_{ x \to 0 }\frac{\sin x}{x}&=\frac{0}{0} \\
\lim_{ x \to 0 }\frac{\cos x}{1}&=\frac{1}{1} \\
&=1  
\end{align}
$$
