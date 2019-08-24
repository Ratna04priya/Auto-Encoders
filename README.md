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

We'll train an autoencoder with these images by flattening them into 784 length vectors. The images from this dataset are already normalized such that the values are between 0 and 1. Let's start by building basically the simplest autoencoder with a single ReLU hidden layer. This layer will be used as the compressed representation. Then, the encoder is the input layer and the hidden layer. The decoder is the hidden layer and the output layer. Since the images are normalized between 0 and 1, we need to use a sigmoid activation on the output layer to get values matching the input.

![Structure](https://github.com/Ratna04priya/Auto-Encoders/blob/master/images/autoencoder_1.png)
