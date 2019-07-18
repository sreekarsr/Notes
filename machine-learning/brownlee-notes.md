# Master Machine Learning Algorithms, Jason Brownlee 

## Chapter-2

### (2.1) 
- **Column** - data of a single type(and same scale)
- **Row** - a single entity or observation
- **Cell** - a single value in a row and column(real val/int/category)

### (2.2) Statistical Learning perspective
_f_ - hypothetical function to 'learn'
_Output = f(Input)_
- **Input variables** 
   The *columns* that are the inputs
- **Output variable/response variable** 
   The columns that you would like to predict.
 
- **input vector**
   The group of input variables
   _OutputVariable = f(InputVector)_

Statistics talk - _dependent_ and _independent_ variables
   _DependentVariable = f (IndependentVariables)_

**Common usage** 
input variables - X
ouput variables - Y
   _Y=f(X)_

### (2.3) Computer Science perspective
- **Attributes** of an observation - the columns of a row
   _OutputAttribute=Program(InputAttribute)_
- **Feature** - same as attribute, more commonly used when _features_ must be _extracted_ from the raw data.
- **_Instance_** of data, referring to a row/observation.
   _Prediction = Program(Instance)_

### (2.4) Models and Algos
**Model** can be thought of as the _specific representation learned from data_, and the **Algorithm** as the _process for learning it_.
   _Model=Algorithm(Data)_
e.g. 
   - decision tree/set of coeff- model
   - least sq regression - an algo
 
## Chapter-3
### (3.1) Learning a function
Target function _f_ to _best map_ the input variables (X) to output variables(Y).
There is an error(irreducible)
	Y = f(X) + e

### (3.2) Learning a function to make predictions
Most common ML type - make predictions of Y for new X by learning the mapping Y = f(X). - Called **predictive modeling**

We are interested in - making accurate predictions, and not the form.
_Statistical inferences_ are made by understanding the form of the learned model. 

### (3.3) Techniques for learning a function
Different representations and ML algos made different **assumptions** about the form -like linear/non-linear, shape and structure.

Therefore, **it is important to try a suite of different algorithms on a machine learning problem, because we can't know beforehand which approach will be best (esp. when the form is not known)**

## Chapter-4 Parametric and Nonparametric ML algos

### (4.1) Parametric Machine learning algos
**Assumptions** greatly **simplify** the process, but **_limit_ what you can learn**.

_Algorithms that simplify the function to a **known form** are called **parametric** machine learning algorithms_
>_A learning model that summarizes data with a set of parameters of fixed size(independent of the number of training examples) is called a parametric model. No matter how much data you throw at a parametric model, it won’t change its mind about how many parameters it needs._
>– Artificial Intelligence: A Modern Approach, page 737

**Steps**
1. Select form
2. Learn the coefficients from data

**Common examples of parametric algos**
- Linear regression
   form of a line B0 +B1X1 +B2X2
- Logistic regression
- Linear Discriminant Analysis
- Perceptron
Linear so common, that parametric are called _'linear machine learning algorithms'_

**Benefits**
- Simpler (to understand and interpret)
- Speed
- Less Data required
**Limitations**
- Constrained (specified form)
- Limited complexity(only simpler problems)
- Poor fitting(unlikely to match)

### (4.2) Nonparametric ML Algos
These do not make strong assumptions about the form. Therefore free to learn ANY functional form of data,whilst maintaining some ability to generalize for a new data instance.

**Useful when** - _lot of data but no prior knowledge_
> Nonparametric methods are good when you have a lot of data and no prior knowledge, and when you don’t want to worry too much about choosing just the right features.
> – Artificial Intelligence: A Modern Approach, page 757

Useful to understand - **k-nearest neigbours algo** - makes predictions based on the k most similar training patterns for a new data instance.

#### More examples
- Decision Trees like CART and C4.5
- Naive Bayes
- Support Vector Machines
- Neural Networks

#### Benefits
- **Flexibility** to fit more forms
- **Power** - no/weak assumptions
- **Performance**
#### Limitations
- More data req
- Slower
- Overfitting (harder to explain why specific predictions are made)


## Chapter-5 Supervised, Unsupervised and Semi-Supervised Learning

### (5.1) Supervised ML
We know the correct answers, and the predictions made by the algo are iteratively corrected.
#### Types
- Classification : o/p var is a category eg:recommendation algs
- Regression: o/p var has a real value eg:time series prediction

#### Popular examples
- Linear reg for regression
- Random forest (both)
- SVMs for classification

### (5.2) Unsupervised ML
Only input data and no corresponding output variables.
**GOAL: _to model the underlying structure or distrubution, to learn more about the data_**

#### Subgroups:
- **Clustering** : discover inherent groupings. e.g., grouping customers by purchasing behaviour
- **Association** : discover _rules_ that govern data. e.g.: customer buying A -> customer buying B's likelihood.

### (5.3) Semi-supervised ML
Some data labeled (Y), while others not.
e.g.: photo archive - only some labeled. unlabeled is cheap.
**Use** 
- learning structure - unsupervised
- labeling remaining data - supervised, then use for further data.

## Chapter-6 The Bias-Variance Trade-Off

#### (6.1) Overview
This concerns with _supervised_ ML algos.
We're estimating the mapping (target) fn.
**Three parts of error**
- Bias error
- Variance error
- Irreducible error

Irreducible error cannot be reduced _regardless of what algo is used_
**Causes**
- Chosen framing of the problem
- unknown variables that influence

#### (6.2) Bias Error
**Bias**
   The _simplifying assumptions_ made by a model to make the target function easier to learn.

In _general_ - parametric - high bias
complex problems - Xmeet assumptions

- Low bias -> !lesser!(error in book??) assumptions about form
- High bias -> !!more assumptions(error??) about form.

**Low-bias examples** - Decision Trees, k-Nearest N, SVMs.
**High  bias examples** - Linear reg, Linear disc analysis, Logistic reg.

### (6.3) Variance error
   _The amount that the estimate of the target function will change if different training data was used._

Specifics of the training influences the number and type of parameters used to characterize the mapping

generally non-parametric - high var -due to the flexibility.

**low-variance examples** Linear reg, Linear Disc analysis, Logistic regression.
**high-variance examples** Decision trees, k-NN, SVMs.

### (6.4) Bias-variance Trade-Off
AIM: Low bias and variance - good prediction performance.

**Trend**
- Parametric -> high bias, low var
- Non-parametric -> low bias, high var

**parameterization** - a battle to balance out bias and variance. examples of configuration:
- k-NN algo - increasing the value of k, can increase your bias and dec variance
- SVM algo - changing C parameter, acan change margin and adjust bias and variance.

**No escape** - Bias inc -> var dec & vice-versa

**calculation of bias-variance error terms** - in reality cannot, because we don't know the target function. but the concept can help us.

## Chapter-7 Overfitting and Underfitting

### (7.1) Generalization in Machine Learning

**Inductive learning** is the term used to refer to learning of the target function from training data. _Induction- learning general concepts from specific data.(Opposite of **deduction**)_
**Generalization** - how well concepts learned apply to specific examples not seen by the learning algo.

### (7.2) Statistical Fit
_'Goodness'_ of a fit - statistically, measures used to estimate how well the approximation of the function matches the target function.
Some of these methods assume we know the form - which is not the cse in machine learning.

### (7.3) Overfitting in Machine Learning
_Model that fits the **training** data too well_

**Noise** and **random fluctuations** are _learnt_ as concepts of the model.

Many nonparametric algos have parameters/techniques to limit and constrain _how much detail_ the model learns.
e.g.:_pruning_ a tree

### (7.4) Underfitting in Machine learning
It can _neither model the training data nor generalize to new data_

### (7.5) A Good Fit in Machine learning

**Understanding the goal**
  Observe performance over time as it learns. Plot skill on the training data, and on a **test set**.
  The error decreases, but if for too long, it may overfit and irrelevant detail/noise is accounted -> increasing error on the test set.

_The sweet spot_ - Just before the test set error starts to increase.
(not actually very useful in practice - because info about the test set has leaked into the training of this)

**Two additional methods**
- Resampling methods
- validation dataset.

### (7.6) How To Limit Overfitting
^(same as above)
- Resampling technique to estimate model accuracy
- Hold back a validation dataset.

#### Resampling
   Most popular: _k-fold cross validation_.(train on different subsets of training data, and build an estimate of performance on unseen data)
#### Validation dataset
   Subset of training data held back till the very end of project.(gives an idea of how it does on unseen data)

Cross-validation - the GOLD standard. If avlbl, validation is useful.

#       Part III - Linear Algorithms
## Chapter- 8 Crash Course in Spreadsheet Math
---

## Chapter-9 Gradient Descent for ML
### (9.1) Gradient Descent
- used for: findinfg parameter values minimizing the cost fn. (when params can't be calc analytically)

#### (9.1.1) Intuition
- reaching the bottom of the bowl by moving in small steps along a decrease in cost function.

#### (9.1.2) Gradient Descent Procedure
- setup initial vals (0 or small random)
- calculate the cost
- calculate the derivative(cost) wrt coeffs - call delta
- coefficient = coefficient - (alphaxdelta)
^ repeat till reaching a small val
### (9.2) Batch Gradient Descent
- cost is calculated over entire dataset, for each iteration
- most common
### (9.3) Stochastic Gradient Descent
- can be used when large amount of data is avlbl, and you want it to be computationally inexpensive.
- the update is made only using each training instance, giving rise to a random walk(though slow)
**Steps**
- Order of dataset - randomized
- update procedure with cost on one sample
- go through the dataset several times before stopping
- for large datasets, it is quite quick.

### (9.4) Tips for gradient descent
- Plot cost vs.time
- Learning rate - try values
- Rescale inputs - make them come in the same range
- Few passes
- Plot mean cost(over certain number of updates so that it doesn't look noisy)

## Chapter-10 Linear Regression

### (10.1)
It is a method common to statistics and machine learning(borrowed)

### (10.2) Many names
- assumes y can be exp as linear comb of xs
- simple linear reg- single variable. multiple - multiple input var
- Different techniques: e.g.:ordinary least squares.

### (10.3) LR Model Rep
	_y = B0 + B1x_
B0 - called intercept/bias coeff
- **complexity** of a model - referred to number of coefficients in the model
- a coeff becoming zero -> loss of dependence.
### (10.4) Linear Regression Learning the Model
We'll look at 4 techniques
#### (10.4.2) Simple Linear Regression
- single input -can be easily done using statistical properties like mean, stddev, corr, cov
#### (10.4.2) Oridinary least Squares
- more than one input - we try to minimize the sum of squared residuals.
- treats data as a matrix and uses linear algebra opns to estimate optimal values.
### (10.5) Gradient Descent
- Optimizing process
- useful when large dataset present(either in rows or columns - that may not fit in memory)
#### (10.5.1) Regularized linear regression
- extensions to the linear model.
- seek to minimize both sum of squared error, AND, complexity of model.
##### Most popular
- **Lasso (L1 regularisation)** - modified to minimize also the absolute sum of coefficients.
- **Ridge (L2 regularisation)** - to minimize also the squared absolute sum of coeff.

### (10.6) Making Predictions with Linear Regression
After finding the optimal coeff, plug in the values, to get the predicted values

### (10.7) Preparing Data for linear Regression
Some rules of thumb
- Linear Assuption - transforming data to make the relationship linear(e.g. taking log for exponential rel)
- Remove noise - data cleaning options - to remove outliers
- Remove collinearity - prevent the input values from being highly correlated. Try calculating **pairwise correlations on the data and remove most correlated**
- Gaussian Distributions - LR will make reliable predictions if input and output vars have a a Gaussian dist. (see log or BoxCox).
- Rescale inputs - using standardization/normalization

## Chapter-11 Simple Linear Regression Tutorial
---
## Chapter-12 Linear Regression Tutorial using gradient descent
---
## Chapter-13 Logistic Regression

### (13.1) Logistic Function
1/(1+e^-val)
### (13.3) Representation used for Logistic Regression
val = B0+B1x
y = sigmoid(val)
### (13.4) Logistic regression predicts probabilities
it models the probability of the default class.
P(X) = P(Y=1|X)
**TERMS**
- **odds** - ratio of probability of the event divided by the probability of the event not occuring
- log(odds) = B0+B1X called **log-odds** or **probit**.
The linear relationship is for the log-odds or the probit.
### (13.4) Learning the Logistic Regression Model
- Maximum likelihood estimation - we would like to drive the model to be closer to 1 when the corr output var is 1 and vice versa. Often implemented using optimization algos like **Quasi-Newton method**, though GD can still be used.
### (13.5) Making Predicitions wit Logistiac regression
^same as above eqns 
### (13.6) Prepare data for logistic regression
- Binary  output variable - intended fot binary(two-class) classification problems. Gives the probability of an instance belonging to the default class(0 or 1)
- Remove noise (LR assumes no error in output var)
- Gaussian distribution - **data transforms** of input var can better expose a linear relationship, and thus give a more accurate model. (e.g.: log, root, Box-Cox/ other univariate)
- Remove correlated inputs (taking pairwise)
- Fail to converge - if there are many highly correlated inputs(/sparse data)

## Chapter-14 Logistic Regression Tutorial
---







