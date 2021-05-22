# MNIST-Sum-CNN
Objective - Build a neural network that takes 3 inputs - an image from MNIST dataset, a random number between 0 to 9, to calculate 2 outputs - the "number" represented in MNIST image and sum of this number with the random number provided as input to the network.

Inputs - 
1. An MNIST dataset image of size 28x28x1
2. Random number between 0-9, represented as one-hot encoding

Outputs - 
1. Prediction of number present in MNIST image
2. Sum of this number with the random number provided in input

Data Generation - A CustomDataset class (inheriting from torch.utils.data.Dataset) that combines MNIST image, label with random number, sum of the numbers and returns through __getitem__ method for use as iterator.

Combining the 2 inputs - MNIST image is passed through the network and the number represented in the image is predicted. Then the one-hot encoding of the input random number is concatenated with last convolution output of MNIST prediction. This concatenated tensor is then convoluted through 3 layers for calculating the output of sum.
