
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


