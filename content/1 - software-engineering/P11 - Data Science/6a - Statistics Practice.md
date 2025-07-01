

## 4O Real Statistics Interview Questions

### Easy
6.1. Uber: Explain the Central Limit Theorem. Why it is useful? Provide the mathematical Definition of the CLT
?x
Solution \#6.1
The Central Limit Theorem (CLT) states that if any random variable, regardless of distribution, is sampled a large enough number of times, the sample mean will be approximately normally distributed. This allows for studying of the properties for any statistical distribution as long as there is a large enough sample size.
The mathematical definition of the CLT is as follows: for any given random variable $X$, as n approaches infinity,
$$
\bar{X}_n=\frac{X_1+\ldots+X_n}{n} \rightarrow \sim N\left(\mu, \frac{\sigma^2}{n}\right)
$$
At any company with a lot of data, like Uber, this concept is core to the various experimentation platforms used in the product. For a real-world example, consider testing whether adding a new feature increases rides booked in the Uber platform, where each X is an individual ride and is a Bernoulli random variable (i.e., the rider books or does not book a ride). Then, if the sample size is sufficiently large, we can assess the statistical properties of the total number of bookings, as well as the booking rate (rides booked / rides opened on app). These statistical properties play a key role in hypothesis testing. allowing companies like Uber to decide whether or not to add new features in a data-driven manner.

---

6.2. Facebook: How would you explain a confidence interval to a non-technical audience?
?x
Suppose we want to estimate some parameters of a population. For example, we might want to estimate the average height of males in the U.S. Given some data from a sample, we can compute a sample mean for what we think the value is, as well as a range of values around that mean. Following the previous example, we could obtain the heights of 1,000 random males in the U.S. and compute the average height, or the sample mean. This sample mean is a type of point estimate and, while useful, will vary from sample to sample. Thus, we can't tell anything about the variation in the data around this estimate, which is why we need a range of values through a confidence interval.
Confidence intervals are a range of values with a lower and an upper bound such that if you were to sample the parameter of interest a large number of times, the $95 \%$ confidence interval would contain the true value of this parameter $95 \%$ of the time. We can construct a confidence interval using the sample standard deviation and sample mean. The level of confidence is determined by a margin of error that is set beforehand. The narrower the confidence interval, the more precise the estimate, since there is less uncertainty associated with the point estimate of the mean.

---

6.3. Twitter: What are some common pitfalls encountered in $\mathrm{A} / \mathrm{B}$ testing?
?x
A/B testing has many possible pitfalls that depend on the particular experiment and setup employed. One common drawback is that groups may not be balanced, possibly resulting in highly skewed results. Note that balance is needed for all dimensions of the groups - like user demographics or device used because, otherwise, the potentially statistically significant results from the test may simply be due to specific factors that were not controlled for. Two types of errors are frequently assessed: Type I error, which is also known as a "false positive," and Type II error, also known as a "false negative." Specifically, Type I error is rejecting a null hypothesis when that hypothesis is correct, whereas Type II error is failing to reject a null hypothesis when its alternative hypothesis is correct.
.
Another common pitfall is not running an experiment for long enough. Generally speaking, experiments are run with a particular power threshold and significance threshold; however, they often do not stop immediately upon detecting an effect. For an extreme example, assume you're at either Uber or Lyft and running a test for two days, when the metric of interest (e.g., rides booked) is subject to weekly seasonality.
.
Lastly, dealing with multiple tests is important because there may be interactions between results of tests you are running and so attributing results may be difficult. In addition, as the number of variations you run increases, so does the sample size needed. In practice, while it seems technically feasible to test 1.000 variations of a button when optimizing for click-through rate, variations in tests are usually based on some intuitive hypothesis concerning core behavior.

---

6.4. Lyft: Explain both covariance and correlation formulaically, and compare and contrast them.
?x
Solution \#6.4
For any given random variables $X$ and $Y$, the covariance, a linear measure of relationship, is defined by the following: $\operatorname{Cov}(X, Y)=E[(X-E[X])(Y-E[Y])]=E[X Y]-E[X] E[Y]$
Specifically, covariance indicates the direction of the linear relationship between $X$ and $Y$ and can take on any potential value from negative infinity to infinity. The units of covariance are based on the units of $X$ and $Y$, which may differ.
The correlation between $X$ and $Y$ is the normalized version of covariance that takes into account the variances of $X$ and $Y$ :

$$
\rho(X, Y)=\frac{\operatorname{Cov}(X, Y)}{\sqrt{\operatorname{Var}(X) \operatorname{Var}(Y)}}
$$


Since correlation results from scaling covariance, it is dimensionless (unlike covariance) and is always between -1 and 1 (also unlike covariance).

---

6.5. Facebook: Say you flip a coin 10 times and observe only one heads. What would be your null hypothesis and p -value for testing whether the coin is fair or not?
?x
Solution \#6.5
The null hypothesis is that the coin is fair, and the alternative hypothesis is that the coin is biased towards tails (note this is a one-sided test):

$$
H_0: p_0=0.5, H_1: p_1<0.5
$$
.
Note that, since the sample size here is 10 , you cannot apply the Central Limit Theorem (and so you cannot approximate a binomial using a normal distribution).
The p-value here is the probability of observing the results obtained given that the null hypothesis is true, i.e., under the assumption that the coin is fair. In total for 10 flips of a coin, there are $2^{\wedge} 10=1024$ possible outcomes, and in only 10 of them are there 9 tails and one heads. Hence, the exact probability of the given result is the p -value, which is $\frac{10}{1024}-0.0098$. Therefore, with a significance level set, for example, at 0.05 , we can reject the null hypothesis.

---

6.6. Uber: Describe hypothesis testing and $p$-values in layman's terms?
Solution \#6.6
The process of testing whether data supports particular hypotheses is called hypothesis testing and involves measuring parameters of a population's probability distribution. This process typically employs at least two groups - one a control that receives no treatment, and the other group(s), which do receive the treatment(s) of interest. Examples could be the height of two groups of people, the conversion rates for particular user flows in a product, etc. Testing also involves two hypotheses the null hypothesis, which assumes no significant difference between the groups, and the alternative hypothesis, which assumes a significant difference in the measured parameter(s) as a consequence of the treatment.
-
A p-value is the probability of observing the given test results under the null hypothesis assumptions. The lower this probability, the higher the chance that the null hypothesis should be rejected. If the p -value is lower than the predetermined significance level $\alpha$, generally set at 0.05 , then it indicates that the null hypothesis should be rejected in favor of the alternative hypothesis. Otherwise, the null hypothesis cannot be rejected, and it cannot be concluded that the treatment has any significant effect.

---

6.7. Groupon: Describe what Type I and Type II errors are, and the trade-offs between them.
?x
Solution \#6.7
Both errors are relevant in the context of hypothesis testing. Type I error is when one rejects the null hypothesis when it is correct, and is known as a false positive. Type II error is when the null hypothesis is not rejected when the alternative hypothesis is correct; this is known as a false negative. In layman's terms, a type I error is when we detect a difference, when in reality there is no significant difference in an experiment. Similarly, a type II error occurs when we fail to detect a difference, when in reality there is a significant difference in an experiment.
Type 1 error is given by the level of significance $\alpha$, whereas the type II error is given by $\beta$. Usually, $1-\alpha$ is referred to as the confidence level, whereas $1-\beta$ is referred to as the statistical power of the test being conducted. Note that, in any well-conducted statistical procedure, we want to have both $\alpha$ and $\beta$ be small. However, based on the definition of the two, it is impossible to make both errors small simultaneously: the larger a is, the smaller B is. Based on the experiment and the relative importance of false positives and false negatives, a data scientist must decide what thresholds to adopt for any given experiment. Note that experiments are set up so as to have both |-a and 1-6 relatively high (say at .95, and .8, respectively).

---

6.8. Microsoft: Explain the statistical background behind power.
?x
Solution \#6.8
Power is the probability of rejecting the null hypothesis when, in fact, it is false. It is also the probability of avoiding a Type II error. A Type II error occurs when the null hypothesis is not rejected when the alternative hypothesis is correct. This is important because we want to detect significant effects during experiments. That is, the higher the statistical power of the test, the higher the probability of detecting a genuine effect (i.e, accepting the alternative hypothesis and rejecting the null hypothesis). A minimum sample size can be calculated for any given level of power - for example, say a power level of 0.8 .
An analysis of the statistical power of a test is usually performed with respect to the test's level of significance $(\alpha)$ and effect size (ie., the magnitude of the results).

---

6.9. Facebook: What is a Z-test and when would you use it versus a t-test?
?x
Solution \#6.9
In a Z-test, your test statistic follows a normal distribution under the null hypothesis. Alternatively, in a t-test, you employ a student's t-distribution rather than a normal distribution as your sampling distribution.
Considering the population mean, we can use either Z-test or t-test only if the mean is normally distributed, which is possible in two cases: the initial population is normally distributed, or the sample size is large enough ( $n \geq 30$ ) that we can apply the Central Limit Theorem.
If the condition above is satisfied, then we need to decide which type of test is more appropriate to use. In general, we use $Z$-tests if the population variation is $k n o w n$, and vice versa: we use $t$-test if the population variation is unknown.
Additionally, if the sample size is very large ( $n>200$ ), we can use the $Z$-test in any case, since for such large degrees of freedom, $t$-distribution coincides with $z$-distribution up to thousands.
Considering the population proportion, we can use a $Z$-test (but not $t$-test) where $n p_0 \geq 10$ and $n\left(1-p_0\right) \geq$ 10. i.e., when each of the number of successes and the number of failures is at least 10 .

---

6.10. Amazon: Say you are testing hundreds of hypotheses, each with t-test. What considerations would you take into account when doing this?
Medium
?x
Solution \#6.10
The primary consideration is that, as the number of tests increases, the chance that a stand-alone p -value for any of the t-lests is statistically significant becomes very high due to chance alone. As an example, with 100 tests performed and a significance threshold of $\alpha=0.05$. you would expect five of the experiments to be statistically significant due only to chance. That is, you have a very high probability of observing at least one significant outcome. Therefore, the chance of incorrectly rejecting a null hypothesis (i.e., committing Type I error) increases.
To correct for this effect. we can use a method called the Bonferroni correction, wherein we set the significance threshold to $\omega / m$, where $m$ is the number of tests being performed. In the above scenario with 100 tests, we can set the significance threshold to instead be $0.05 / 100=0.0005$. While this correction helps to protect from Type I error. it is still prone to Type II error (i.e., failing to reject the null hypothesis when it should be rejected). In general, the Bonferroni correction is mostly useful when there is a smaller number of multiple comparisons of which a few are significant. If the number of tests becomes sufficiently high such that many tests yield statistically significant results. the number of Type II errors may also increase significantly.


### Medium

6.11. Google: How would you derive a confidence interval for the probability of flipping heads from a series of coin tosses?
?x
Solution \#6.11
The confidence interval (CI) for a population proportion is an interval that includes a true population proportion with a certain degree of confidence $1-\alpha$.
For the case of flipping heads from a series of coin tosses, the proportion follows the binomial distribution. If the series size is large enough (each of the number of successes and the number of failures is at least 10), we can utilize the Central Limit Theorem and use the normal approximation for the binomial distribution as follows:
$$
N\left(\hat{p}, \frac{\hat{p}(1-\hat{p})}{n}\right)
$$
where $\hat{p}$ is the proportion of heads tossed in series, and $n$ is the series size. The Cl is centered at the series proportion, and plus or minus a margin of error:
$$
\hat{p} \pm z_{\mathrm{a} / 2} \sqrt{\frac{\hat{p}(1-\hat{p})}{n}}
$$where $z_{\mathrm{a} / 2}$ is the appropriate value from the standard normal distribution for the desired confidence level.
For example, for the most commonly used level of confidence, $95 \%, z_{0 / 2}=1.96$.


---

6.12. Two Sigma: What is the expected number of coin flips needed to get two consecutive heads?
?x
Solution \#6.12
Let $X$ be the number of coin flips needed to obtain two consecutive heads. We then want to solve for $E[X]$. Let H denote a flip that results in heads, and T denote a flip that results in tails. Note that $\mathrm{E}[X]$ can be written in terms of $\mathrm{E}[X \mid \mathrm{H}]$ and $\mathrm{E}[X \mid \mathrm{T}]$, i.e., the expected number of flips needed, conditioned on a flip being either heads or tails, respectively.
Conditioning on the first flip, we have: $E[X]=\frac{1}{2}(1+E[X \mid H])+\frac{1}{2}(1+E[X \mid T])$
Note that $\mathrm{E}[X \mid \mathrm{T}]=\mathrm{E}[X]$ since if a tail is flipped, we need to start over in getting two heads in a row.
To solve for $\mathrm{E}[X \mid \mathrm{H}]$, we can condition it further on the next outcome: either heads (HH) or tails (HT).
Therefore, we have: $E[X \mid H]=\frac{1}{2}(1+E[X \mid H H])+\frac{1}{2}(1+E[X \mid H T])$
Note that if the result is HH , then $\mathrm{E}[X \mid \mathrm{HH}]=0$, since the outcome has been achieved. If a tail was flipped, then $\mathrm{E}[X \mid \mathrm{HT}]=\mathrm{E}[X]$, and we need to start over in attempting to get two heads in a row. Thus:
$$
E[X \mid H]=\frac{1}{2}(1+0)+\frac{1}{2}(1+E[X])=1+\frac{1}{2} E[X]
$$
Plugging this into the original equation yields:
$$
E[X]=\frac{1}{2}\left(1+1+\frac{1}{2} E[X]\right)+\frac{1}{2}(1+E[X])
$$and after solving we get: $E[X]=6$. Therefore, we would expect 6 flips.

---


6.13. Citadel: What is the expected number of rolls needed to see all six sides of a fair die?
?x


6.14. Akuna Capital: Say you're rolling a fair six-sided die. What is the expected number of rolls until you roll two consecutive 5 s ?
6.15. D.E. Shaw: A coin was flipped 1,000 times, and 550 times it showed heads. Do you think the coin is biased? Why or why not?
6.16. Quora: You are drawing from a normally distributed random variable $X \sim \mathrm{~N}(0,1)$ once a day. What is the approximate expected number of days until you get a value greater than 2 ?
6.17. Akuna Capital: Say you have two random variables $X$ and $Y$, each with a standard deviation. What is the variance of $a X+b Y$ for constants $a$ and $b$ ?
6.18. Google: Say we have $X \sim \operatorname{Uniform}(0,1)$ and $Y \sim \operatorname{Uniform}(0,1)$ and the two are independent. What is the expected value of the minimum of $X$ and $Y$ ?
6.19. Morgan Stanley: Say you have an unfair coin which lands on heads $60 \%$ of the time. How many coin flips are needed to detect that the coin is unfair?
6.20. Uber: Say you have $n$ numbers $1 \ldots n$, and you uniformly sample from this distribution with replacement $n$ times. What is the expected number of distinct values you would draw?
6.21. Goldman Sachs: There are 100 noodles in a bowl. At each step, you randomly select two noodle ends from the bowl and tie them together. What is the expectation on the number of loops formed?
6.22. Morgan Stanley: What is the expected value of the max of two dice rolls?
6.23. Lyft: Derive the mean and variance of the uniform distribution $\mathrm{U}(a, b)$.
6.24. Citadel: How many cards would you expect to draw from a standard deck before seeing the first ace?
6.25. Spotify: Say you draw n samples from a uniform distribution $\mathrm{U}(a, b)$. What are the MLE estimates of $a$ and $b$ ?


### Hard
Hard questiosnare to be continued

