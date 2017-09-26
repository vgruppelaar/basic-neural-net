# basic-neural-net
I have implemented a simple vanilla feedforward neural network for classification of the plant data in the Iris dataset, in Python. The work is divided over two files, nn.py and main.py, which contain the neural network class and the script that trains and applies it to the dataset.

Running main.py shows the final results of the neural network classification. 

Neural network implementation:
The neural network implementation has the following characteristics:

   Can be constructed with any number of hidden layers and any number of nodes per hidden layer.
	 All hidden layers use logistic sigmoidal activation functions.
	 The output layer also uses logistic sigmoidal activation functions, but the implementation makes it easy to substitute a different function.
	 The network trains using backpropagation and a cross-entropy loss function.
	 Early termination of training was implemented, to speed up the process.
	 The network can use L2 regularization to improve performance.
	 The network can use dropout to improve performance.

In order to save programming time, the stochastic gradient descent calculations were not implemented in a matrix based approach, and no use was made of GPU capabilities.

Design choices:
The dataset was split into three sections. 60% of the dataset was used to train the neural network, 20% for validating the chosen hyperparameters, and the final 20% for testing the classification performance of the network. For such a small dataset, perhaps k-fold cross-validation is a better choice, but in the interest of time it was not implemented.

The hyperparameters were tuned manually using the validation dataset, resulting in the following values:
 Learning rate: 0.075
 Epochs: 500 (high number of epochs can be used since early termination is implemented).
 Maximum training epochs without a new maximum validation accuracy before early termination: 50
 Stochastic Gradient Descent batch size: 10
 L2 regularization $\lambda$: 0.0 (no L2 regularization used, since it did not result in improved performance or robustness)
\ Dropout probability = 0.05
