# Deep Learning Long Short-Term Memory (LSTM) Networks: What You Should Remember - MissingLink.ai

> Learn the basics of Long Short-Term Memory networks (LSTM)s, how the architecture of LSTMs allow them to solve tasks that traditional RNNs are unable to.

![Neural Network Concepts Cover](https://missinglink.ai/wp-content/uploads/2019/04/cover-Healthcare.png)

What Is a Long Short-Term Memory Neural Network?
------------------------------------------------

The German researchers, Hochreiter and Schmidhuber, introduced the idea of long short-term memory networks in an [paper](http://www.bioinf.jku.at/publications/older/2604.pdf) published in 1997. LSTM is a unique type of [Recurrent Neural Network](https://missinglink.ai/guides/neural-network-concepts/recurrent-neural-network-glossary-uses-types-basic-structure/) (RNN) capable of learning long-term dependencies, which is useful for certain types of prediction that require the network to retain information over longer time periods, a task that traditional RNNs struggle with.

The Problem with Recurrent Neural Networks
------------------------------------------

A recurrent neural network is a deep learning algorithm designed to deal with a variety of complex computer tasks such as object classification and speech detection. RNNs are designed to handle a sequence of events that occur in succession, with the understanding of each event based on information from previous events.

Ideally, we would prefer to have the deepest RNNs so they could have a longer memory period and better capabilities. These could be applied for many real-world use-cases such as stock prediction and enhanced speech detection. However, while they sound promising, RNNs are rarely used for real-world scenarios because of the vanishing gradient problem.

### The Vanishing Gradient Problem

This is one of the most significant challenges for RNNs performance. In practice, the architecture of RNNs restricts its long-term memory capabilities, which are limited to only remembering a few sequences at a time. Consequently, the memory of RNNs is only useful for shorter sequences and short time-periods.

The vanishing gradient problem restricts the memory capabilities of traditional RNNs—adding too many time-steps increases the chance of facing a gradient problem and losing information when you use [backpropagation](https://missinglink.ai/guides/neural-network-concepts/backpropagation-neural-networks-process-examples-code-minus-math/).

How Long Short-Term Memory Networks Solve the Vanishing Gradient Problem with Recurrent Neural Networks
-------------------------------------------------------------------------------------------------------

LSTMs are designed to overcome the vanishing gradient problem and allow them to retain information for longer periods compared to traditional RNNs. LSTMs can maintain a constant error, which allows them to continue learning over numerous time-steps and backpropagate through time and layers.

![LSTM gated cells](https://missinglink.ai/wp-content/uploads/2019/08/A.png)

Additionally, as seen in the diagram above, LSTMs use gated cells to store information outside the regular flow of the RNN. With these cells, the network can manipulate the information in many ways, including storing information in the cells and reading from them. The cells are individually capable of making decisions regarding the information and can execute these decisions by opening or closing the gates.

The ability to retain information for a long period of time gives LSTM the edge over traditional RNNs in these tasks.

### Long Short-Term Memory Architecture

The chain-like architecture of LSTM allows it to contain information for longer time periods, solving challenging tasks that traditional RNNs struggle to or simply cannot solve.

The three major parts of the LSTM include:

* **Forget gate**—removes information that is no longer necessary for the completion of the task. This step is essential to optimizing the performance of the network.

![LSTM forget gate](https://missinglink.ai/wp-content/uploads/2019/08/B.png)

* **Input gate**—responsible for adding information to the cells

![LSTM input gate](https://missinglink.ai/wp-content/uploads/2019/08/C.png)

* **Output gate**—selects and outputs necessary information

![LSTM output gate](https://missinglink.ai/wp-content/uploads/2019/08/D.png)

Applications of Long Short-Term Memory Networks
-----------------------------------------------

LSTMs can be applied to a variety of deep learning tasks that mostly include prediction based on previous information. Two noteworthy examples include text prediction and stock prediction:

### Text Prediction

The long-term memory capabilities of LSTM means it excels at predicting text sequences. In order to predict the next word in a sentence, the network has to retain all the words that preceded it. One of the most common applications of text prediction is in chatbots used by eCommerce sites.

### Stock Prediction

Simple Machine Learning (SML) models are able to predict stock values and prices based on inputs such as the opening value and the volume of the stock. While these values do take part in stock prediction, they lack a key component. To properly predict a stock value with high accuracy, the model needs to take into account one of the biggest factors—the trend of the stock. To do so, the model needs to identify the trend based on the values recorded over the preceding days—a task suited to an LSTM network.

Running Long Short-Term Memory Networks with MissingLink
--------------------------------------------------------

Nowadays, you can use deep learning frameworks such as TensorFlow or PyTorch to create your own RNNs and LSTMs with speed and ease. However, if you try to apply these networks in real-world scenarios, you may run into some challenges.

* ![tracking experiments](https://missinglink.ai/wp-content/uploads/2018/11/graph.png) 
  
  ### Tracking progress across multiple LSTM experiments with many hyperparameters
  
  Running an LSTM model in real-world scenarios requires intensive tasks such as training the model and tracking multiple experiments with a high number of hyperparameters, which can be demanding and time-consuming.

* ![running experiment across multiple machines](https://missinglink.ai/wp-content/uploads/2018/11/2server.png) 
  
  ### Running an experiment across multiple machines
  
  Real-world projects often require running experiments on multiple machines. Settings all these machines up and distributing the workflow between them can become tedious.

* ![manage training datasets](https://missinglink.ai/wp-content/uploads/2018/11/filepics.png) 
  
  ### Managing training datasets
  
  LSTMs are designed to make predictions based on large amounts of data. The time-step sequence of LSTMs can exceed 1000 steps. Consequently, running LSTM networks can be highly intensive and time-consuming.

These challenges become much more manageable with MissingLink, a deep learning platform that can help you automate these aspects of LSTM deployment, so you can concentrate on building the best network. [Request a demo](https://missinglink.ai/) to see how easy it is.

Learn More About Neural Network Concepts
----------------------------------------

[Source](https://missinglink.ai/guides/neural-network-concepts/deep-learning-long-short-term-memory-lstm-networks-remember/)