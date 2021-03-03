# Decision tree:

Directed graph for representation of decision rules

## Properties

- One node where no edge terminates ( Root node )

- In all other nodes: exactly one edge terminates ( Leaf node )

- All nodes can be reached from the root on exactly one path

![](/home/mnpr_term/Documents/Knowledgebase/docsVC-ed/Markdowns/AI/ImgResources/Decisiontree.png)

@dzone.com

- Each node specifies a test for some attribute ( Variable )

- Each branch / edge corresponds to a possible value of the attribute.

- Each leaf assigns a class (for classification) / some value (for regression)

### The Greedy approach

> "The Greedy Approach is based on the concept of Heuristic Problem 
> Solving by making an optimal local choice at each node. By making these  local optimal choices, we reach the approximate optimal solution globally."

1. At each stage (node), pick out the best feature as the test condition.

2. Now split the node into the possible outcomes ( internal nodes ).

3. Repeat the above steps until all the test conditions have been exhausted into leaf nodes.

**How to pick the starting test conditon ?**

<u>Entropy</u> : Entropy in Decision Tree stands for homogeneity. If the data is completely homogenous, the entropy is 0; otherwise, if the data is divided (50-50%) entropy is 1.

<u>Information Gain</u> : Information Gain is the decrease/increase in Entropy value when the node is split.

An attribute should have the highest information gain to be selected for splitting. Based on the computed values of Entropy and Information Gain, we choose the best attribute at any particular step.

### Implementation( Python )

### Classification

<u>Tools</u> :

- Pandas

- Numpy

- Matplotlib

- Scikit-Learn

<u>Dataset</u> :

- UCI ( banknote authentication ) Dataset

<u>Notebook</u> : [DecisionTreeClassification](https://github.com/Mnpr/ML_Implementations/blob/master/DecisionTreeClassification.ipynb)

### Regression

<u>Tools</u> :

- Pandas

- Numpy

- Matplotlib

- Scikit-Learn

<u>Dataset</u> :

- *FSU ( Petrol Consumption) Data Set*

<u>Notebook</u> : [DecisionTreeRegression](https://github.com/Mnpr/ML_Implementations/blob/master/DecisionTreeRegression.ipynb)

****
