# Notes for Chapter 1: What is deep learning?

* Deep learning $\subset$  Machine learning $\subset$ Artificial intelligence

* AI: the effort to automate intellectual tasks normally performed by humans.
    * symbolic AI: Rules + Data --> Answers

* Machine Learning: Data + Answers --> Rules
    * Trained rather than explicitly programmed.

* Three things needed to do machine learning:
    * Input data points
    * Examples of the expected output
    * A way to measure whether the algorithm is doing a good job

* Machine-learning models are all about finding appropriate representations for the input data. (meaningfully transform data)

* "Learning" describes an automatic search process for better representations. 

* Machine learning is, technically: searching for useful representations of some input data, within a predefined space of possibilities, using guidance from a feedback signal.

* Deep learning: 'deep', successive layers of representations. The number of layers: 'depth'. The layered representation are (almost always) learned via models called *nueral networks*.

* Weights/parameters of a layer stores the transformation of a layer.

* Loss function: measure the distance between prediction and the true targets.

* Optimizer: adjust the weights using loss score. Backpropagation algorithm: central algo in deep learning.

* Probabilistic modeling: Naive Bayes/ logistic regression (for classfication). Machine learning classifier.

* Kernel methods: group of classfication algorithms, such as SVM (Support Vector Machine)

* Decision Tree, Random Forest, Gradient Boosting Machines.

* Feature engineering: make the initial data more amenable to processing by machine learning methods. Deep learning completely automates this step. 

* Kernel function: maps two points in initial space to the distance between the points in the target representation space.

* Two essential characteristics of deep learning:
    * incremental, layer-by-layer way in which increasingly complex representations are developed.
    * these intermidiate incremental representations are learned jointly.

* Gradient boosting machines for shallow learning problems (structured data); Deep learning for perceptual problems.