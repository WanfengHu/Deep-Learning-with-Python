## Notes for Chapter 2: The mathematical building blocks of neural networks

* In machine learning, a category in a classification problem is called a class. Data points are called samples. The class associated with a specific sample is called a label.

* Overfitting: the fact that machine-learning models tend to perform worse on new data than on their training data.

* A tensor is difined by three key attributes:
    * Rank: number of axes. `ndim`
    * Shape
    * Data type `dtype`

* Samples axis/batch axis. In general, the first axis (axis 0).

* Vector data: 2D (samples, features)
* Timeseries data/sequence data: 3D (samples, timesteps. features)
* Images: 4D (sample, height, weight, channels)/(s, c, h, w)
* Video: 5D (sample, frames, height, weight, channels)/(s,f,c,h,w)

* Tensor operations
    * Element-wise operations
    * Broadcasting
    * Tensor dot (tensor product)
    * Tensor reshaping

* Layer parameters:
    ```python
    output = relu(dot(W, input) + b) 
    # W/b: weights/trainable parameters 
    # W: kernel attributes
    # b: bias attributes
    ```

* SGD (Stochastic Gradient Descent)
    * mini-batch SGD : use mini-batches of reasonable size as input
    * true SGD: a single sample each time
    * batch SGD: all the samples

* Variants (optimization methods/optimizers)
    * SGD with momentum
    * Adagrad
    * RMSProp

* Momentum addressed two issues with SGD: convergence speed and local minima. Update `W` based on current gradient and previous parameter.

* Each iteration over all the trainning data is called an *epoch*