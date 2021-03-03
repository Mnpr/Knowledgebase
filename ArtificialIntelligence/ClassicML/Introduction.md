# Introduction

*Aims of machine learning*

- Describe different learning paradigm, algorithm, theoretical results, applications
  
  - Understand learning by  building learning systems("synthetic "approach)

- Realize improvements in technical systems based on data interpretation or on interaction with environment using learning algorithms( artificial Intelligence)

## Dimensions of Machine Learning;

- **Learning Modes**
  
  - Supervised Learning
  
  - Unsupervised Learning
  
  - Reinforcement Learning

- **Availability of training example**s : offline / online / active learning

- **Learning Tasks :** Classification, Regression, Clusturing, Data Preprocessing, Density Estimation ( *Depending on the learning mode* )

- **Concept/ Knowledge representation :** Decision tree, Neural Network, Support Vector Machine, Statistical Model, Parameterized funciton, ...

- **Machine Learning models & Algorithms :** Backpropagation , maximum likelihood training, ...

- **Generalisation**

### Machine learning: Issues and aspects

- What clues can we get from biological learning systems?

- How to select suitable features?
  
  - Invariance to irrelevant input variations
  
  - Encoding and use of „domain knowledge“

- What algorithms can approximate functions well (and when)?

- How does the size of the training set influence accuracy?

- How does the complexity of the hypothesis representation impact
  accuracy?

- How does noisy data influence accuracy?

- What are the theoretical limits of learnability?

- How can prior knowledge help?

- How can systems adapt to the enviroment?

### Issues :

- Finding efficient feature representation
  
  - Feature selection
  
  - Dimensionality reduction( Linear Discriminant Analysis )\

- Decision Criterion
  
  - Bayes decision Theory

- What is our Model ?
  
  - Hidden Markov Models
  
  - Gaussian mixture models

- How to Estimate parameters ?
  
  - Maximum Likelihood
  
  - Discriminative training

- How to improve our model ?
  
  - Adaptation
  
  - Model Combination

- How to incorporatet prior Knowledge
  
  - Bayes decision Theory

### Main Applicaiton Domains

- Data Mining
  
  - Automatic detection of regularity in big amounts of data
  
  - E.g. Medical records -> medical knowledge/ Decision support
    
    - using historical data to improve decisions

- Software applications which cannot be easily programmed by hand

- Self Customizing programs
  
  - System that automatically adatps e.g. user preferences
  
  - e.g. Newsreader that learns user interests

- Speech recognition

- Natural language processing, Machine translation

- Computer Vision

- Medical decision support

- Bio-Informatics

- Robot Control

- Application in Speech/ Document processing
  
  - Information Extraction
  
  - Part-of-Speech tagging
  
  - Question Answering
  
  - Document Classification
  
  - Topic Segmentation
  
  - Machine Translation

#### Example :

Credit risk management :

*Use past experience of  bank to automatically construct a decision support program*

*Classification :* Good and Bad customer

*Regression:* Prediction gain or Loss for the bank

**Formalization**

- Machine that learns to perform task from experience.

$y = f(X;W)$

$y$ : Output variable

$X$ : Input variable

$W$ : model parameters

- **Learn :** Adjust the parameter W

- **Task** : The funciton $f$

- **Experience :** Using training datased $D$, where of 

either

$D = \{(x^{(1)},y^{(1)}), ...,(x^{(p)},y^{(p)})\}$ : **Supervised Learning**

or

$D=\{x^{(1)}, ... , x^{(p)}\}$ : **Unsupervised Learning**

# Learning Modes

## Supervised Learning

Given : input/ label pars $D = {(x^{(1)},y^{(1)}), ...,(x^{(p)},y^{(p)})}$

- Desired output ("Teacher") given in addition to input.

- Goal : **Learn functional relation** between input $x$ and desired output $y$
  
  - Generalization to unseen data : given new input $x$, predict $y=f(x; w)$

*Classification:*

- Desired output is taken from a small set of possibilities

- Patterns are partitioned into classes( corresponding to desired output )

- e.g. Digit Recognition

*Regression:*

- Desired output is a numerical value

- Mathematical function is learned

- e.g. Weather forecast (maximal temperature)

## Unsupervised Learning

Given : input data points $D=\{x^{(1)}, ... , x^{(p)}\}$

- No ouput labels

- Goal : 
  
  - **Clustering :** Find groupings of data
  
  - **Density Estimation** : Determine the data distribution $p(x)$
  
  - **Dimensionality Reduction** 

## Reinforcement Learning

- Given : Sequence of Situations, Actions & Rewards

- Goal :
  
  - Learn the **Behaviour**/ **Policy** that maximizes the reward.
  
  - Tradeoff Between **Exploration** & **Exploitation**.
    
    - Exploration( *try out new actions* )
    
    - Exploitation( *use known actions that yeilds high rewards* )

- Learn a set of action based on current situation( Learning a policy )

- Maximizing the reward for suitable sequence of actions

### Learning Modes ( Based on Availability of examples during training  )

- ### Batch Learning( Offline )

- Batch set of training examples are provided during training

- ### Incremental Learning( Online )

- Constant stream( Step-by-step ) of training examples.

- ### Active Learning

- The label may be corrected while learning.

# Algorithms

- Classification
  
  - **K-nearest neinghbor**
  
  - Perceptron/ Neural networks
  
  - **Support Vector Machine**
  
  - Decision Tree
  
  - Bayesian Classifier etc.

- Regression
  
  - Linear Regression
  
  - Logistic Regression
  
  - Non-Linear Regression
  
  - Non Parametric Regression

- Clustering

- Outlier Detection

- Single class Classification

- Density estimation

- Data Preprocessing

- Knowledge Representation / Model
  
  - Explicit representation
    
    - Perveptron, Neural networks
    
    - SVM
    
    - Decision Tree
    
    - HMM
    
    - Mathematical Funciton
  
  - Implicit Representation
    
    - KNN

- Maps
