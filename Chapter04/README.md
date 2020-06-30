# Notes for Chapter 4: Fundamentals of machine learning

## Four branches of machine learning

* Supervised learning: learning to map input data to known targets (annotations).
    * Classdification
    * Regression
    * Sequence generation
    * Syntax tree prediction
    * Object detection
    * Image segmentation

* Unsupervised learning: finding interesting transformations of the input data without the help of any targets.
    * Dimensionality reduction
    * clustering

* Self-supervised learning: supervised leaning without human-annotated labels. Labels are generated from the input data, typically using a heuristic algorithm.

* Reinforcement leanring: an agent receives information about its environment and learns to choose actions that will maximize some reward.

## Evaluating machine-leanring models

* Split the available data into three sets: training, validation and test.

* *Information leaks*: Every time you tune a hyperparameter of your model (number of layers, the size of layers) based on the model's performance on the validation set, some information about the validation data leaks into the model.

* Three classic evaluation recipes:
    * simple hold-out validation
    * K-fold validation
    * iterated K-fold validation with shuffling

* Randomly shuffle the data before splitting it into training and test sets.

* If the model is to predict future trend, do not randomly shuffle before splitting.

* Make sure the training set and validation set are disjoint.

## Data preprocessing, feature engineering, feauture learning

* Data preprocessing for neural networks
    * Vectorization: process the data into tensors.
    * Normalization: the data should be small values and homogenous.
    * Handling missing values
    * Feature extraction

* Feature engineering: make the algorithm work better by applying hardcoded transformations to the data before it goes into a model.
    * Good features allows to solve problems more elegantly while using fewer resources.
    * Good features let you solve a problem with far less data. 

## Overfitting and underfitting

* To prevent a model from overfitting, the best solution is to get more training data.

* The next-best solution is to modulate the quantity of informations that the model is allowed to store or add constraints --> focus on the most prominent patterns.

* The processing of fighting overfitting is called *regularization*.

* Most common regularization techniques:
    * Reducing the network's size
    * Adding weight regularization
    * Adding dropout

* Adding weight regularization: If multiple models can explain the data, simpler models are less likely to overfit than complex ones. (principle of Occam's razor)
    * A simple model --> The distribution of parameter values has less entropy (or with fewer parameters)
    * Force the weights to take only small values, by adding to the loss function a *cost* associated with having large weights.
        * *L1 regularization*: cost is proportional to the absolute value of the weight coeffs.
        * *L2 regularization*: cost is proportional to the square of the value of the weight coeffs. Also called weight decay. 

* Adding dropout: one of the most effective and most commonly used regularization techniques for neural networks.
    * Randomly drop out (setting to zero) a number of output feature of a layer during the training.
    * Dropout rate: the fraction of the features that are zeroed out. (usually 0.2-0.5)
    * At test time, no dropout. Instead, the layer's output values are scaled down by a factor equal to drop rate, to balance for the fact that more units are active than at training time.

## The universal workflow of machine learning

1. Defining the problem and assembling a dataset.
2. Choosing a measure of success.
3. Deciding on an evaluation protocol.
4. Preparing the data.
5. Developing a model that does better than a baseline (statistical)
6. Scaling up: developing a model that overfits.
7. Rugularizing the model and tuning the hyperparameters.