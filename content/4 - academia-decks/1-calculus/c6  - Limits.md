| Chapter 6 | LIMITS | 35  |
| :-------- | :----- | :-- |
#### 6.1 Definition on Limits

Define Km f(x) = L.
?x
Intuitively, this means that, as $x$ gets closer and closer to $a, f(x)$ gets closer and closer to $L$. We can state this in more precise language as follows: For any $\varepsilon>0$, there exists $\delta>0$ such that, if $|x-a|<\delta$, then $|f(x)-L|<\varepsilon$. Here, we assume that, for any $\delta>0$, there exists at least one $x$ in the domain of $f(x)$ such that $|x-a|<\delta$.


#### 6.2 Limits of a function
6.2 Find $\lim _{u \rightarrow 5} \frac{u^2-25}{u-5}$.

?x
I. The numerator and denominator both approach 0 . However, $u^2-25=(u+5)(u-5)$. Hence, $\frac{u^2-25}{u-5}=u+5$. Thus, $\lim _{u \rightarrow 5} \frac{u^2-25}{u-5}=\lim _{u \rightarrow 5}(u+5)=10$.

6.3 Find $\lim _{x \rightarrow 1} \frac{x^3-1}{x-1}$.
?x
Both the numerator and denominator approach 0 . However, $x^3-1=(x-1)\left(x^2+x+1\right)$. Hence, $\lim _{x \rightarrow 1} \frac{x^3-1}{x-1}=\lim _{x \rightarrow 1}\left(x^2+x+1\right)=1+1+1=3$.

6.4 Find $\lim _{u \rightarrow 0} \frac{5 u^2-4}{u+1}$.
?x
$\lim _{u \rightarrow 0} 5 u^2-4=-4$ and $\lim _{u \rightarrow 0}(u+1)=1$. Hence, by the quotient law for limits,
$$
\lim _{u \rightarrow 0} \frac{5 u^2-4}{u+1}=\frac{-4}{1}=-4
$$


6.6 Find $\lim _{x \rightarrow 4} \frac{x^2-x-12}{x-4}$.
?x
Both the numerator and denominator approach 0 . However, $x^2-x-12=(x+3)(x-4)$. Hence, $\lim _{x \rightarrow 4} \frac{x^2-x-12}{x-4}=\lim _{x \rightarrow 4}(x+3)=7$.


6.7 Find $\lim _{x \rightarrow 1} \frac{x^4+3 x^3-13 x^2-27 x+36}{x^2+3 x-4}$.
?x
Both the numerator and denominator approach 0. However, division of the numerator by the denominator reveals that $x^4+3 x^3-13 x^2-27 x+36=\left(x^2+3 x-4\right)\left(x^2-9\right)$. Hence, $\lim _{x \rightarrow 1} \frac{x^4+3 x^3-13 x^2-27 x+36}{x^2+3 x-4}=$ $\lim _{x \rightarrow 1}\left(x^2-9\right)=1-9=-8$.

6.8 Find $\lim _{x \rightarrow 2} \frac{x^3-5 x^2+2 x-4}{x^2-3 x+3}$.
?x
In this case, neither the numerator nor the denominator approaches 0 . In fact, $\lim _{x \rightarrow 2}\left(x^3-5 x^2+2 x-4\right)=$ -12 and $\lim _{x \rightarrow 2}\left(x^2-3 x+3\right)=1$. Hence, our limit is $\frac{-12}{1}=-12$.

6.9 Find $\lim _{x \rightarrow 0} \frac{\sqrt{x+3}-\sqrt{3}}{x}$.
?x
Both numerator and denominator approach 0. "Rationalize" the numerator by multiplying both numerator and denominator by $\sqrt{x+3}+\sqrt{3}$.
$$
\frac{\sqrt{x+3}-\sqrt{3}}{x} \cdot \frac{\sqrt{x+3}+\sqrt{3}}{\sqrt{x+3}+\sqrt{3}}=\frac{(x+3)-3}{x(\sqrt{x+3}+\sqrt{3})}=\frac{1}{\sqrt{x+3}+\sqrt{3}}
$$
So, we obtain $\lim _{x \rightarrow 0} \frac{1}{\sqrt{x+3}+\sqrt{3}}=\frac{1}{\sqrt{3}+\sqrt{3}}=\frac{1}{2 \sqrt{3}}$.

6.10 Find $\lim _{x \rightarrow 2}\left(\frac{1}{x-2}-\frac{4}{x^2-4}\right)$.
?x
As $x \rightarrow 0$, both terms $1 /(x-2)$ and $4 /\left(x^2-4\right)$ "blow up" (that is, become infinitely large in magnitude). Since $x^2-4=(x+2)(x-2)$, we can factor out $\frac{1}{x-2}$ and simplify:
$$
\frac{1}{x-2}-\frac{4}{x^2-4}=\frac{1}{x-2}\left(1-\frac{4}{x+2}\right)=\frac{1}{x-2}\left(\frac{x+2-4}{x+2}\right)=\frac{1}{x-2}\left(\frac{x-2}{x+2}\right)=\frac{1}{x+2}
$$
Hence, the limit reduces to $\lim _{x \rightarrow 2}[1 /(x+2)]=\frac{1}{4}$.

6.11 Give an $\varepsilon-\delta$ proof of the fact that $\lim _{x \rightarrow 4}(2 x-5)=3$.
?x
Assume $\varepsilon>0$. We wish to find $\delta>0$ so that, if $|x-4|<\delta$, then $|(2 x-5)-3|<\varepsilon$. But, $(2 x-5)-3=2 x-8=2(x-4)$. Thus, we must have $|2(x-4)|<\varepsilon$, or, equivalently, $|x-4|<\varepsilon / 2$. So, it suffices to choose $\delta=\varepsilon / 2$ (or any positive number smaller than $\varepsilon / 2$ ).




