# GAN with Denoising Feature Matching

An unofficial attempt to implement the GAN proposed in [Improving Generative Adversarial Networks with Denoising Feature Matching](http://openreview.net/forum?id=S1X7nhsxl) using Chainer.

Details such as activations and hyperparameters not presented in the paper are simply guessed.

The denoising autoencoder in the original papers is trained to reconstructs corrupted images with Gaussian noise. **In this implementation the autoencoder is trained to remove the noise instead**.

This implementation does not separately keep track of the batch normalization statistics for the discrimnator (including the feature extractor) and the denoising autoencoder for real and generated data.

The corruption function used when updating the parameters of the autoencoder is not annealed.

### Loss

The network is trained on 32x32 RGB images (3 channels) from CIFAR-10.

<img src="./samples/log.png" width="512px;"/>

#### Discriminator Loss

Traditional discriminator GAN loss.

#### Generator Loss

Traditional generator GAN loss and reconstruction error (L2, mean squared error).

#### Denoiser Loss

Denoising autoencoder reconstruction error (L2, mean squared error).

### Samples

**Epoch 1**

<img src="./samples/1.png" width="512px;"/>

**Epoch 10**

<img src="./samples/10.png" width="512px;"/>

**Epoch 20**

<img src="./samples/20.png" width="512px;"/>

**Epoch 30**

<img src="./samples/30.png" width="512px;"/>

**Epoch 30**

<img src="./samples/40.png" width="512px;"/>

