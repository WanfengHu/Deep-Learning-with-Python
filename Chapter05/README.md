# Notes for Chapter 5: Deep learning for computer vision

## Introduction to convnets

* Convolutional neural networks (*convnets*), almost universally used in computer vision applications.

* A convnet takes as input tensors of shape (image_height, image_width, image_channels).

* *Dense* layers learn global patterns in their input feature space (for MNIST, patterns involving all pixels).

* Convnets learn local patterns in small windows of the inputs. (For images, 2D windows).
    * The pattern they learn are translation invariant.
    * They can learn spatial hierarchies of patterns. (e.g. egdes -> larger patters)

* Convolutions operate over 3D tensors (*feature maps*) (height, width, depth). The output of depth can be arbitrary, they stand for filters.

* Convolutions are defined by 2 key parameters:
    * Size of patches extracted from the inputs
    * Depth of the output feature map

* The output width and height may differ from the input, for 2 reasons:
    * Border effects, can be countered by padding.
    * The use of strides: the distance between two successive windows.

* The max-pooling operation: to aggressively downsample feature maps, output max value of each window, stride is usually 2 --> downsample by a factor of 2.

* The reason to use downsampling is to reduce the number of feature-map coefficients to process and to induce spatial-filter hierarchies by making successive convolution layers look at increasingly large windows.

## Training a convnet on a small dataset 

* Training a convnet from scratch on a small dataset -> data augmentation -> feature extraction with a pretrained network -> fine-tuning a pretrained network.

* Technique that helps mitigate overfitting, specific to computer vision and used almost universally when processing images with deep-learning models: *data augmentation*.

* Feature extraction: using the representations learned by a pretrained network to extract interesting features from new samples.

* Convnets for image classification: convolutional base + densely connected classifier. Keep the convolutional base and training a new classifier on top of the output.

* Conv_base should be frozen to prevent the update of the weights.

* *Fine-turning*: unfreeze a few of the top layers of a frozen model base and train it. Slightly adjust the more abstract representations of the model to make more relevent for the problem at hand.

* Fine-tuning the top layers of the conv base after the classifier has already been trained.

## Visualizing what convnets learn

* Three of the most accessible techniques:
    * Visualizing intermidiate convnet outputs (intermediate activations)
    * Visualizing convnets filters
    * Visualizing heatmaps of class activation in an image

* The features extracted by a layer become increasingly abstract with the depth of the layer.

* The activations of higher layers carry less and less information about the specific input being seen, and more and more information about the target (the class of the image)

* Heatmaps of class activation: useful for understanding which parts of a given image led a convnet to its final classification decision. Called class activation map (CAM) 