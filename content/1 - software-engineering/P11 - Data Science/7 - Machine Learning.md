
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

:p What is cross validation?

























