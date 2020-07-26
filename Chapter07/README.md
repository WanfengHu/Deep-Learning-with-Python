# Notes for Chapter 7: Advanced deep-learning best practices

## the Keras functional API

* Multimodal inputs: merge data from different input sources, processing each type of data using different kinds of neural layers.

* Multioutput models: predict multiple target attributes of input data.

* Graph-like models: DAG (directed acyclic graphs), residual connections.

* Use layers as functions that take tensors and return tensors.

* Neural networks in Keras are allowed to be arbitrary *directed acyclic graphs* of layers.

* In general, adding residual connections to any model that has more than 10 layers is likely to be beneficial.

* Layer weight sharing: when a layer instance is called twice, you reuse the same weights with every call.

## Keras callbacks and TensorBoard

* Ways to use callbacks:
    * Model checkpointing
    * Early stopping
    * Dynamically adjusting the value of certain parameters during training
    * Logging training and validation metrics during training, or visualizing the representations learned by the model as they're updated

* Model checkpoint and early stopping
    * `EarlyStopping`:interrupt training once a target metric has stopped improving for a fixed number of epochs.
    * `ModelCheckpoint`: continually save the model during training (optionally, save only the current best model so far).

* `ReduceLROnPlateau`: reduce/increase the learning rate when validation loss has stopped improving.

* Writing your own callback:
    * subclass `keras.callbacks.Callback`
    * implement methods such as `on_epoch_begin`, `on_batch_begin`, `on_train_begin`, etc.

* TensorBoard:
    * Visually monitoring metrics during training
    * Visualizing your model architecture
    * Visualizing histograms of activations and gradients
    * Exploring embeddings in 3D

## Getting the most out of your models

* Advanced architecture patterns:
    * batch normalization `BatchNormalization` / batch renormalization
    * depthwise separable convolution: fewer trainable weights and floating-point operations (lighter and faster) with a better result.

* Hyperparameter optimization

* Model ensembling
    * should ensemble models that are as good as possible while being as different as possible.