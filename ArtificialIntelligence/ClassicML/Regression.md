# Regression

A set of statistical processes for estimating the relationships between a dependent variable (often called the 'outcome variable') and one or more independent variables (often called 'predictors', 'covariates', or 'features'). 

**Components of Regression model :**

- The **unknown parameters**, often denoted as a scalar  or vector  $\beta$

- The **independent variables**, which are observed in data and are often denoted as a vector $X_i$ where $i$ denotes a row of data.

- The **dependent variable**, which are observed in data and often denoted using the scalar $Y_i$.

- The **error terms**, which are _not_ directly observed in data and are often denoted using the scalar $e_i$.

- **$Y_i = f(X_i,\beta) + e_i$**

- Where, $Y_i$ is a funciton of $X_i$ and $\beta$, with $e_i$ representing additive error term that may stand in for un-modelled determinants of $Y_i$ or random statistical noise.

@Wikipedia.

**Applications :**

- Prediction & Forecasting

- Infer [causal relationships](https://en.wikipedia.org/wiki/Causality "Causality") between the independent and dependent variables.

**Types:**

- **Linear Regression**
  
  - Least Mean Square LR
  
  - Bayesian LR
  
  - Perceptron / SVM

- **Non-Linear Regression**
  
  - Model function non linear in the parameters( Iterative parameter Estimation )
  
  - e.g. Perceptron

- **Non-Parametric Regression**
  
  - Regression Tree/ Decision Tree Learning

## Linear Regression

Linear regression is a **linear model**, e.g. a model that assumes a linear relationship between the input variables $(x)$ and the single output variable $(y)$. $y =$ linear combination of the input variables $(x)$.

**Simple Linear Regression** ( Single Input Variable )

$y = \beta_0 + \beta_1*x$

when coefficient $\beta_1$ becomes zero, it effectively removes the influence of the input variable on the model.

*Ref : Regression.ipynb*

**Multiple Linear Regression**( Multiple Input Variables )

*Ref : Regression.ipynb*

( From FH Lecture )

- [ ] Mathematical Formumation

## Non-Linear Regression
