## Notes for Chapter 3: Getting started with neural networks

* Three most common use cases of neural networks:
    * Binary classification
    * Multiclass classification
    * Scalar regression

* Different layers are appropriate for different tensor formats and different type of data processing.
    * 2D: densely connected layers/fully connected, dense layers
    * 3D: recurrent layers such as LSTM layer
    * 4D: 2D convolution layers (Conv2D)

* The topology of a network defines a *hypothesis space*.

* Choosing the right network architecture is more an art than a science.

* The choice of right objective function matters.

* Two ways to define a model in Keras:
    * `Sequential`: only for linear stacks of layers 
    * functional API: for directed acyclic graphs of layers

* Two key architecture decisions to make about a stack of Dense layers:
    * How many layers to use
    * How many hidden units to choose for each layer

* Activation functions: non-linearity, to get access to a much richer hypothesis space.

* Crossentry is usually the best choice when dealing with models that output possibilities.
    * `binary_crossentropy`
    * `categorical_crossentropy`

* To prevent overfitting, be sure to always monitor performance on data that is outside of the training set.

* If you encode the labels by casting them as an integer tensor, the loss function should be `sparse_categorical_crossentropy` 

* The quantities used for normalization are computed using the training data! Never use any quantities computed on the test data!

* In general, the less training data you have, the worse overfitting will be. Using a small network is one way to mitigate overfitting.

* For regression problems, the loss function `mse` (mean square error) is widely used. The metric monitored is `mae` (mean absolute error).

* When train data set is small and thus a small validation set, the best practice is to use *K-fold* cross-validation.