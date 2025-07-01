

## Theory

#### Properties of Random Variable

For any given random variable X, the following properties hold true (below we assume X is continuous, but it also holds true for discrete random variables). The expectation (average value, or mean) of a random variable is given by the integral of the value

The expectation (average value, or mean) of a random variable is given by the integral of the value of $X$ with its probability density function (PDF) $f x(x)$ :
?x
Think of **expectation** as the **center of mass**:  
You're **weighing each value xxx** by how likely it is (its **density** fX(x)f_X(x)fX​(x)).
> _"Expectation = weighted average of outcomes"_
> 
> 
$$
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

$$
E[X \mid Y=y]=\int_x^x x f_{X \mid Y}(x \mid y) d x
$$


For any given random variables $X$ and $Y$, the covariance, a linear measure of relationship between the two variables, is defined by the following:
Measures **how X and Y move together**:
- **Positive**: both increase/decrease together
- **Negative**: one increases while other decreases
"Covariance = average product of their deviations from mean"
:p provide the formula for calculating the Covariance between X and Y given Expectation of them
?x
$$
\operatorname{Cov}(X, Y)=E[(X-E[X])(Y-E[Y])]=E[X Y]-E[X] E[Y]
$$

and the normalization of covariance, represented by the Greek letter $\rho$, is the correlation between $X$ and $Y$ :
?x
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
Although it is not necessary to memorize the derivations for all the different probability distributions, you should be comfortable deriving them as needed, as it is a common request in more technical interviews. To this end, you should make sure to understand the formulas given above and be able to apply them to some of the common probability distributions like the exponential or uniform distribution.


#### Law of Large Numbers
The Law of Large Numbers (LLN) states that if you sample a random variable independently a large number of times, the measured average value should converge to the random variable's true expectation. Stated more formally,

$$
\bar{X}_n=\frac{X_1+\ldots+X_n}{n} \rightarrow \mu, \text { as } n \rightarrow \infty
$$


This is important in studying the longer-term behavior of random variables over time. As an example, a coin might land on heads 5 times in a row, but over a much larger $n$ we would expect the proportion

#### Hypothesis Testing
**General Setup**
The process of testing whether or not a sample of data supports a particular hypothesis is called hypothesis testing. Generally, hypotheses concern particular properties of interest for a given population, such as its parameters, like $\mu$ (for example, the mean conversion rate among a set of users).
The steps in testing a hypothesis are as follows: 
:p provide the 3 steps to create the hypothesis testing
?x
1. State a null hypothesis and an alternative hypothesis. Either the null hypothesis will be rejected (in favor of the alternative hypothesis), or it will fail to be rejected (although failing to reject the null hypothesis does not necessarily mean it is true, but rather that there is not sufficient evidence to reject it).
2. Use a particular test statistic of the null hypothesis to calculate the corresponding $\rho$-value.
3. Compare the p -value to a certain significance level $\alpha$.

Since the null hypothesis typically represents a baseline (e.g., the marketing campaign did not increase conversion rates, etc.), the goal is to reject the null hypothesis with statistical significance and hope that there is a significant outcome.
Hypothesis tests are either one- or two-tailed tests. A one-tailed test has the following types of null and alternative hypotheses:
$$
H_0: \mu=\mu_0 \text { versus } H_1: \mu<\mu_0 \text { or } H_1: \mu>\mu_0
$$

whereas a two-tailed test has these types: $H_0: \mu=\mu_0$ versus $H_1: \mu \neq \mu_0$
where $H_0$ is the null hypothesis and $H_1$ is the alternative hypothesis, and $\mu$ is the parameter of interest.

#### Z-Test
Generally the Z-test is used when the sample size is large (to invoke the CLT) or when the population variance is known, and a $t$-test is used when the sample size is small and when the population variance is unknown. The $Z$-test for a population mean is formulated as:
:p Provide the Z test population formula, When does it make sense to use z-tests?
You're comparing your **sample mean** to a known **population mean**, and you **know how spread out the population is (σ)**.
“How many standard errors away is my sample mean from what I expected?”
- You **know** the population standard deviation σ\sigmaσ
- Your **sample size is large** (usually n≥30n \geq 30n≥30)
?x
$$
z=\frac{\bar{x}-\mu_0}{\sigma / \sqrt{n}} \sim N(0,1)
$$
in the case where the population variance $\sigma^2$ is known.
$z=\frac{\text { sample mean }- \text { expected mean }}{\text { standard deviation } / \sqrt{n}}$


#### $t$-Test
The $t$-test is structured similarly to the $Z$-test, but uses the sample variance $s^2$ in place of population variance. The $t$-test is parametrized by the degrees of freedom, which refers to the number of independent observations in a dataset, denoted below by $n-1$ :
:p Provide the T test formula given ean, the sample, Whend does it make sense to use t-tests?
“Given that I’m estimating the standard deviation, is my sample mean far enough from the expected mean?”
- You **do NOT know σ**
- Sample size is **small**
- You assume the underlying data is **roughly normal**
?x
$$
t=\frac{\bar{x}-\mu_0}{s / \sqrt{n}} \sim t_n
$$
$$
t=\frac{\text { sample mean }- \text { expected mean }}{\text { sample standard deviation } / \sqrt{n}}
$$


where $s^y-\frac{\sum^n(x, \bar{x})^2}{n \cdot 1}$



#### Chi-Squared Test
The Chi-squared test statistic is used to assess goodness of fit, and is calculated as follows:
:p Provide Chi Squared Test Formula, When does it make sense to use Chi Squared Tests?
“Are the differences between what I saw and what I expected **too big to be random**?”
- Data is **counts** or **frequencies**
- You want to test **how well the data fits** an expected pattern (or independence)
?x
$$
\chi^2=\sum_i \frac{\left(O_i-E_i\right)^2}{E_i}
$$
$$
\chi^2=\sum \frac{(\text { observed }- \text { expected })^2}{\text { expected }}
$$
where $O_i$ is the observed value of interest and $E_i$ is its expected value. A Chi-squared test statistic takes on a particular number of degrees of freedom, which is based on the number of categories in the distribution.
.
To use the squared test to check whether two categorical variables are independent, create a table of counts (called a contingency table), with the values of one variable forming the rows of the table and the values of the other variable forming its columns, and check for intersections. It uses the same style of Chi-squared test statistic as given above.

#### Hypothesis Testing for Population Proportions
Note that, due to the CLT, the Z-test can be applied to random variables of any distribution. For example, when estimating the sample proportion of a population having a characteristic of interest, we can view the members of the population as Bernoulli random variables, with those having the characteristic represented by " 1 s " and those lacking it represented by " 0 s ". Viewing the sample proportion of interest as the sum of these Bernoulli random variables divided by the total population size, we can then compute the sample mean and variance of the overall proportion, about which we can form the following set of hypotheses:

$$
H_0: \hat{p}=p_0 \text { versus } H_1: \hat{p} \neq p_0
$$

and the corresponding test statistic to conduct a $Z$-test would be: $z=\frac{\hat{p}-p_0}{\sqrt{p_0\left(1-p_0\right)} / n}$
In practice, these test statistics form the core of A/B testing. For instance, consider the previously discussed case, in which we seek to measure conversion rates within groups $A$ and $B$, where $A$ is the control group and B has the special treatment (in this case, a marketing campaign). Adopting the same null hypothesis as before, we can proceed to use a Z-test to assess the difference in empirical population means (in this case, conversion rates) and test its statistical significance at a predetermined level.
When asked about A/B testing or related topics, you should always cite the relevant test statistic and the cause of its validity (usually the CLT).


#### p-values and Confidence Intervals
In conducting a hypothesis test, an $\alpha$, or measure of the acceptable probability of rejecting a true null hypothesis, is typically chosen prior to conducting the test. Then, a confidence interval can also be calculated to assess the test statistic. This is a range of values that, if a large sample were taken, would contain the parameter value of interest $(1-\alpha) \%$ of the time. For instance, a $95 \%$ confidence interval would contain the true value $95 \%$ of the time. If 0 is included in the confidence intervals, then we cannot reject the null hypothesis (and vice versa).
The general form for a confidence interval around the population mean looks like the following, where the term is the critical value (for the standard normal distribution):
.
$$
\mu \pm z_{i, v / 2} \frac{\sigma}{\sqrt{n}}
$$
.
In the prior example with the $\mathrm{A} / \mathrm{B}$ testing on conversion rates, we see that the confidence interval for a population proportion would be
-
$$
\hat{p} \pm z_{\mathrm{a} / 2} \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}
$$
.
since our estimate of the true proportion will have the following parameters when estimated as approximately Gaussian:
.
$$
\mu=\frac{n p}{n}=p, \sigma^2=\frac{n p(1-p)}{n^2}=\frac{p(1-p)}{n}
$$
.
As long as the sampling distribution of a random variable is known, the appropriate p -values and confidence intervals can be assessed.
:p Explain p-values and confidence intervals in nontechical terms
?x
“The p-value tells you how surprised you should be if the null hypothesis were true.”
- Imagine flipping a coin that’s supposed to be fair. If you get 95 heads out of 100 flips, the **p-value** is the chance of getting that result **by luck** — and if it’s really low, you **start doubting the coin is fair**.
> “The confidence interval gives you a smart guess range for where the **true value** might be.”
- If you build a 95% confidence interval around your sample result, you're saying:
> “If I repeated this many times, 95 out of 100 intervals would catch the real answer.”


#### Type I and II Errors
There are two errors that are frequently assessed: type I error, which is also known as a "false positive." and type II error, which is also known as a "false negative." Specifically, a type I error is when one rejects the null hypothesis when it is correct, and a type II error is when the null hypothesis is not rejected when it is incorrect.
![[Pasted image 20250701154755.png]]
:p What is a type I and type II in a example situation?
?x
Usually $1-\alpha$ is referred to as the confidence level, whereas $1-\beta$ is referred to as the power. If you plot sample size versus power, generally you should see a larger sample size corresponding to a larger power. It can be useful to look at power in order to gauge the sample size needed for detecting a significant effect. Generally, tests are set up in such a way as to have both $1-\alpha$ and $1-\beta$ relatively high (say at 0.95 and 0.8 , respectively).
In testing multiple hypotheses, it is possible that if you ran many experiments --- even if a particular outcome for one experiment is very unlikely - you would see a statistically significant outcome at least once. So, for example, if you set $\alpha=0.05$ and run 100 hypothesis tests, then by pure chance you would expect 5 of the tests to be statistically significant. However, a more desirable outcome is to have the overall $\alpha$ of the 100 tests be 0.05 , and this can be done by setting the new $\alpha$ to $\alpha / n$, where $n$ is the number of hypothesis tests (in this case, $\alpha / n=0.05 / 100=0.0005$ ). This is known as Bonferroni correction, and using it helps make sure that the overall rate of false positives is controlled within a multiple testing framework.

#### MLE and MAP
Any probability distribution has parameters, so fitting parameters is an extremely crucial part of data analysis. There are two general methods for doing so. In maximum likelihood estimation (MLE), the goal is to estimate the most likely parameters given a likelihood function: $\theta_{M L E}=\arg \max L(\theta)$, where $L(\theta)=f_n\left(x_1 \ldots x_n \mid \theta\right)$.
Since the values of $X$ are assumed to be i.i.d., then the likelihood function becomes the following:
-
$$
L(\theta)=\prod_{i+1}^n f\left(x_i \mid \theta\right)
$$

> Multiply the probability of each data point, assuming the parameter is $θ$. The higher the product, the more likely it is that θ is the correct setting.


The natural $\log$ of $L(\theta)$ is then taken prior to calculating the maximum; since log is a monotonically increasing function, maximizing the $\log$-likelihood $\log L(\theta)$ is equivalent to maximizing the likelihood:
$$
\log L(\theta)=\sum_{i=1}^n \log f\left(x_i \mid \theta\right)
$$

> - **Products** are hard to work with, **sums** are easier.The **log doesn’t change the maximum**, because it’s a **monotonic function** (order stays the same). This version is called the **log-likelihood**, and it simplifies the math.

Another way of fitting parameters is through maximum a posteriori estimation (MAP), which assumes a "prior distribution:"
$$
\theta_{M U P}=\arg \max g(\theta) f\left(x_1 \ldots x_n \mid \theta\right)
$$

> MAP estimation finds the value of θ that is most **probable given the data**, not just most likely to produce the data.

where the similar log-likelihood is again employed, and $g(\theta)$ is a density function of $\theta$.
Both MLE and MAP are especially relevant in statistics and machine learning, and knowing these is recommended, especially for more technical interviews. For instance, a common question in such interviews is to derive the MLE for a particular probability distribution. Thus, understanding the above steps, along with the details of the relevant probability distributions, is crucial.

:p Explain Maximum Likelihood Estimation and Maxium A Posteriri estimation ideas and formulas in non technical way

??x
**MLE**
You’ve collected some data — like seeing the results of 100 coin flips — and now you're asking:
“What’s the most likely setting (parameter) that explains what I saw?”
MLE says: “Pick the parameter that makes the data you observed the most likely.”
**MAP**
“Pick the parameter that is most likely given both the data and what you believed before.”
“Choose the recipe that both explains the flavor **and** matches what you already thought the baker probably used.”
x??
