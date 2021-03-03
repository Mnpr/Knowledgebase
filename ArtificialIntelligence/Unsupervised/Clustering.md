# Clustering

## Todo

- [ ] K-medoids

- [ ] Example of K-means clustering for Image Compression.

- [ ] TopDown -BottomUp definiton.

## Expectation-Maximization

**Latent Variables :** Latent variables are hidden/unobserved variables that make estimation problems difficult, and are often denoted z. Here are the most common settings where there are latent variables:

| Setting                  | Latent variable              $z$ | $x\|z$                            | Comments                                     |
| ------------------------ | -------------------------------- | --------------------------------- | -------------------------------------------- |
| Mixture of $k$ Gaussians | $\textrm{Multinomial}(\phi)$     | $\mathcal{N}(\mu_j,\Sigma_j)$     | $\mu_j\in\mathbb{R}^n, \phi\in\mathbb{R}^k $ |
| Factor Analysis          | $\mathcal{N}(0,I)$               | $\mathcal{N}(\mu+\Lambda z,\psi)$ | $\mu_j\in\mathbb{R}^n$                       |

**Algorithm** ― The Expectation-Maximization (EM) algorithm gives an efficient method at estimating the parameter $\theta$ through maximum likelihood estimation by repeatedly constructing a lower-bound on the likelihood (E-step) and optimizing that lower bound (M-step) as follows:

- <u>E-step</u>: Evaluate the posterior probability $Q_i(z^{(i)})$ that each data point $x^{(i)}$ came from a particular cluster z(i) as follows:

$$
\boxed{Q_i(z^{(i)})=P(z^{(i)}|x^{(i)};\theta)}
$$

- <u>M-step</u>: Use the posterior probabilities $Q_i(z^{(i)})$as cluster specific weights on data points $x^{(i)}$ to separately re-estimate each cluster model as follows:

$$
\boxed{\theta_i=\underset{\theta}{\textrm{argmax }}\sum_i\int_{z^{(i)}}Q_i(z^{(i)})\log\left(\frac{P(x^{(i)},z^{(i)};\theta)}{Q_i(z^{(i)})}\right)dz^{(i)}}
$$

![](../../ImgResources/expectation-maximization.png)

## K-means Clustering

We note $c^{(i)}$ the cluster of data point $i$ and $\mu_j$ the center of cluster $j$.

**Algorithm** - After randomly initializing the cluster centroids $\mu_1,\mu_2,...,\mu_k\in\mathbb{R}^n$ , the $k$-means algorithm repeats the following untill it converges:

$$
\boxed{c^{(i)}=\underset{j}{\textrm{arg min}}||x^{(i)}-\mu_j||^2}\quad\textrm{and}\quad\boxed{\mu_j=\frac{\displaystyle\sum_{i=1}^m1_{\{c^{(i)}=j\}}x^{(i)}}{\displaystyle\sum_{i=1}^m1_{\{c^{(i)}=j\}}}}
$$

![](../../ImgResources/k-means.png)

**Distortion function** - In order to see if the algorithm converges, we look at the distortion function defined as follows:

$$
\boxed{J(c,\mu)=\sum_{i=1}^m||x^{(i)}-\mu_{c^{(i)}}||^2}
$$

## Hierarchical clustering

**Algorithm** ―< It is a clustering algorithm with an agglomerative hierarchical approach that build nested clusters in a successive manner.

**Types** ― There are different sorts of hierarchical clustering 
algorithms that aims at optimizing different objective functions, which 
is summed up in the table below:

| Ward linkage                         | Average linkage                                 | Complete linkage                                 |
| ------------------------------------ | ----------------------------------------------- | ------------------------------------------------ |
| Minimize within the cluster distance | Minimize average distance between cluster pairs | Minimize maximum distance between cluster pairs. |

### Clustering assessment metrics

In an unsupervised learning setting, it is often hard to assess the performance of a model since we don't have the ground truth labels as 
was the case in the supervised learning setting.

**Silhouette coefficient** ― By noting $a$ and $b$ the mean distance between a sample and all other points in the same  class, and between a sample and all other points in the next nearest  cluster, the silhouette coefficient $s$ for a single sample is defined as follows:

$$
\boxed{s=\frac{b-a}{\max(a,b)}}
$$

**Calinski-Harabaz index** ― By noting $k$ the number of clusters, $B_k$ and $W_k$ the between and within-clustering dispersion matrices respectively defined as :

$$
B_k=\sum_{j=1}^kn_{c^{(i)}}(\mu_{c^{(i)}}-\mu)(\mu_{c^{(i)}}-\mu)^T
$$

$$
and \quad\quad W_k=\sum_{i=1}^m(x^{(i)}-\mu_{c^{(i)}})(x^{(i)}-\mu_{c^{(i)}})^T
$$

the Calinski-Harabaz index $s(k)$ indicates how well a clustering model defines its clusters, such that the higher the score, the more dense and well separated the clusters are. It is defined as follows:

$$
\boxed{s(k)=\frac{\textrm{Tr}(B_k)}{\textrm{Tr}(W_k)}\times\frac{N-k}{k-1}}
$$

## Applications

- Text documents( Article Clustering )

- Market Segmentation

- Astronomical Data analysis

- Social network analysis

- Genome Analysis

**Refereces :**

[1.]

[2.]

[3.]
