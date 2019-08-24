# Auto-Encoders
`An autoencoder  to learn efficient data codings in an unsupervised manner.`

_Autoencoder is an unsupervised artificial neural network that learns how to efficiently compress and encode data then learns how to reconstruct the data back from the reduced encoded representation to a representation that is as close to the original input as possible._

Autoencoder, by design, reduces data dimensions by learning how to ignore the noise in the data.

## About the repo

This repo contains the code for simple autoencoders as well as autoencoders by CNN.
Denoising is also a major concept covered in the repo .

## PART:A - Simple Autoencoder


We'll start off by building a simple autoencoder to compress the MNIST dataset. With autoencoders, we pass input data through an encoder that makes a compressed representation of the input. Then, this representation is passed through a decoder to reconstruct the input data. Generally the encoder and decoder will be built with neural networks, then trained on example data. title

In this notebook, we'll be build a simple network architecture for the encoder and decoder. Let's get started by importing our libraries and getting the dataset.

![Simple Autoencoder](https://github.com/Ratna04priya/Auto-Encoders/blob/master/images/autoencoder_1.png)

We'll train an autoencoder with these images by flattening them into 784 length vectors. The images from this dataset are already normalized such that the values are between 0 and 1. Let's start by building basically the simplest autoencoder with a single Relu hidden layer. This layer will be used as the compressed representation. Then, the encoder is the input layer and the hidden layer. The decoder is the hidden layer and the output layer. Since the images are normalized between 0 and 1, we need to use a sigmoid activation on the output layer to get values matching the input.

![Structure](https://github.com/Ratna04priya/Auto-Encoders/blob/master/images/simple_autoencoder.png)


## PART:B - Convolutional_Autoencoder (Using CNN)

 Sticking with the MNIST dataset, we'll improve our autoencoder's performance using convolutional layers. Again, loading modules and the data.
 
 
 ### Network Architecture

The encoder part of the network will be a typical convolutional pyramid. Each convolutional layer will be followed by a max-pooling layer to reduce the dimensions of the layers. The decoder though might be something new to you. The decoder needs to convert from a narrow representation to a wide reconstructed image. For example, the representation could be a 4x4x8 max-pool layer. This is the output of the encoder, but also the input to the decoder. We want to get a 28x28x1 image out from the decoder so we need to work our way back up from the narrow decoder input layer. A schematic of the network is shown below.

![convolutional_autoencoder.png](https://github.com/Ratna04priya/Auto-Encoders/blob/master/images/convolutional_autoencoder.png)

Here our final encoder layer has size 4x4x8 = 128. The original images have size 28x28 = 784, so the encoded vector is roughly 16% the size of the original image. These are just suggested sizes for each of the layers. Feel free to change the depths and sizes, but remember our goal here is to find a small representation of the input data.

### Denoising

As I've mentioned before, autoencoders like the ones you've built so far aren't too useful in practive. However, they can be used to denoise images quite successfully just by training the network on noisy images. We can create the noisy images ourselves by adding Gaussian noise to the training images, then clipping the values to be between 0 and 1. We'll use noisy images as input and the original, clean images as targets. Here's an example of the noisy images I generated and the denoised images.

![Denoising](https://github.com/Ratna04priya/Auto-Encoders/blob/master/images/denoising.png)

### Checking out the performance

On opening the method of convolution notebook, we'll be clearly able to see the results provided by the network.


