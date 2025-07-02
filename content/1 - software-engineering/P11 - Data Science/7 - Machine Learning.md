---
tags:
  - CFA
---


## To Research

- [ ] Linear Algebra Terms


## Linear Algebra

What is eigenvectors and what is eigen values?
?x
for some n x n matrix A, x is an eigenvector of A if: Ax = Ax, where > is a scalar. A matrix can represent a linear transformation and, when applied to a vector x, results in another vector called an eigenvector, which has the same direction as x and is in fact x multiplied by a scaling factor i. known as an eigenvalue.

- [ ] for ML engineering and quantitative finance roles, you should be able to whiteboard any follow-up questions on the linear algebra concepts underlying techniques like PCA and linear regression.
- [ ] Other linear algebra topics you’re expected to know are core building blocks like vector spaces, projections, inverses, matrix transformations, determinants, orthonormality, and diagonalization.

###  Gradient Descent

- [ ] ML interviews since they are used to optimize the training of almost all machine learning methods. Besides the usual questions on the high-level concepts and mathematical details,
- [ ] you may be asked when you would want to use one or the other. You might even be asked to implement a basic version of SGD in a coding interview
- [ ] Explain what is gradient descent we can use a version of gradient descent called stochastic gradient descent (SGD), which adds an element of randomness so that the gradient does not get stuck. SGDand compare it with gradient descent BGD

![](https://cdn.mathpix.com/snip/images/xpV8M60gUfzIgNSpofZnI8BHmdjh_0eXnGZnNxiLzd0.original.fullsize.png)




- excel 
- Content Management

## Model Evaluation and Selection
With the math underlying machine learning techniques out of the way, how do we actually choose the best model for our problem, or compare two models against each other? Model evaluation is the process of evaluating how well a model performs on the test set after it's been trained on the train set. Separating out your training data - usually $80 \%$ for the train set - from the $20 \%$ of the test set is critical because the usefulness of a model boils down to how good predictions are on data that has not been seen before.
.
Model selection, as the name implies, is the process of selecting which model to implement after each model has been evaluated. Both steps (evaluation and selection) are critical to get right, because even tiny changes in model performance can lead to massive gains at big tech companies. For example, at Facebook, a model that can cause even a $0.1 \%$ lift in ad click-through rates can lead to $\$ 10+$ million in extra revenue.
.
That's why in interviews, especially during case-study questions where you solve an open-ended problem, discussions often head toward comparing and contrasting models, and selecting the most suitable one after factoring in business and product constraints. Thus, internalizing the concepts covered in this section is key to succeeding in ML interviews.

### Bias - Variance Trade-off

The bias-variance trade-off is an interview classic, and is a key framework for understanding different kinds of models. With any model, we are usually trying to estimate a function $f(x)$, which predicts our target variable $y$ based on our input $x$. This relationship can be described as follows:
$$
y=f(x)+w
$$
where $w$ is noise, not captured by $f(x)$, and is assumed to be distributed as a zero-mean Gaussian random variable for certain regression problems. To assess how well the model fits, we can decompose the error of $y$ into the following:
1 Bias: how close the model's predicted values come to the true underlying $f(x)$ values, with smaller being better
2 Variance: the extent to which model prediction error changes based on training inputs, with smaller being better
3 Irreducible error: variation due to inherently noisy observation processes
p: Explain bias, Variance and Irreducible error in simple terms -What is w in the formula?
?x
Pause and read above

The trade-off between bias and variance provides a lens through which you can analyze different models. Say we want to predict housing prices given a large set of potential predictors (square footage of a house, the number of bathrooms, and so on). A model with high bias but low variance, such as linear regression, is easy to implement but may oversimplify the situation at hand. This high bias but low variance situation would mean that predicted house prices are frequently off from the market value, but the variance in these predicted prices is low. On the flip side, a model with low bias and high variance, such as neural networks, would lead to predicted house prices closer to market value, but with predictions varying wildly based on the input features.

### Model Complexity and Overfitting

Suggests that simpler models are generally more useful and correct than more complicated models. That’s because simpler, more parsimonious models tend to generalize better. Said another way, simpler, smaller models are less likely to overfit (fit too closely to the training data). Overtit models tend not to generalize well out of sample. That’s because during overfitting, the models pick up too much noise or random fluctuations using the training data, which hinders performance on data the model has never seen before.
:p Explain what does the model complxity and overfitting suggest
?x
Pause and read above
![[Pasted image 20250701180408.png]]


#### Regularization
Regularization aims to reduce the complexity of models. In relation to the bias-variance trade-off, regularization aims to decrease complexity in a way that significantly reduces variance while only slightly increasing bias. The most widely used forms of regularization are L1 and L2. Both methods add a simple penalty term to the objective function. The penalty helps shrink coefficients of features, which reduces overfitting. This is why, not surprisingly, they are also known as shrinkage methods.
:p Explain the process of regularization in simple terms, Explain the L1 and L2 form of regularization
?x
Specifically, L1, also known as lasso, uses the absolute value of a coefficient to the objective function as a penalty. On the other hand, L2, also known as ridge, uses the squared magnitude of a coefficient to the objective function. The L1 and L2 penalties can also be linearly combined, resulting in the popular form of regularization called elastic net. Since having models overfit is a prevalent problem in machine learning, it`s important to understand when to use each type of regularization. For example, Ll serves as a feature selection method, since many coefficients shrink to 0 (are zeroed out), and hence, are removed from the model. L2 is less likely to shrink any coefficients to 0 . Therefore, L1 regularization leads to sparser models, and is thus considered a more strict shrinkage operation.


#### Inerpretabiliy & Explainability
linear models have weights which can be visualized and analyzed to interpret the decision making. Similarly, random forests have feature importance readily available to identify what the model is using and learning. There are also some general frameworks that can help with more “black-box” models. One is SHAP (SHapley Additive exPlanation), which uses “Shapley” values to denote the average marginal contribution of a feature over all possible combinations of inputs. Another technique 1S LIME (Local Interpretable Model-agnostic Explanations), which uses sparse linear models built around various predictions to understand how any model performs in that local vicinity.
:p explain ways in which you cna make your models easier to explain.
?x
Stop, read above, and explain

## Model Trainning
Recall the basics: we first train models on a training dataset and then test the models ona testing dataset. Normally, 80% of the data will go towards training data, and 20% serves as the test set. But as we soon cover, there’s much more to model training than the 80/20 train vs. test split.
:p What is the basics on training datasets and testing models?
?x
Stop, read abve, and explain

### Cross Validation
assesses the performance of an algorithm in several subsamples of training data. It consists of running the algorithm on subsamples of the training data, such as the original data without some of the original observations, and evaluating model performance on the portion of the data that was excluded from the subsample. This process is repeated many times for the different subsamples, and the results are combined at the end.
Cross-validation helps you avoid training and testing on the same subsets of data points, which would lead to overfitting. 
:p What is cross validation  and how does this process work, Provide an example of a popular way to do cross-validation? 
??x
One popular way to do cross-validation is called $k$-fold cross-validation. The process is as follows:
1. Randomly shuffle data into equally-sized blocks (folds).
2. For each fold $k$, train the model on all the data except for fold $i$, and evaluate the validation error using block $i$.
3. Average the $k$ validation errors from step 2 to get an estimate of the true error.

| Dataset $\wedge$ |  |  |  |  |  |
| :--- | :--- | :--- | :--- | :--- | :--- |
| Estimation 1 | Test 1 | Train | Train | Train | Train |
| Estimation 2 | Train | Test 2 | Train | Train | Train |
| Estimation 3 | Train | Train | Test 3 | Train | Train |
| Estimation 4 | Train | Train | Train | Test 4 | Train |
| Estimation 5 | Train | Train | Train | Train | Test 5 |

Example of 5-Fold Cross Validation
Another form of cross-validation you're expected to know for the interview is leave-one-out crossvalidation. L.OOCV is a special case of $k$-fold cross-validation where $k$ is equal to the size of the dataset (n). That is, it is where the model is testing on every single data point during the crossvalidation.

x??


how to apply cross-validation for time series data?
?x
Standard k-fold CV can’t be applied, since the time-series data is not randomly distributed but instead is already in chronological order. Therefore, you should not be using data “in the future” for predicting data “from the past.” Instead, you should use historical data up until a given point in time, and vary that point in time from the beginning till the end

### Bootstrapping and Bagging 
The process of bootstrapping is simply drawing observations from a large data sample repeatedly (sampling with replacement) and estimating some quantity of a population by averaging estimates from multiple smaller samples. Besides being useful in cases where the dataset is small, bootstrapping is also useful for helping deal with **class imbalance**: for the classes that are rare, we can generate new samples via bootstrapping. Another common application of bootstrapping is in **ensemble learning**: the process of averaging estimates from many smaller models into a main model. Each individual model is produced using a particular sample from the process. This process of bootstrap aggregation is also known as **bagging**. 
p: What is bootstrapping useful for? What applications?
?x
Stop, read and answer

### Hyperparameter Tuning 
Hyperparameters are important because they impact a model’s training time, compute resources needed (and hence cost), and, ultimately, performance. One popular method for tuning hyperparameters is grid search, which involves forminga grid that is the Cartesian product of those parameters and then sequentially trying all such combinations and seeing which yields the best results. While comprehensive, this method can take a long time to run since the cost increases exponentially with the number of hyperparameters. Another popular hyperparameter tuning method is **random search**, where we define a distribution for each parameter and randomly sample from the joint distribution over all parameters. This solves the problem of exploring an exponentially increasing search space, but is not necessarily guaranteed to achieve an optimal result. 
:p What is Hyperparaeters tuning important for? Provide an example of hypeparametertuning method?
?x
Please read and continue


### Trainning Times and Learning Curves

## Linear Regression

What is the goal of linear regressions?
:p Explain whats the goal using the formula
?x
In linear regression, the goal is to estimate a function $f(x)$, such that each feature has a linear relationship to the target variable $y$, or:
$$
y=X \beta
$$
where $X$ is a matrix of predictor variables and $\beta$ is a vector of parameters that determines the weight of each variable in predicting the target variable. So, how do you compare the performance of two linear regression models?


### Evaluating Linear Regression
:p On what is built the concept of linear regression evaluation? What is the sum of squares formula?
?x
Evaluation of a regression model is built on the concept of a residual: the distance between what the model predicted versus the actual value. Linear regression estimates $\beta$ by minimizing the residual sum of squares (RSS), which is given by the following:
$$
R S S(\beta)=(y-X \beta)^T(y-X \beta)
$$

#### MAE and MSE? in RSS

Two other sum of squares concepts to know besides the RSS are the total sum of squares (TSS) and explained sum of squares (ESS). The total sum of squares is the combined variation in the data ( $E S S+R S S$ ). The explained sum of squares is the difference between TSS and RSS. $R^2$, a popular metric for assessing goodness-of-fit, is given by $R^2=1-\frac{R S S}{T S S}$. It ranges between zero and one, and represents the proportion of variability in the data explained by the model. Other prominent error metrics to measure the goodness-of-fit of linear regression are MSE (mean squared error) and MAE (mean absolute error). MSE measures the variance of the residuals, whereas MAE measures the average of the residuals; hence, MSE penalizes larger errors more than MAE, making it more sensitive to outliers.
:p When it comes to measuring RSS What is the difrference between MSE and MAE?
?x
![[Pasted image 20250701213729.png]]

#### Subset Selection
Subset selection. By default, we use all the predictors in a linear model. However, in practice, it’s important to narrow down the number of features, and only include the most important features. One way is best subset selection, which tries each model with & predictors, out of possible ones, where k < p. Then, you choose the best subset model using a regression metric like R?. While this guarantees the best result, it can be computationally infeasible as p increases (due to the exponential number of combinations to try). Additionally, by trying every option in a large search space, you're likely to get model that overfits with a high variance in coefficient estimates
:p How does subset selection work to reduce models complexity of a regression model?
?x
tries each model with & predictors, out ofp possible ones, where k < p. Then, you choose the best subset model using a regression metric like R?. While this guarantees the best result, it can be computationally infeasible as p increases (due to the exponential number of combinations to try).


What is stepwise selection and how does it work? What it solves? Whats the difference with backward stepwise selection?
?x
we start with an empty model and iteratively add the most useful predictor. In backward stepwise selection, we start with the full model and iteratively remove the least useful predictor. While doing stepwise selection, we aim to find a model with high R? and low RSS, while considering the number of predictors using metnics like AIC or adjusted R?.


### Linear Regression Assumptions
Before you can use this technique, you must validate its four main assumptions to prevent erroneous results.
- Linearity: The relationship between the feature set and the target variable is linear. 
- Homoscedasticity: The variance of the residuals is constant. 
- Independence: All observations are independent of one another. 
- Normality: The distribution of Y is assumed to be normal.
:p explain each point in non technical manner
?x
- **Linearity**: The effect of each input (feature) on the result (output) is consistent. If one feature increases, the result increases or decreases in a straight-line way, not in a curve or zigzag.
- **Homoscedasticity**: The amount of error or noise in the predictions stays about the same no matter what the input values are. It doesn’t get bigger or smaller depending on the situation.
- **Independence**: Each data point is separate and doesn’t influence the others. For example, one person’s income doesn’t affect another’s in your dataset.
- **Normality**: The results (outputs) follow a bell-shaped curve. Most values are around the average, and very high or low values are rare.

### Avoiding Linear Regression Pitfalls

#### Heteroscedasticity
p103











































