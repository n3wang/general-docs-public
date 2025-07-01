[Nick Singh, Kevin Huo - Ace the Data Science Interview_ 201 Real Interview Questions Asked By FAANG, Tech Startups, & Wall Street-Ace the Data Science Interview (2021).pdf](file:///C:/Users/Nelson%20Wang/Koofr/Books/Technical/2%20-%20Data%20Engineering/Nick%20Singh,%20Kevin%20Huo%20-%20Ace%20the%20Data%20Science%20Interview_%20201%20Real%20Interview%20Questions%20Asked%20By%20FAANG,%20Tech%20Startups,%20&%20Wall%20Street-Ace%20the%20Data%20Science%20Interview%20\(2021\).pdf)

## Theory

### Properties of Random Variable

For any given random variable X, the following properties hold true (below we assume X is continuous, but it also holds true for discrete random variables). The expectation (average value, or mean) of a random variable is given by the integral of the value

The expectation (average value, or mean) of a random variable is given by the integral of the value of $X$ with its probability density function (PDF) $f x(x)$ :
?x
Think of **expectation** as the **center of mass**:  
You're **weighing each value xxx** by how likely it is (its **density** fX(x)f_X(x)fX​(x)).
> _"Expectation = weighted average of outcomes"_$$
\mu=E[X]=\int^x x f_X(x) d x
$$

and the variance Var(X) is given by the formula respective to :
"Square the variable, take the mean, then subtract the square of the mean"
:p Provide the formula of the variance using expectancy and mean
?x
$$
\operatorname{Var}(X)=E\left[(X-E[X])^2\right]=E\left[X^2\right]-(E[X])^2
$$


The variance is always non-negative, and its square root is called the standard deviation, which is heavily used in statistics.
Just the **square root of variance** — gives the spread in **original units** of XXX.
"Standard deviation = typical distance from the mean"
:p Provide the formula of the standard deviation using variance, or expectancy and mean
?x
$$
\sigma=\sqrt{\operatorname{Var}(X)}=\sqrt{E\left[(X-E[X])^2\right]}=\sqrt{E\left[X^2\right]-(E[X])^2}
$$


The conditional values of both the expectation and variance are as follows. For example, consider the case for the conditional expectation of $X$, given that $Y=y$ :
:p 
?x
$$
E[X \mid Y=y]=\int_x^x x f_{X \mid Y}(x \mid y) d x
$$


For any given random variables $X$ and $Y$, the covariance, a linear measure of relationship between the two variables, is defined by the following:

$$
\operatorname{Cov}(X, Y)=E[(X-E[X])(Y-E[Y])]=E[X Y]-E[X] E[Y]
$$

and the normalization of covariance, represented by the Greek letter $\rho$, is the correlation between $X$ and $Y$ :

$$
\rho(X, Y)=\frac{\operatorname{Cov}(X, Y)}{\sqrt{\operatorname{Var}(X) \operatorname{Var}(Y)}}
$$


All of these properties are commonly tested in interviews, so it helps to be able to understand the mathematical details behind each and walk through an example for each.
For example, if we assume $X$ follows a Uniform distribution on the interval $[a, b]$, then we have the following:

$$
f_x(x)=\frac{1}{b-a}
$$


Therefore the expectation of $X$ is:

$$
E[X]=\int_a^b x f_X(x) d x=\int_a^b \frac{x}{b-a} d x=\left.\frac{x^2}{2(b-a)}\right|_a ^b=\frac{a+b}{2}
$$



