# Classification

Map input X to discrete class e.g. $y\space\epsilon\space\lbrace1,2,...\rbrace$

Input : ( Supervised ) training data

Output:  Classifier ( model )

**Types of classifier**

- Rule based classifier ( if condition & condition | else )

- Linear classifier with parameter vector **w** ( if $W^TX \geq 0$  | else )

## Types of Classification

- Binary Classification

- Multi-class Classificaiton

## Classification Algorithms

- Linear Models
  
  - Logistic Regression
  
  - SVM

- Non-linear Models
  
  - KNN
  
  - Kernel SVM
  
  - Naïve Bayes
  
  - Decision Tree Cl.
  
  - Random Forest Cl.

### Logistic Regression

- The dependent variable is categorical: y ϵ {0, 1}

- A binary dependent variable can have only two values, like 0 or 1, win or lose, pass or fail, healthy or sick, etc

- In this case, the probability distribution of output y as 1 or 0 is modelled. This is called the sigmoid probability (σ)

- If σ(θ Tx) > 0.5, set y = 1, else set y = 0
