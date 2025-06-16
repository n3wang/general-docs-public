
#### 7.10 Continuity and Interruptions

If the function

$$
f(x)= \begin{cases}\frac{x^2-16}{x-4} & \text { if } \quad x \neq 4 \\ c & \text { if } \quad x=4\end{cases}
$$

?p: is continuous, what is the value of $C$ ?
?x
Since $x^2-16=(x-4)(x+4), \quad f(x)=x+4$ for $x \neq 4$. Hence, $\lim _{x \rightarrow 4} f(x)=8$. For continuity, we must have $\lim _{x \rightarrow 4} f(x)=f(4)$, and, therefore, $8=f(4)=C$.


#### 7.11 Existence in Continuity

Let $g(x)$ be the function such that

$$
g(x)= \begin{cases}\frac{x^2-b^2}{x-b} & \text { if } x \neq b \\ 0 & \text { if } x=b\end{cases}
$$

?p: (a) Does $g(b)$ exist? (b) Does $\lim _{x \rightarrow b} g(x)$ exist? (c) Is $g(x)$ continuous at $x=b$ ?
?x
(a) $g(b)=0$ by definition. (b) Since $x^2-b^2=(x-b)(x+b), g(x)=x+b$ for $x \neq b$. Hence, $\lim _{x \rightarrow b} g(x)=\lim _{x \rightarrow b}(x+b)=2 b$. (c) For $g(x)$ to be continuous at $x=b$, we must have $\lim _{x \rightarrow b} g(x)=g(b)$, that is, $2 b=0$. So, $g(x)$ is continuous at $x=b$ only when $b=0$.

#### 7.12 Continuous Function and interruptions
7.12 For what value of $k$ is the following a continuous function?

$$
f(x)=\left\{\begin{array}{ll}
\frac{\sqrt{7 x+2}-\sqrt{6 x+4}}{x-2} & \text { if } x \geq-3 \\
k & \text { if } x=2
\end{array} \text { and } x \neq 2\right.
$$
?x

Notice that $\sqrt{7 x+2}$ and $\sqrt{6 x+4}$ are defined when $x \geq-\frac{2}{3}$, since $7 x+2$ and $6 x+4$ are nonnegative for $x \geq-3$. Also,

$$
\begin{aligned}
\frac{\sqrt{7 x+2}-\sqrt{6 x+4}}{x-2} & =\frac{\sqrt{7 x+2}-\sqrt{6 x+4}}{x-2} \cdot \frac{\sqrt{7 x+2}+\sqrt{6 x+4}}{\sqrt{7 x+2}+\sqrt{6 x+4}}=\frac{(7 x+2)-(6 x+4)}{(x-2)(\sqrt{7 x+2}+\sqrt{6 x+4})} \\
& =\frac{x-2}{(x-2)(\sqrt{7 x+2}+\sqrt{6 x+4})}=\frac{1}{\sqrt{7 x+2}+\sqrt{6 x+4}}
\end{aligned}
$$


Hence, $\lim _{x \rightarrow 2} f(x)=\lim _{x \rightarrow 2} \frac{1}{\sqrt{7 x+2}+\sqrt{6 x+4}}=\frac{1}{\sqrt{16}+\sqrt{16}}=\frac{1}{8}$. Therefore, $k$ must be $\frac{1}{8}$.

#### 7.13Determine tHe points of discontinuity
7.13 Determine the points of discontinuity (if any) of the following function $f(x)$.

$$
f(x)= \begin{cases}1 & \text { if } x \text { is rational } \\ 0 & \text { if } x \text { is irrational }\end{cases}
$$

?X
Since there are both rational and irrational numbers arbitrarily close to a given number $c, \lim _{x \rightarrow c} f(x)$ does not exist. Hence, $f(x)$ is discontinuous at all points.


#### 7.14 Determine points of Discontinuity

7.14 Determine the points of discontinuity (if any) of the following function $f(x)$.

$$
f(x)= \begin{cases}x & \text { if } x \text { is rational } \\ 0 & \text { if } x \text { is irrational }\end{cases}
$$

?x
Let $c$ be any number. Since there are irrational numbers arbitrarily close to $c, f(x)=0$ for values of $x$ arbitrarily close to $c$. Hence, if $\lim _{x \rightarrow c} f(x)$ exists, it must be 0 . Therefore, if $f(x)$ is to be continuous at $c$, we must have $f(c)=0$. Since there are rational numbers arbitrarily close to $c, f(x)=x$ for some points that are arbitrarily close to $c$. Hence, if $\lim _{x \rightarrow c} f(x)$ exists, it must be $\lim _{x \rightarrow c} x=c$. So, if $f(x)$ is continuous at $c$, $f(c)=c=0$. The only point at which $f(x)$ is continuous is $x=0$.
