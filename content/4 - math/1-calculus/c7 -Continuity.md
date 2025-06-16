
##### 7.10 Continuity
If the function

$$
f(x)= \begin{cases}\frac{x^2-16}{x-4} & \text { if } \quad x \neq 4 \\ c & \text { if } \quad x=4\end{cases}
$$

is continuous, what is the value of $C$ ?
Since $x^2-16=(x-4)(x+4), \quad f(x)=x+4$ for $x \neq 4$. Hence, $\lim _{x \rightarrow 4} f(x)=8$. For continuity, we must have $\lim _{x \rightarrow 4} f(x)=f(4)$, and, therefore, $8=f(4)=C$.
7.11 Let $g(x)$ be the function such that

$$
g(x)= \begin{cases}\frac{x^2-b^2}{x-b} & \text { if } x \neq b \\ 0 & \text { if } x=b\end{cases}
$$

(a) Does $g(b)$ exist? (b) Does $\lim _{x \rightarrow b} g(x)$ exist? (c) Is $g(x)$ continuous at $x=b$ ?
(a) $g(b)=0$ by definition. (b) Since $x^2-b^2=(x-b)(x+b), g(x)=x+b$ for $x \neq b$. Hence, $\lim _{x \rightarrow b} g(x)=\lim _{x \rightarrow b}(x+b)=2 b$. (c) For $g(x)$ to be continuous at $x=b$, we must have $\lim _{x \rightarrow b} g(x)=g(b)$, that is, $2 b=0$. So, $g(x)$ is continuous at $x=b$ only when $b=0$.
7.12 For what value of $k$ is the following a continuous function?

$$
f(x)=\left\{\begin{array}{ll}
\frac{\sqrt{7 x+2}-\sqrt{6 x+4}}{x-2} & \text { if } x \geq-3 \\
k & \text { if } x=2
\end{array} \text { and } x \neq 2\right.
$$


Notice that $\sqrt{7 x+2}$ and $\sqrt{6 x+4}$ are defined when $x \geq-\frac{2}{3}$, since $7 x+2$ and $6 x+4$ are nonnegative for $x \geq-3$. Also,

$$
\begin{aligned}
\frac{\sqrt{7 x+2}-\sqrt{6 x+4}}{x-2} & =\frac{\sqrt{7 x+2}-\sqrt{6 x+4}}{x-2} \cdot \frac{\sqrt{7 x+2}+\sqrt{6 x+4}}{\sqrt{7 x+2}+\sqrt{6 x+4}}=\frac{(7 x+2)-(6 x+4)}{(x-2)(\sqrt{7 x+2}+\sqrt{6 x+4})} \\
& =\frac{x-2}{(x-2)(\sqrt{7 x+2}+\sqrt{6 x+4})}=\frac{1}{\sqrt{7 x+2}+\sqrt{6 x+4}}
\end{aligned}
$$


Hence, $\lim _{x \rightarrow 2} f(x)=\lim _{x \rightarrow 2} \frac{1}{\sqrt{7 x+2}+\sqrt{6 x+4}}=\frac{1}{\sqrt{16}+\sqrt{16}}=\frac{1}{8}$. Therefore, $k$ must be $\frac{1}{8}$.


