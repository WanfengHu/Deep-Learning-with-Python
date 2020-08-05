# Notes for Chapter 8: Generative deep learning

* Any network that can model the probability of the next token (characters/words) given the previous ones is called a *language model*.

* Sampling strategy:
    * Greedy sampling: always choosing the most likely next token.
    * stochastic sampling: sampling from the probability distribution for the next character. e.g: if `e` has a probability of 0.3 being the next char, you'll choose it 30% of the time.

* softmax temperature: higher --> higher entropy, more surprising data.

* DeepDream: maximize the activation of entire layers rather than that of a specific filter --> mixing together visualizations of large numbers of features at once.
    * Algo: difine a list of scales/octaves, each successive scale is larger than the previous one by a factor of 1.4. Start by processing a small image and then increasingly scale it up. Detail reinjection upon upscaling.

* Neural style transfer: applying the style of a reference image to a target image while conserving the content of the target image.
    * *style*: textures, colors, visual patterns in the image at various spatial scales.
    * *content*: higher-level macrostructure of the image
    * the key is to define a loss function.
    * Preserve content by maintaining similar high-level layer activations. Preserve style by maintaining similar correlations within activations for both low-level and high-level layers.

* Generating images, sound, music, text...
    * VAEs (variational autoencoders); Decoder; Great for learning latent spaces that are well structured, where specific directions encode a meaningful axis of variation in the data.
    * GANs (generative adversarial networks); Generator; Generate images that can potentially be highly realistic, but the latent space they come from may not have as much structure and continuity.

* VAE turns the image into the parameters of a statistical distribution: a mean and a variance.

* GANs enable the generation of fairly realistic images by forcing the generated images to be statistically almost indistinguishable from real ones.
    * Generator network: a forger network, takes as input a random vector (a random point in the latent space), and decodes it into a synthetic image
    * Discriminator network (adversary): an expert network, takes as input an image (real or synthetic), and predicts whether the image came from the training set or was created by the generator network.
    * Each being trained to best the other.
    * a system where the optimization minimum isn't fixed. A dynamic system where the optimization process is seeking not a minimum, but an equilibrium between two forces.