# Support Vector Machines

## Props

- a.k.a. **Support-Vector Networks**

- Supervised Learning

- Classification & Regression Analysis

- Support Vector Clustering ( To categorize unlabelled data )

- Linearly Separable problems

- Linearly non-separable problems

- Non-Linear SVM

- Multi-Class SVM

## Application

### Classification

Suppose some given data points each belong to one of two classes, and the goal is to decide which class a *new* data point will be in. In the case of support-vector machines, a data point is viewed as a $P$ dimensional vector (a list of  $P$  numbers), and we want to know whether we can separate such points with a $( P − 1 )$ dimensional `hyperplane`. This is called a `linear classifier`.

Here, we choose the hyperplane so that the distance from it to the nearest data point on each side is maximized. if such hyperplane exists then is termed as *maximum-margin hyperplane*

#### Linear SVM

**Given :** Dataset : n points of form $(x_n, y_n)$ y either ( 1 or -1 )

<img title="" src="../ImgResources/linearSVM.png" alt="" width="381" data-align="center">

@ Wikipedia

- Each $x_n$ is a  p-dimensional real vector.

- Finding the *maximum-margin hyperplane* that divides the points $x_i$ such that, the distance from either group  of nearest points is maximized.

- Hyperplane : $\vec w.\vec x-b = 0$ where $w$ is the normal vector to the hyperplane

- the parameter $\dfrac{b}{||\vec w||}$  determines the offset of the hyperplane from the origin along the normal vector $\vec{w}$.

- Samples on the margins are called **Support Vectors**.

##### Hard and Soft Margin

### Non-Linear Classification

- Kernel trick

- Common Kernels
  
  - Polynomial ( Homogeneous )
  
  - Polynomial ( inHomogeneous )
  
  - Gaussian radial basis function
  
  - Hyperbolic tangent.

### Empirical risk Minimizaiton
