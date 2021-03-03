# Machine Learning

## Introduction

- Applications
  
  - Speech recognition
  
  - Speech / Document Processing
  
  - Fraud Detection
  
  - Medical Decison support
  
  - Optical character recognition
  
  - Marketing: Recommendation
  
  - Spam Classification

- Issues and Aspects

## ML Basics

- Credit risk management example.

- Fish Classification example

- Learing Modes
  
  - Supervised Learning
  
  - Unsupervised
  
  - Reinforcement
  
  - Based on Example presented during training:
    
    - Batch  learning
    
    - Incremental
    
    - Active

- Learning Tasks
  
  - **Classification**
    
    - e.g. Toxicity classification of drug combination.( Toxic | Non-Toxic )
    
    - e.g. Spam classificaiton
    
    - Different classifiers
      
      - KNN
      
      - SVM
      
      - Perceptrons
      
      - DT
      
      - Bayesian Classifier
  
  - **Regression**
    
    - Types of regressions
      
      - Linear
        
        - **Least mean square LR**
          
          - Examples
        
        - Bayesian LR
        
        - Perceptron / SVM( Linear )
      
      - Non-Linear
        
        - Perceptron( Non-linear )
      
      - Non-Parametric
        
        - Regression trees / Decision tree learning
      
      - Mathematical formulations.
  
  - **Clustering**
  
  - Maps
  
  - Outlier detection
  
  - Density estimation
  
  - Data preprocessing
  
  - Single class classification

- Knowledge representation
  
  - Explicit ( model, function, hypothesis, concept)
    
    - Perceptron, SVM, Decision trees, mathematical functions, Hidden markov models e.t.c.
  
  - Not Explicit( e.g. Nearest neighbor classification )

- Machine Learning methods and algorithms
  
  - Dedicated algorithm for specific models
    
    - Perceptrons: Perc. Learning, backprop., gradient learning
    
    - Decision trees : ID3, C4.5, CART
    
    - Probability densities: ML, MAP ...]
  
  - Model selection strategies
    
    - Model selection chapter
  
  - General algorithms to improve accuracy
    
    - e.g. Ensemble methods
    
    - Chapter Ensemble methods.

- Generalization
  
  - e.g. The spiral problem
  
  - Formulation( Math )
  
  - Errors( Training and Validation )
  
  - Overfitting | underfitting
  
  - Cross-validation
  
  - Regulatization

- K - nearest neighbor classifier
  
  - Algorithm
  
  - Mathemital formulation
  
  - Implementation

## Learning Machines

- Perceptrons
  
  - Biological Neuroscience
  
  - Simplified model( Weights, Biases & Threshold )
  
  - Mathematical Formulation
  
  - Perceptron Learning
  
  - Algorithm.
  
  - Ext. MLP

- SVM
  
  - Linear SVM
    
    - Linear Separability
    
    - Statistical learning theory
    
    - Structural risk minimization
    
    - Mathematical Formulation
    
    - Support vectors
    
    - Scaling problem
    
    - Optimizaiton problem
    
    - LSVM Classifier
  
  - Linearly non-separable data
    
    - Soft margin classification
    
    - Optimization problem
  
  - Non-Linear SVMs
    
    - Feature space
    
    - Transformation to feature space
    
    - Kernel Trick
    
    - Mercer's theorem
    
    - e.g. radial basis function kernel
  
  - Multi-class SVMs
    
    - one vs rest
    
    - pairwise classification
    
    - Error-correcting output coding
  
  - SVM Applications
  
  - Advantages and drawbacks

- Decision Trees
  
  - Introduction
  
  - Learning Decision trees
  
  - Digression: Information gain and Entropy
    
    - Entropy as measure of impurity
    
    - Information gain as entropy-based measure of impurity reduction.
  
  - Gini impurity
    
    - Gini Index/ Gini gain
    
    - Continuous attribute values
    
    - Pruning ( Overfitting prevention )
  
  - Regression trees
  
  - Learning decision trees 
    
    - ID3
    
    - C4.5
    
    - CART

## Unsupervised Learning

- Clustering
  
  - K-Means
    
    - e.g. Image Compression
  
  - Heirarchical
    
    - Top-down
    
    - **Bottom-up**
      
      - Distance measure between cluster
        
        - Single linkage
        
        - Complete
        
        - Average
        
        - Centroid
      
      - Dendogram
      
      - Applications

## Dimensionality Reduction

- Feature Extraction
  
  - Feature Selection
  
  - **Feature transformation**
    
    - **LDA, PCA**

- LDA
  
  - Covariance / between-class and within-class scatter.
  
  - Fisher's LDA
  
  - e.g. Fisherfaces
  
  - Two-class problem

- PCA
  
  - Introduction
  
  - Examples
  
  - Eigenfaces, Eigenvoices

- t-SNE
  
  - Algorithm

- Applications: Eigenfaces

## Model Selection

- No Free lunch Theorem: example

- Ugly duckling theorem

- Model selection vs concept selection

- Model selection methods/ criteria
  
  - Validation / Cross-validation
  
  - Bias-variance decomposition
  
  - Occam-s razor
    
    - MDL
  
  - Minimum description length/ Bayes model selection
  
  - Bayes Information Criterion( BIC )
  
  - Akaike Information Criterion( AIC )
  
  - Regularization
  
  - Structural risk minimization

## Ensemble Methods

- Model combination
  
  - Combining classifiers : voting
  
  - Examples ( classificaiton, regression)
  
  - Model averaging : Expected error

- Ensemble formation

- Bagging

- Boosting
  
  - AdaBoost.M1
  
  - AdaBoost.M2
  
  - Applications

## Reinforcement Learning

---

## *Resources*

- Tom M. Mitchell:
  „Machine Learning“
  McGraw Hill (1997)
  – [Machine Learning textbook](http://www.cs.cmu.edu/~tom/mlbook.html)

- Ethem Alpaydin:
  „Introduction to Machine Learning“
  MIT Press (2010)
  – http://mitpress.mit.edu/catalog/item/default.asp?tid=12012&ttype=2

- Stephen Marsland:
  „Machine Learning – An Algorithmic Perspective“
  CRC Press (2009)
  – http://www-ist.massey.ac.nz/smarsland/MLBook.html

- Christopher M. Bishop:
  „Pattern Recognition and Machine Learning“
  Springer (2006)
  – [Christopher Bishop at Microsoft Research](http://research.microsoft.com/en-us/um/people/cmbishop/prml/)

- Simon Haykin:
  „Neural Networks and Learning Machines“
  Prentice Hall (2009)
  – [Haykin, Neural Networks and Learning Machines, 3rd Edition | Pearson](http://www.pearsonhighered.com/educator/product/Neural-Networks-and-Learning-Machines/9780131471399.page)

- Richard O. Duda, Peter E. Hart, David G. Stork :
  „Pattern classification“
  Wiley (2001)
  – http://eu.wiley.com/WileyCDA/WileyTitle/productCd-0471056693.html

- Kevin P. Murphy:
  „Machine Learning – A Probabilistic Perspective“
  MIT Press (2012)
  – [Machine learning textbook](http://www.cs.ubc.ca/~murphyk/MLbook/)

- Peter Flach:
  „Machine Learning – The Art And Science of
  Algorithms that Make Sense of Data“
  Cambridge University Press (2012)

- Shai Shalev-Shwartz, Shai Ben-David:
  „Understanding Machine Learning –
  From Theory to Algorithms“
  Cambridge University Press (2014)

- Jason Bell:
  „Machine Learning – Hands-On for Developers
  and Technical Professionals“
  Wiley (2014)

- Trevor Hastie, Robert Tibshirani, Jerome Friedman:
  „The Elements of Statistical Learning“
  2nd edition, Springer (2009)
  – http://www-stat.stanford.edu/~tibs/ElemStatLearn/

- Francesco Camastra, Alessandro Vinciarelli:
  „Machine learning for Audio, Image and Video Analysis“
  Springer (2008)
  – Preprint freely available at http://www.dcs.gla.ac.uk/~vincia/textbook.pdf

- Aurelien Geron:
  „Hands-On Machine Learning with Scikit-Learn, Keras
  and Tensorflow” (2 nd ed.), O’Reilly (Sept. 2019)
  – https://www.oreilly.com/library/view/hands-on-machine- learning/9781492032632/#toc-start

- Jörg Frochte:
  „Maschinelles Lernen“ (2. Auflage, in German)
  Hanser (2019)
  – https://www.hanser-fachbuch.de/buch/Maschinelles+Lernen/9

- Andriy Burkov:
  „The Hundred-Page Machine Learning Book“
  Andriy Burkov (2019)
  – [The Hundred-Page Machine Learning Book by Andriy Burkov](http://themlbook.com/)

- Olivier Theobald:
  „Machine Learning for Absolute Beginners” (2 nd ed.)
  Scatterplot Press (2017)
  – http://www.scatterplotpress.com/book/machine-learning-for-absolute- beginners-2/

- Sebastian Raschka, Vahid Mirjalili:
  „Python Machine Learning“
  3rd edition, Packt Publishing Ltd. (2019)
  – [Books](https://sebastianraschka.com/books.html)

- Andreas C. Müller, Sarah Guido:
  „Introduction to Machine Learning with Python“
  O‘Reilly Media (2016)
  – Freely available at [Introduction to Machine Learning with Python: A Guide for Data Scientists | Andreas C. Müller, Sarah Guido | download](https://b-ok.org/book/2600143/062a5c)

- Nils J. Nilsson:
  „Introduction to Machine Learning“
  Freely available at
  
  - [Introduction to Machine Learning](http://robotics.stanford.edu/~nilsson/mlbook.html)

- Carl Edward Rasmussen, Christopher K. I. Williams:
  „Gaussian Processing for Machine Learning“
  MIT Press (2006), freely available at
  
  - [Gaussian Processes for Machine Learning: Book webpage](http://www.gaussianprocess.org/gpml/)

- Website of David Aha (not maintained anymore):
  
  - http://home.earthlink.net/~dwaha/research/machine-learning.html

- Tutorial page of Tom Dietterich:
  – [Tutorials on Machine Learning (Tom Dietterich)](http://web.engr.oregonstate.edu/~tgd/projects/tutorials.html)

---
