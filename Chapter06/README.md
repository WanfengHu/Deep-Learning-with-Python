# Notes for Chapter 6: Deep learning for text and sequences

Two fundamental deep-learning algorithms for sequence processing:
    * Recurrent neural networks
    * 1D convnets

## Working with text data

* Deep-learning for NLP is pattern recognition applied to words, sentences and paragraphs.

* The different units into which the text can be broken down (words, characters, n-grams) are called *tokens*

* Breaking text into tokens is called *tokenization*

* Two major ways to associate a vector with a token:
    * one-hot encoding
    * token embedding (word embedding)

* N-grams: groups of N (or fewer) consecutive words that you can extract from a sentence.

* Word embeddings pack more information into far fewer dimensions.

* Word embeddings are learned from data.

## Understanding recurrent neural networks

* *Feedforward networks*: have no memory, such as densely connected networks and convnets.

* RNN: processed sequences by iterating through the sequence elements and maintaining a state containing information relative to what it has seen so far.

* RNN has an internal loop.

* When stacking several recurrent layers one after the other, the intermediate layers have to return full sequence of outputs.

* *Vanishing gradient problem*: as you keep adding layers to a network, the network eventually becomes untrainable.

* LSTM: Long Short-Term Memory, saves information for later, thus preventing older signals from gradually vanishing during processing.

* GRU: Gated Recurrent Unit, cheaper to run, but may not have as much representational power as LSTM.

## Advanced use of RNN

* Three techniques for improving the performance and generalization of RNN
    * Recurrent dropout
    * Stacking recurrent layers
    * Bidirectional recurrent layers

* Sometimes, unless the learning algorithm is hardcoded to look for a specific kind of simple model, parameter learning can sometimes fail to find a simple solution to a simple problem.

* Machine learning is applicable to datasets where the past is a good predictor of the future.

## 1D convnets

* Extracts subsequences from sequences.

* Can offer fast alternative to RNNs for simple tasks such as text classification and timeseries forecasting.

* Can use larger convolution windows.