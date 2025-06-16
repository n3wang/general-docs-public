

9.1 If $f(x)=x^2+2 x-5$ and $g(x)=x^3$, find formulas for the composite functions $f \circ g$ and $g \circ f$.

$$
\begin{aligned}
& (f \circ g)(x)=f(g(x))=f\left(x^3\right)=\left(x^3\right)^2+2\left(x^3\right)-5=x^6+2 x^3-5 \\
& (g \circ f)(x)=g(f(x))=g\left(x^2+2 x-5\right)=\left(x^2+2 x-5\right)^3
\end{aligned}
$$

9.2 Write the function $\sqrt{3 x-5}$ as the composition of two functions.

I Let $g(x)=3 x-5$ and let $f(x)=\sqrt{x}$. Then $(f \circ g)(x)=f(g(x))=f(3 x-5)=\sqrt{3 x-5}$.
9.3 If $f(x)=2 x$ and $g(x)=1 /(x-1)$, find all solutions of the equation $(f \circ g)(x)=(g \circ f)(x)$.
l $(f \circ g)(x)=f(g(x))=f\left(\frac{1}{x-1}\right)=\frac{2}{x-1} \quad$ and $\quad(g \circ f)(x)=g(f(x))=g(2 x)=\frac{1}{2 x-1}$
So, we must solve $\frac{2}{x-1}=\frac{1}{2 x-1}, \quad 4 x-2=x-1, \quad 3 x=1, \quad x=\frac{1}{3}$. Answer
9.4 Write the chain rule formula for the derivative of $f \circ g$
$(f \circ g)^{\prime}(x)=f^{\prime}(g(x)) \cdot g^{\prime}(x)$.
9.5 If $y=F(u)$ and $u=G(x)$, then we can write $y=F(G(x))$. Write the chain rule formula for $d y / d x$, where we think of $y$ as a function of $x$.
l $\frac{d y}{d x}=\frac{d y}{d u} \cdot \frac{d u}{d x}$. Here, the first occurrence of $y$ refers to $y$ as a function of $x$, while the second occurrence of $y$ (on the right side) refers to $y$ as a function of $u$.
9.6 Find the derivative of $\left(x^3-2 x^2+7 x-3\right)^4$.

Use the chain rule. Think of the function as a composition $(f \circ g)(x)$, where $f(x)=x^4$ and $g(x)=$ $x^3-2 x^2+7 x-3$. Then $f^{\prime}(x)=4 x^3$ and $g^{\prime}(x)=3 x^2-4 x+7$. Hence, $\frac{d}{d x}\left(x^3-2 x^2+7 x-3\right)^4=4\left(x^3-\right.$ $\left.2 x^2+7 x-3\right)^3 \cdot\left(3 x^2-4 x+7\right)$.
9.7 Find the derivative of $\frac{1}{\left(3 x^2+5\right)^4}$.

We can write $\frac{1}{\left(3 x^2+5\right)^4}=\left(3 x^2+5\right)^{-4}$. Now we can use the chain rule. Remember that $\frac{d}{d x} x^{\prime}=r x^{\prime-1}$ for any real number $r$. In particular, $\frac{d}{d x} x^{-4}=-4 x^{-5}$. By the chain rule,

$$
\frac{d}{d x}\left(3 x^2+5\right)^{-4}=-4\left(3 x^2+5\right)^{-5} \cdot(6 x)=-\frac{24 x}{\left(3 x^2+5\right)^5}
$$

9.8 Find the derivative of $\sqrt{2 x+7}$.

We can write $\sqrt{2 x+7}=(2 x+7)^{1 / 2}$. By the chain rule,

$$
\frac{d}{d x}(2 x+7)^{1 / 2}=\frac{1}{2}(2 x+7)^{-1 / 2} \cdot(2)=(2 x+7)^{-1 / 2}=\frac{1}{(2 x+7)^{1 / 2}}=\frac{1}{\sqrt{2 x+7}}
$$

$\left[\right.$ Here, we have used $\frac{d}{d v} v^{1 / 2}=\frac{1}{2} v^{-1 / 2}$ and $\left.\frac{d}{d x}(2 x+7)=2.\right]$